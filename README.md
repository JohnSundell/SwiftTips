# SwiftTips

Here I've gathered all the Swift tips & tricks that I've shared on Twitter.

## [#X Chaining optionals with map() and flatMap()](https://twitter.com/johnsundell/status/864130284140318720)

Using `map()` and `flatMap()` on optionals you can chain multiple operations without having to use lengthy if lets or guards:

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

## [#X Using self-executing closures for lazy properties](https://twitter.com/johnsundell/status/863073311718338561)

Using self-executing closures is a great way to encapsulate lazy property initialization:

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

## [#X Speeding up Swift package tests](https://twitter.com/johnsundell/status/862721700584189953)

You can speed up your Swift package tests using the `--parallel` flag. For [Marathon](https://github.com/johnsundell/marathon), the tests execute 3 times faster that way!

```
swift test --parallel
```

## [#X Avoiding mocking UserDefaults](https://twitter.com/johnsundell/status/855713943809032192)

Struggling with mocking `UserDefaults` in a test? The good news is: you don't need mocking - just create a real instance:

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

## [#X Using variadic parameters](https://twitter.com/johnsundell/status/854365916716572672)

Using variadic parameters in Swift, you can create some really nice APIs that take a list of objects without having to use an array:

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

## [#X Referring to enum cases with associated values as closures](https://twitter.com/johnsundell/status/848951678288228352)

Just like you can refer to a Swift function as a closure, you can do the same thing with enum cases with associated values:

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

## [#X Using the === operator to compare objects by instance](https://twitter.com/johnsundell/status/847468284198797313)

The `===` operator lets you check if two objects are the same instance. Very useful when verifying that an array contains an instance in a test:

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

## [#X Calling initializers with dot syntax and passing them as closures](https://twitter.com/johnsundell/status/845560409126027264)

Cool thing about Swift initializers: you can call them using dot syntax and pass them as closures! Perfect for mocking dates in tests.

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

## [#X Structuring UI tests as extensions on XCUIApplication](https://twitter.com/johnsundell/status/844945775088013312)

Most of my UI testing logic is now categories on `XCUIApplication`. Makes the test cases really easy to read:

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

## [#X Avoiding default cases in switch statements](https://twitter.com/johnsundell/status/844608407718051847)

It’s a good idea to avoid “default” cases when switching on Swift enums - it’ll “force you” to update your logic when a new case is added:

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

## [#X Using the guard statement in many different scopes](https://twitter.com/johnsundell/status/844262618630148098)

It's really cool that you can use Swift's 'guard' statement to exit out of pretty much any scope, not only return from functions:

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

## [#X Passing functions & operators as closures](https://twitter.com/johnsundell/status/843771235897098240)

Love how you can pass functions & operators as closures in Swift. For example, it makes the syntax for sorting arrays really nice!

```swift
let array = [3, 9, 1, 4, 6, 2]
let sorted = array.sorted(by: <)
```

## [#X Using #function for UserDefaults key consistency](https://twitter.com/johnsundell/status/842058888371421185)

Here's a neat little trick I use to get UserDefault key consistency in Swift (#function expands to the property name in getters/setters). Just remember to write a good suite of tests that'll guard you against bugs when changing property names.

```swift
extension UserDefaults {
    var onboardingCompleted: Bool {
        get { return bool(forKey: #function) }
        set { set(newValue, forKey: #function) }
    }
}
```

## [#X Using a name already taken by the standard library](https://twitter.com/johnsundell/status/839209426015891456)

Want to use a name already taken by the standard library for a nested type? No problem - just use `Swift.` to disambiguate:

```swift
extension Command {
    enum Error: Swift.Error {
        case missing
        case invalid(String)
    }
}
```

## [#X Using Wrap to implement Equatable](https://twitter.com/johnsundell/status/835860744176553984)

Playing around with using [Wrap](https://github.com/johnsundell/wrap) to implement `Equatable` for any type, primarily for testing:

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

