# Swift tips & tricks ⚡️

One of the things I really love about Swift is how I keep finding interesting ways to use it in various situations, and when I do - I usually share them on [Twitter](https://twitter.com/johnsundell). Here's a collection of all the tips & tricks that I've shared so far. Each entry has a link to the original tweet, if you want to respond with some feedback or question, which is always super welcome! 🚀

I also write a weekly blog about Swift development at [swiftbysundell.com](https://www.swiftbysundell.com) 😀

## [#28 Defining static URLs using string literals](https://twitter.com/johnsundell/status/886876157479616513)

🌏 Tired of using `URL(string: "url")!` for static URLs? Make `URL` conform to `ExpressibleByStringLiteral` and you can now simply use `"url"` instead.

```swift
extension URL: ExpressibleByStringLiteral {
    // By using 'StaticString' we disable string interpolation, for safety
    public init(stringLiteral value: StaticString) {
        self = URL(string: "\(value)").require(hint: "Invalid URL string literal: \(value)")
    }
}

// We can now define URLs using static string literals 🎉
let url: URL = "https://www.swiftbysundell.com"
let task = URLSession.shared.dataTask(with: "https://www.swiftbysundell.com")

// In Swift 3 or earlier, you also have to implement 2 additional initializers
extension URL {
    public init(extendedGraphemeClusterLiteral value: StaticString) {
        self.init(stringLiteral: value)
    }

    public init(unicodeScalarLiteral value: StaticString) {
        self.init(stringLiteral: value)
    }
}
```

*To find the extension that adds the `require()` method on `Optional` that I use above, check out [Require](https://github.com/johnsundell/require).*

## [#27 Manipulating points, sizes and frames using math operators](https://twitter.com/johnsundell/status/885486106594115584)

✚ I'm always careful with operator overloading, but for manipulating things like sizes, points & frames I find them super useful.

```swift
extension CGSize {
    static func *(lhs: CGSize, rhs: CGFloat) -> CGSize {
        return CGSize(width: lhs.width * rhs, height: lhs.height * rhs)
    }
}

button.frame.size = image.size * 2
```

*If you like the above idea, check out [CGOperators](https://github.com/JohnSundell/CGOperators), which contains math operator overloads for all Core Graphics' vector types.*

## [#26 Using closure types in generic constraints](https://twitter.com/johnsundell/status/884794185722859520)

🔗 You can use closure types in generic constraints in Swift. Enables nice APIs for handling sequences of closures.

```swift
extension Sequence where Element == () -> Void {
    func callAll() {
        forEach { $0() }
    }
}

extension Sequence where Element == () -> String {
    func joinedResults(separator: String) -> String {
        return map { $0() }.joined(separator: separator)
    }
}

callbacks.callAll()
let names = nameProviders.joinedResults(separator: ", ")
```

*(If you're using Swift 3, you have to change `Element` to `Iterator.Element`)*

## [#25 Using associated enum values to avoid state-specific optionals](https://twitter.com/johnsundell/status/879427146367848448)

🎉 Using associated enum values is a super nice way to encapsulate mutually exclusive state info (and avoiding state-specific optionals).

```swift
// BEFORE: Lots of state-specific, optional properties

class Player {
    var isWaitingForMatchMaking: Bool
    var invitingUser: User?
    var numberOfLives: Int
    var playerDefeatedBy: Player?
    var roundDefeatedIn: Int?
}

// AFTER: All state-specific information is encapsulated in enum cases

class Player {
    enum State {
        case waitingForMatchMaking
        case waitingForInviteResponse(from: User)
        case active(numberOfLives: Int)
        case defeated(by: Player, roundNumber: Int)
    }
    
    var state: State
}
```

## [#24 Using enums for async result types](https://twitter.com/johnsundell/status/876920087885877248)

👍 I really like using enums for all async result types, even boolean ones. Self-documenting, and makes the call site a lot nicer to read too!

```swift
protocol PushNotificationService {
    // Before
    func enablePushNotifications(completionHandler: @escaping (Bool) -> Void)
    
    // After
    func enablePushNotifications(completionHandler: @escaping (PushNotificationStatus) -> Void)
}

enum PushNotificationStatus {
    case enabled
    case disabled
}

service.enablePushNotifications { status in
    if status == .enabled {
        enableNotificationsButton.removeFromSuperview()
    }
}
```

## [#23 Working on async code in a playground](https://twitter.com/johnsundell/status/876044534458847232)

🏃 Want to work on your async code in a Swift Playground? Just set `needsIndefiniteExecution` to true to keep it running:

```swift
import PlaygroundSupport

PlaygroundPage.current.needsIndefiniteExecution = true

DispatchQueue.main.asyncAfter(deadline: .now() + 3) {
    let greeting = "Hello after 3 seconds"
    print(greeting)
}
```

To stop the playground from executing, simply call `PlaygroundPage.current.finishExecution()`.

## [#22 Overriding self with a weak reference](https://twitter.com/johnsundell/status/874290749386477569)

💦 Avoid memory leaks when accidentially refering to `self` in closures by overriding it locally with a weak reference:

```swift
dataLoader.loadData(from: url) { [weak self] result in
    guard let `self` = self else {
        return
    }

    self.cache(result)
    
    ...
```

Note that the reason the above currently works is [because of a compiler bug](https://lists.swift.org/pipermail/swift-evolution/Week-of-Mon-20160118/007425.html) (which I hope gets turned into a properly supported feature soon).

## [#21 Using DispatchWorkItem](https://twitter.com/johnsundell/status/868849469558861824)

🕓 Using dispatch work items you can easily cancel a delayed asynchronous GCD task if you no longer need it:

```swift
let workItem = DispatchWorkItem {
    // Your async code goes in here
}

// Execute the work item after 1 second
DispatchQueue.main.asyncAfter(deadline: .now() + 1, execute: workItem)

// You can cancel the work item if you no longer need it
workItem.cancel()
```

## [#20 Combining a sequence of functions](https://twitter.com/johnsundell/status/865855870294523904)

➕ While working on a new Swift developer tool (to be open sourced soon 😉), I came up with a pretty neat way of organizing its sequence of operations, by combining their functions into a closure:

```swift
internal func +<A, B, C>(lhs: @escaping (A) throws -> B,
                         rhs: @escaping (B) throws -> C) -> (A) throws -> C {
    return { try rhs(lhs($0)) }
}

public func run() throws {
    try (determineTarget + build + analyze + output)()
}
```

*If you're familiar with the functional programming world, you might know the above technique as the [pipe operator](http://theburningmonk.com/2011/09/fsharp-pipe-forward-and-pipe-backward/) (thanks to [Alexey Demedreckiy](https://twitter.com/DAlooG) for pointing this out!)*

## [#19 Chaining optionals with map() and flatMap()](https://twitter.com/johnsundell/status/864130284140318720)

🗺 Using `map()` and `flatMap()` on optionals you can chain multiple operations without having to use lengthy `if lets` or `guards`:

```swift
// BEFORE

guard let string = argument(at: 1) else {
    return
}

guard let url = URL(string: string) else {
    return
}

handle(url)

// AFTER

argument(at: 1).flatMap(URL.init).map(handle)
```

## [#18 Using self-executing closures for lazy properties](https://twitter.com/johnsundell/status/863073311718338561)

🚀 Using self-executing closures is a great way to encapsulate lazy property initialization:

```swift
class StoreViewController: UIViewController {
    private lazy var collectionView: UICollectionView = {
        let layout = UICollectionViewFlowLayout()
        let view = UICollectionView(frame: self.view.bounds, collectionViewLayout: layout)
        view.delegate = self
        view.dataSource = self
        return view
    }()
    
    override func viewDidLoad() {
        super.viewDidLoad()
        view.addSubview(collectionView)
    }
}
```

## [#17 Speeding up Swift package tests](https://twitter.com/johnsundell/status/862721700584189953)

⚡️ You can speed up your Swift package tests using the `--parallel` flag. For [Marathon](https://github.com/johnsundell/marathon), the tests execute 3 times faster that way!

```
swift test --parallel
```

## [#16 Avoiding mocking UserDefaults](https://twitter.com/johnsundell/status/855713943809032192)

🛠 Struggling with mocking `UserDefaults` in a test? The good news is: you don't need mocking - just create a real instance:

```swift
class LoginTests: XCTestCase {
    private var userDefaults: UserDefaults!
    private var manager: LoginManager!
    
    override func setUp() {
        super.setup()
        
        userDefaults = UserDefaults(suiteName: #file)
        userDefaults.removePersistentDomain(forName: #file)
        
        manager = LoginManager(userDefaults: userDefaults)
    }
}
```

## [#15 Using variadic parameters](https://twitter.com/johnsundell/status/854365916716572672)

👍 Using variadic parameters in Swift, you can create some really nice APIs that take a list of objects without having to use an array:

```swift
extension Canvas {
    func add(_ shapes: Shape...) {
        shapes.forEach(add)
    }
}

let circle = Circle(center: CGPoint(x: 5, y: 5), radius: 5)
let lineA = Line(start: .zero, end: CGPoint(x: 10, y: 10))
let lineB = Line(start: CGPoint(x: 0, y: 10), end: CGPoint(x: 10, y: 0))

let canvas = Canvas()
canvas.add(circle, lineA, lineB)
canvas.render()
```

## [#14 Referring to enum cases with associated values as closures](https://twitter.com/johnsundell/status/848951678288228352)

😮 Just like you can refer to a Swift function as a closure, you can do the same thing with enum cases with associated values:

```swift
enum UnboxPath {
    case key(String)
    case keyPath(String)
}

struct UserSchema {
    static let name = key("name")
    static let age = key("age")
    static let posts = key("posts")
    
    private static let key = UnboxPath.key
}
```

## [#13 Using the === operator to compare objects by instance](https://twitter.com/johnsundell/status/847468284198797313)

📈 The `===` operator lets you check if two objects are the same instance. Very useful when verifying that an array contains an instance in a test:

```swift
protocol InstanceEquatable: class, Equatable {}

extension InstanceEquatable {
    static func ==(lhs: Self, rhs: Self) -> Bool {
        return lhs === rhs
    }
}

extension Enemy: InstanceEquatable {}

func testDestroyingEnemy() {
    player.attack(enemy)
    XCTAssertTrue(player.destroyedEnemies.contains(enemy))
}
```

## [#12 Calling initializers with dot syntax and passing them as closures](https://twitter.com/johnsundell/status/845560409126027264)

😎 Cool thing about Swift initializers: you can call them using dot syntax and pass them as closures! Perfect for mocking dates in tests.

```swift
class Logger {
    private let storage: LogStorage
    private let dateProvider: () -> Date
    
    init(storage: LogStorage = .init(), dateProvider: @escaping () -> Date = Date.init) {
        self.storage = storage
        self.dateProvider = dateProvider
    }
    
    func log(event: Event) {
        storage.store(event: event, date: dateProvider())
    }
}
```

## [#11 Structuring UI tests as extensions on XCUIApplication](https://twitter.com/johnsundell/status/844945775088013312)

📱 Most of my UI testing logic is now categories on `XCUIApplication`. Makes the test cases really easy to read:

```swift
func testLoggingInAndOut() {
    XCTAssertFalse(app.userIsLoggedIn)
    
    app.launch()
    app.login()
    XCTAssertTrue(app.userIsLoggedIn)
    
    app.logout()
    XCTAssertFalse(app.userIsLoggedIn)
}

func testDisplayingCategories() {
    XCTAssertFalse(app.isDisplayingCategories)
    
    app.launch()
    app.login()
    app.goToCategories()
    XCTAssertTrue(app.isDisplayingCategories)
}
```

## [#10 Avoiding default cases in switch statements](https://twitter.com/johnsundell/status/844608407718051847)

🙂 It’s a good idea to avoid “default” cases when switching on Swift enums - it’ll “force you” to update your logic when a new case is added:

```swift
enum State {
    case loggedIn
    case loggedOut
    case onboarding
}

func handle(_ state: State) {
    switch state {
    case .loggedIn:
        showMainUI()
    case .loggedOut:
        showLoginUI()
    // Compiler error: Switch must be exhaustive
    }
}
```

## [#9 Using the guard statement in many different scopes](https://twitter.com/johnsundell/status/844262618630148098)

💂 It's really cool that you can use Swift's 'guard' statement to exit out of pretty much any scope, not only return from functions:

```swift
// You can use the 'guard' statement to...

for string in strings {
    // ...continue an iteration
    guard shouldProcess(string) else {
        continue
    }
    
    // ...or break it
    guard !shouldBreak(for: string) else {
        break
    }
    
    // ...or return
    guard !shouldReturn(for: string) else {
        return
    }
    
    // ..or throw an error
    guard string.isValid else {
        throw StringError.invalid(string)
    }
    
    // ...or exit the program
    guard !shouldExit(for: string) else {
        exit(1)
    }
}
```

## [#8 Passing functions & operators as closures](https://twitter.com/johnsundell/status/843771235897098240)

❤️ Love how you can pass functions & operators as closures in Swift. For example, it makes the syntax for sorting arrays really nice!

```swift
let array = [3, 9, 1, 4, 6, 2]
let sorted = array.sorted(by: <)
```

## [#7 Using #function for UserDefaults key consistency](https://twitter.com/johnsundell/status/842058888371421185)

🗝 Here's a neat little trick I use to get UserDefault key consistency in Swift (#function expands to the property name in getters/setters). Just remember to write a good suite of tests that'll guard you against bugs when changing property names.

```swift
extension UserDefaults {
    var onboardingCompleted: Bool {
        get { return bool(forKey: #function) }
        set { set(newValue, forKey: #function) }
    }
}
```

## [#6 Using a name already taken by the standard library](https://twitter.com/johnsundell/status/839209426015891456)

📛 Want to use a name already taken by the standard library for a nested type? No problem - just use `Swift.` to disambiguate:

```swift
extension Command {
    enum Error: Swift.Error {
        case missing
        case invalid(String)
    }
}
```

## [#5 Using Wrap to implement Equatable](https://twitter.com/johnsundell/status/835860744176553984)

📦 Playing around with using [Wrap](https://github.com/johnsundell/wrap) to implement `Equatable` for any type, primarily for testing:

```swift
protocol AutoEquatable: Equatable {}

extension AutoEquatable {
    static func ==(lhs: Self, rhs: Self) -> Bool {
        let lhsData = try! wrap(lhs) as Data
        let rhsData = try! wrap(rhs) as Data
        return lhsData == rhsData
    }
}
```

## [#4 Using typealiases to reduce the length of method signatures](https://twitter.com/johnsundell/status/823554020639916033)

📏 One thing that I find really useful in Swift is to use typealiases to reduce the length of method signatures in generic types:

```swift
public class PathFinder<Object: PathFinderObject> {
    public typealias Map = Object.Map
    public typealias Node = Map.Node
    public typealias Path = PathFinderPath<Object>
    
    public static func possiblePaths(for object: Object, at rootNode: Node, on map: Map) -> Path.Sequence {
        return .init(object: object, rootNode: rootNode, map: map)
    }
}
```

## [#3 Referencing either external or internal parameter name when writing docs](https://twitter.com/johnsundell/status/823131585830645760)

📖 You can reference either the external or internal parameter label when writing Swift docs - and they get parsed the same:

```swift
// EITHER:

class Foo {
    /**
    *   - parameter string: A string
    */
    func bar(with string: String) {}
}

// OR:

class Foo {
    /**
    *   - parameter with: A string
    */
    func bar(with string: String) {}
}
```

## [#2 Using auto closures](https://twitter.com/johnsundell/status/822097067648700418)

👍 Finding more and more uses for auto closures in Swift. Can enable some pretty nice APIs:

```swift
extension Dictionary {
    mutating func value(for key: Key, orAdd valueClosure: @autoclosure () -> Value) -> Value {
        if let value = self[key] {
            return value
        }
        
        let value = valueClosure()
        self[key] = value
        return value
    }
}
```

## [#1 Namespacing with nested types](https://twitter.com/johnsundell/status/821828733107634176)

🚀 I’ve started to become a really big fan of nested types in Swift. Love the additional namespacing it gives you!

```swift
public struct Map {
    public struct Model {
        public let size: Size
        public let theme: Theme
        public var terrain: [Position : Terrain.Model]
        public var units: [Position : Unit.Model]
        public var buildings: [Position : Building.Model]
    }
    
    public enum Direction {
        case up
        case right
        case down
        case left
    }
    
    public struct Position {
        public var x: Int
        public var y: Int
    }
    
    public enum Size: String {
        case small = "S"
        case medium = "M"
        case large = "L"
        case extraLarge = "XL"
    }
}
```
