# Swift tips & tricks ⚡️

One of the things I really love about Swift is how I keep finding interesting ways to use it in various situations, and when I do - I usually share them on [Twitter](https://twitter.com/johnsundell). Here's a collection of all the tips & tricks that I've shared so far. Each entry has a link to the original tweet, if you want to respond with some feedback or question, which is always super welcome! 🚀

I also write a weekly blog about Swift development at [swiftbysundell.com](https://www.swiftbysundell.com), where you can also find [my podcast](https://www.swiftbysundell.com/podcast) on which me + guests answer questions from the community! 😀

## Table of contents

[#79 Struct convenience initializers](https://github.com/johnsundell/swifttips#79-struct-convenience-initializers)  
[#78 Usages of throwing functions](https://github.com/johnsundell/swifttips#78-usages-of-throwing-functions)  
[#77 Nested generic types](https://github.com/johnsundell/swifttips#77-nested-generic-types)  
[#76 Equatable & Hashable structures](https://github.com/johnsundell/swifttips#76-equatable-hashable-structures)  
[#75 Conditional conformances](https://github.com/johnsundell/swifttips#75-conditional-conformances)  
[#74 Generic type aliases](https://github.com/johnsundell/swifttips#74-generic-type-aliases)  
[#73 Parsing command line arguments using UserDefaults](https://github.com/johnsundell/swifttips#73-parsing-command-line-arguments-using-userdefaults)  
[#72 Using the & operator](https://github.com/johnsundell/swifttips#72-using-the--operator)  
[#71 Capturing multiple values in mocks](https://github.com/johnsundell/swifttips#71-capturing-multiple-values-in-mocks)  
[#70 Reducing the need for mocks](https://github.com/johnsundell/swifttips#70-reducing-the-need-for-mocks)  
[#69 Using "then" as an external parameter label for closures](https://github.com/johnsundell/swifttips#69-using-then-as-an-external-parameter-label-for-closures)  
[#68 Combining lazily evaluated sequences with the builder pattern](https://github.com/johnsundell/swifttips#68-combining-lazily-evaluated-sequences-with-the-builder-pattern)  
[#67 Faster & more stable UI tests](https://github.com/johnsundell/swifttips#67-faster--more-stable-ui-tests)  
[#66 Accessing the clipboard from a Swift script](https://github.com/johnsundell/swifttips#66-accessing-the-clipboard-from-a-swift-script)  
[#65 Using tuples for view state](https://github.com/johnsundell/swifttips#65-using-tuples-for-view-state)  
[#64 Throwing tests and LocalizedError](https://github.com/johnsundell/swifttips#64-throwing-tests-and-localizederror)  
[#63 The difference between static and class properties](https://github.com/johnsundell/swifttips#63-the-difference-between-static-and-class-properties)  
[#62 Creating extensions with static factory methods](https://github.com/johnsundell/swifttips#62-creating-extensions-with-static-factory-methods)  
[#61 Child view controller auto-resizing](https://github.com/johnsundell/swifttips#61-child-view-controller-auto-resizing)  
[#60 Using zip](https://github.com/johnsundell/swifttips#60-using-zip)  
[#59 Defining custom option sets](https://github.com/johnsundell/swifttips#59-defining-custom-option-sets)  
[#58 Using the where clause with associated types](https://github.com/johnsundell/swifttips#58-using-the-where-clause-with-associated-types)  
[#57 Using first class functions when iterating over a dictionary](https://github.com/johnsundell/swifttips#57-using-first-class-functions-when-iterating-over-a-dictionary)  
[#56 Calling instance methods as static functions](https://github.com/johnsundell/swifttips#56-calling-instance-methods-as-static-functions)  
[#55 Dropping suffixes from method names to support multiple arguments](https://github.com/johnsundell/swifttips#55-dropping-suffixes-from-method-names-to-support-multiple-arguments)  
[#54 Constraining protocols to classes to ensure mutability](https://github.com/johnsundell/swifttips#54-constraining-protocols-to-classes-to-ensure-mutability)  
[#53 String-based enums in string interpolation](https://github.com/johnsundell/swifttips#53-string-based-enums-in-string-interpolation)  
[#52 Expressively comparing a value with a list of candidates](https://github.com/johnsundell/swifttips#52-expressively-comparing-a-value-with-a-list-of-candidates)  
[#51 UIView bounds and transforms](https://github.com/johnsundell/swifttips#51-uiview-bounds-and-transforms)  
[#50 UIKit default arguments](https://github.com/johnsundell/swifttips#50-uikit-default-arguments)  
[#49 Avoiding Massive View Controllers](https://github.com/johnsundell/swifttips#49-avoiding-massive-view-controllers)  
[#48 Extending optionals](https://github.com/johnsundell/swifttips#48-extending-optionals)  
[#47 Using where with for-loops](https://github.com/johnsundell/swifttips#47-using-where-with-for-loops)   
[#46 Variable shadowing](https://github.com/JohnSundell/SwiftTips#46-variable-shadowing)   
[#45 Using dot syntax for static properties and initializers](https://github.com/JohnSundell/SwiftTips#45-using-dot-syntax-for-static-properties-and-initializers)   
[#44 Calling functions as closures with a tuple as parameters](https://github.com/JohnSundell/SwiftTips#44-calling-functions-as-closures-with-a-tuple-as-parameters)   
[#43 Enabling static dependency injection](https://github.com/JohnSundell/SwiftTips#43-enabling-static-dependency-injection)   
[#42 Type inference for lazy properties in Swift 4](https://github.com/JohnSundell/SwiftTips#42-type-inference-for-lazy-properties-in-swift-4)   
[#41 Converting Swift errors to NSError](https://github.com/JohnSundell/SwiftTips#41-converting-swift-errors-to-nserror)   
[#40 Making UIImage macOS compatible](https://github.com/JohnSundell/SwiftTips#40-making-uiimage-macos-compatible)   
[#39 Internally mutable protocol-oriented APIs](https://github.com/JohnSundell/SwiftTips#39-internally-mutable-protocol-oriented-apis)   
[#38 Switching on a set](https://github.com/JohnSundell/SwiftTips#38-switching-on-a-set)   
[#37 Adding the current locale to cache keys](https://github.com/JohnSundell/SwiftTips#37-adding-the-current-locale-to-cache-keys)   
[#36 Setting up tests to avoid retain cycles with weak references](https://github.com/JohnSundell/SwiftTips#36-setting-up-tests-to-avoid-retain-cycles-with-weak-references)   
[#35 Expressively matching a value against a list of candidates](https://github.com/JohnSundell/SwiftTips#35-expressively-matching-a-value-against-a-list-of-candidates)   
[#34 Organizing code using extensions](https://github.com/JohnSundell/SwiftTips#34-organizing-code-using-extensions)   
[#33 Using map to transform an optional into a Result type](https://github.com/JohnSundell/SwiftTips#33-using-map-to-transform-an-optional-into-a-result-type)   
[#32 Assigning to self in struct initializers](https://github.com/JohnSundell/SwiftTips#32-assigning-to-self-in-struct-initializers)   
[#31 Recursively calling closures as inline functions](https://github.com/JohnSundell/SwiftTips#31-recursively-calling-closures-as-inline-functions)   
[#30 Passing self to required Objective-C dependencies](https://github.com/JohnSundell/SwiftTips#30-passing-self-to-required-objective-c-dependencies)   
[#29 Making weak or lazy properties readonly](https://github.com/JohnSundell/SwiftTips#29-making-weak-or-lazy-properties-readonly)   
[#28 Defining static URLs using string literals](https://github.com/JohnSundell/SwiftTips#28-defining-static-urls-using-string-literals)   
[#27 Manipulating points, sizes and frames using math operators](https://github.com/JohnSundell/SwiftTips#27-manipulating-points-sizes-and-frames-using-math-operators)   
[#26 Using closure types in generic constraints](https://github.com/JohnSundell/SwiftTips#26-using-closure-types-in-generic-constraints)   
[#25 Using associated enum values to avoid state-specific optionals](https://github.com/JohnSundell/SwiftTips#25-using-associated-enum-values-to-avoid-state-specific-optionals)   
[#24 Using enums for async result types](https://github.com/JohnSundell/SwiftTips#24-using-enums-for-async-result-types)   
[#23 Working on async code in a playground](https://github.com/JohnSundell/SwiftTips#23-working-on-async-code-in-a-playground)   
[#22 Overriding self with a weak reference](https://github.com/JohnSundell/SwiftTips#22-overriding-self-with-a-weak-reference)   
[#21 Using DispatchWorkItem](https://github.com/JohnSundell/SwiftTips#21-using-dispatchworkitem)   
[#20 Combining a sequence of functions](https://github.com/JohnSundell/SwiftTips#20-combining-a-sequence-of-functions)   
[#19 Chaining optionals with map() and flatMap()](https://github.com/JohnSundell/SwiftTips#19-chaining-optionals-with-map-and-flatmap)   
[#18 Using self-executing closures for lazy properties](https://github.com/JohnSundell/SwiftTips#18-using-self-executing-closures-for-lazy-properties)   
[#17 Speeding up Swift package tests](https://github.com/JohnSundell/SwiftTips#17-speeding-up-swift-package-tests)   
[#16 Avoiding mocking UserDefaults](https://github.com/JohnSundell/SwiftTips#16-avoiding-mocking-userdefaults)   
[#15 Using variadic parameters](https://github.com/JohnSundell/SwiftTips#15-using-variadic-parameters)   
[#14 Referring to enum cases with associated values as closures](https://github.com/JohnSundell/SwiftTips#14-referring-to-enum-cases-with-associated-values-as-closures)   
[#13 Using the === operator to compare objects by instance](https://github.com/JohnSundell/SwiftTips#13-using-the--operator-to-compare-objects-by-instance)   
[#12 Calling initializers with dot syntax and passing them as closures](https://github.com/JohnSundell/SwiftTips#12-calling-initializers-with-dot-syntax-and-passing-them-as-closures)   
[#11 Structuring UI tests as extensions on XCUIApplication](https://github.com/JohnSundell/SwiftTips#11-structuring-ui-tests-as-extensions-on-xcuiapplication)   
[#10 Avoiding default cases in switch statements](https://github.com/JohnSundell/SwiftTips#10-avoiding-default-cases-in-switch-statements)   
[#9 Using the guard statement in many different scopes](https://github.com/JohnSundell/SwiftTips#9-using-the-guard-statement-in-many-different-scopes)   
[#8 Passing functions & operators as closures](https://github.com/JohnSundell/SwiftTips#8-passing-functions--operators-as-closures)   
[#7 Using #function for UserDefaults key consistency](https://github.com/JohnSundell/SwiftTips#7-using-function-for-userdefaults-key-consistency)   
[#6 Using a name already taken by the standard library](https://github.com/JohnSundell/SwiftTips#6-using-a-name-already-taken-by-the-standard-library)   
[#5 Using Wrap to implement Equatable](https://github.com/JohnSundell/SwiftTips#5-using-wrap-to-implement-equatable)   
[#4 Using typealiases to reduce the length of method signatures](https://github.com/JohnSundell/SwiftTips#4-using-typealiases-to-reduce-the-length-of-method-signatures)   
[#3 Referencing either external or internal parameter name when writing docs](https://github.com/JohnSundell/SwiftTips#3-referencing-either-external-or-internal-parameter-name-when-writing-docs)   
[#2 Using auto closures](https://github.com/JohnSundell/SwiftTips#2-using-auto-closures)   
[#1 Namespacing with nested types](https://github.com/JohnSundell/SwiftTips#1-namespacing-with-nested-types)

## [#79 Struct convenience initializers](https://twitter.com/johnsundell/status/989470243008458752)

❤️ I love to structure my code using extensions in Swift. One big benefit of doing so when it comes to struct initializers, is that defining a convenience initializer doesn't remove the default one the compiler generates - best of both worlds!

```swift
struct Article {
    let date: Date
    var title: String
    var text: String
    var comments: [Comment]
}

extension Article {
    init(title: String, text: String) {
        self.init(date: Date(), title: title, text: text, comments: [])
    }
}

let articleA = Article(title: "Best Cupcake Recipe", text: "...")

let articleB = Article(
    date: Date(),
    title: "Best Cupcake Recipe",
    text: "...",
    comments: [
        Comment(user: currentUser, text: "Yep, can confirm!")
    ]
)
```

## [#78 Usages of throwing functions](https://twitter.com/johnsundell/status/988713137854668800)

🏈 A big benefit of using throwing functions for synchronous Swift APIs is that the caller can decide whether they want to treat the return value as optional (`try?`) or required (`try`).

```swift
func loadFile(named name: String) throws -> File {
    guard let url = urlForFile(named: name) else {
        throw File.Error.missing
    }

    do {
        let data = try Data(contentsOf: url)
        return File(url: url, data: data)
    } catch {
        throw File.Error.invalidData(error)
    }
}

let requiredFile = try loadFile(named: "AppConfig.json")

let optionalFile = try? loadFile(named: "UserSettings.json")
```

## [#77 Nested generic types](https://twitter.com/johnsundell/status/983798689994035200)

🐝 Types that are nested in generics automatically inherit their parent's generic types - which is super useful when defining accessory types (for things like states or outcomes).

```swift
struct Task<Input, Output> {
    typealias Closure = (Input) throws -> Output

    let closure: Closure
}

extension Task {
    enum Result {
        case success(Output)
        case failure(Error)
    }
}
```

## [#76 Equatable & Hashable structures](https://twitter.com/johnsundell/status/981449931134259202)

🤖 Now that the Swift compiler automatically synthesizes Equatable & Hashable conformances for value types, it's easier than ever to setup model structures with nested types that are all `Equatable`/`Hashable`!

```swift
typealias Value = Hashable & Codable

struct User: Value {
    var name: String
    var age: Int
    var lastLoginDate: Date?
    var settings: Settings
}

extension User {
    struct Settings: Value {
        var itemsPerPage: Int
        var theme: Theme
    }
}

extension User.Settings {
    enum Theme: String, Value {
        case light
        case dark
    }
}
```

*[You can read more about using nested types in Swift here](https://www.swiftbysundell.com/posts/namespacing-swift-code-with-nested-types).*

## [#75 Conditional conformances](https://twitter.com/johnsundell/status/979682447544737792)

🎉 Swift 4.1 is here! One of the key features it brings is conditional conformances, which lets you have a type only conform to a protocol under certain constraints.

```swift
protocol UnboxTransformable {
    associatedtype RawValue

    static func transform(_ value: RawValue) throws -> Self?
}

extension Array: UnboxTransformable where Element: UnboxTransformable {
    typealias RawValue = [Element.RawValue]

    static func transform(_ value: RawValue) throws -> [Element]? {
        return try value.compactMap(Element.transform)
    }
}
```

*I also have [an article with lots of more info on conditional conformances here](https://www.swiftbysundell.com/posts/conditional-conformances-in-swift). Paul Hudson also has a great overview of [all Swift 4.1 features here](https://www.hackingwithswift.com/articles/50/whats-new-in-swift-4-1).*

## [#74 Generic type aliases](https://twitter.com/johnsundell/status/979059265238388739)

🕵️‍♀️ A cool thing about Swift type aliases is that they can be generic! Combine that with tuples and you can easily define simple generic types.

```swift
typealias Pair<T> = (T, T)

extension Game {
    func calculateScore(for players: Pair<Player>) -> Int {
        ...
    }
}
```

*You can read more about using tuples as lightweight types [here](https://www.swiftbysundell.com/posts/using-tuples-as-lightweight-types-in-swift).*

## [#73 Parsing command line arguments using UserDefaults](https://twitter.com/johnsundell/status/973273054699773953)

☑️ A really cool "hidden" feature of UserDefaults is that it contains any arguments that were passed to the app at launch!

Super useful both in Swift command line tools & scripts, but also to temporarily override a value when debugging iOS apps.

```swift
let defaults = UserDefaults.standard
let query = defaults.string(forKey: "query")
let resultCount = defaults.integer(forKey: "results")
```

## [#72 Using the & operator](https://twitter.com/johnsundell/status/972134523612925952)

👏 Swift's `&` operator is awesome! Not only can you use it to compose protocols, you can compose other types too! Very useful if you want to hide concrete types & implementation details.

```swift
protocol LoadableFromURL {
    func load(from url: URL)
}

class ContentViewController: UIViewController, LoadableFromURL {
    func load(from url: URL) {
        ...
    }
}

class ViewControllerFactory {
    func makeContentViewController() -> UIViewController & LoadableFromURL {
        return ContentViewController()
    }
}
```

## [#71 Capturing multiple values in mocks](https://twitter.com/johnsundell/status/971675443307917314)

🤗 When capturing values in mocks, using an array (instead of just a single value) makes it easy to verify that only a certain number of values were passed.

Perfect for protecting against "over-calling" something.

```swift
class UserManagerTests: XCTestCase {
    func testObserversCalledWhenUserFirstLogsIn() {
        let manager = UserManager()

        let observer = ObserverMock()
        manager.addObserver(observer)

        // First login, observers should be notified
        let user = User(id: 123, name: "John")
        manager.userDidLogin(user)
        XCTAssertEqual(observer.users, [user])

        // If the same user logs in again, observers shouldn't be notified
        manager.userDidLogin(user)
        XCTAssertEqual(observer.users, [user])
    }
}

private extension UserManagerTests {
    class ObserverMock: UserManagerObserver {
        private(set) var users = [User]()

        func userDidChange(to user: User) {
            users.append(user)
        }
    }
}
```

## [#70 Reducing the need for mocks](https://twitter.com/johnsundell/status/966652150247055360)

👋 When writing tests, you don't always need to create mocks - you can create stubs using real instances of things like errors, URLs & UserDefaults.

Here's how to do that for some common tasks/object types in Swift:

```swift
// Create errors using NSError (#function can be used to reference the name of the test)
let error = NSError(domain: #function, code: 1, userInfo: nil)

// Create non-optional URLs using file paths
let url = URL(fileURLWithPath: "Some/URL")

// Reference the test bundle using Bundle(for:)
let bundle = Bundle(for: type(of: self))

// Create an explicit UserDefaults object (instead of having to use a mock)
let userDefaults = UserDefaults(suiteName: #function)

// Create queues to control/await concurrent operations
let queue = DispatchQueue(label: #function)
```

*For when you actually do need mocking, check out ["Mocking in Swift"](https://www.swiftbysundell.com/posts/mocking-in-swift).*

## [#69 Using "then" as an external parameter label for closures](https://twitter.com/johnsundell/status/965880323614695424)

⏱ I've started using "then" as an external parameter label for completion handlers. Makes the call site read really nicely (Because I do ❤️ conversational API design) regardless of whether trailing closure syntax is used or not.

```swift
protocol DataLoader {
    // Adding type aliases to protocols can be a great way to
    // reduce verbosity for parameter types.
    typealias Handler = (Result<Data>) -> Void
    associatedtype Endpoint

    func loadData(from endpoint: Endpoint, then handler: @escaping Handler)
}

loader.loadData(from: .messages) { result in
    ...
}

loader.loadData(from: .messages, then: { result in
    ...
})
```

## [#68 Combining lazily evaluated sequences with the builder pattern](https://twitter.com/johnsundell/status/964515011765899266)

😴 Combining lazily evaluated sequences with builder pattern-like properties can lead to some pretty sweet APIs for configurable sequences in Swift.

Also useful for queries & other things you "build up" and then execute.

```swift
// Extension adding builder pattern-like properties that return
// a new sequence value with the given configuration applied
extension FileSequence {
    var recursive: FileSequence {
        var sequence = self
        sequence.isRecursive = true
        return sequence
    }

    var includingHidden: FileSequence {
        var sequence = self
        sequence.includeHidden = true
        return sequence
    }
}

// BEFORE

let files = folder.makeFileSequence(recursive: true, includeHidden: true)

// AFTER

let files = folder.files.recursive.includingHidden
```

Want an intro to lazy sequences? Check out *["Swift sequences: The art of being lazy"](https://www.swiftbysundell.com/posts/swift-sequences-the-art-of-being-lazy)*.

## [#67 Faster & more stable UI tests](https://twitter.com/johnsundell/status/960578271439138816)

My top 3 tips for faster & more stable UI tests:

📱 Reset the app's state at the beginning of every test.

🆔 Use accessibility identifiers instead of UI strings.

⏱ Use expectations instead of waiting time.

```swift
func testOpeningArticle() {
    // Launch the app with an argument that tells it to reset its state
    let app = XCUIApplication()
    app.launchArguments.append("--uitesting")
    app.launch()
    
    // Check that the app is displaying an activity indicator
    let activityIndicator = app.activityIndicator.element
    XCTAssertTrue(activityIndicator.exists)
    
    // Wait for the loading indicator to disappear = content is ready
    expectation(for: NSPredicate(format: "exists == 0"),
                evaluatedWith: activityIndicator)
                
    // Use a generous timeout in case the network is slow
    waitForExpectations(timeout: 10)
    
    // Tap the cell for the first article
    app.tables.cells["Article.0"].tap()
    
    // Assert that a label with the accessibility identifier "Article.Title" exists
    let label = app.staticTexts["Article.Title"]
    XCTAssertTrue(label.exists)
}
```

## [#66 Accessing the clipboard from a Swift script](https://twitter.com/johnsundell/status/959875189961056256)

📋 It's super easy to access the contents of the clipboard from a Swift script. A big benefit of Swift scripting is being able to use Cocoa's powerful APIs for Mac apps.

```swift
import Cocoa

let clipboard = NSPasteboard.general.string(forType: .string)
```

## [#65 Using tuples for view state](https://twitter.com/johnsundell/status/958374853555511296)

🎯 Using Swift tuples for view state can be a super nice way to group multiple properties together and render them reactively using the layout system.

By using a tuple we don't have to either introduce a new type or make our view model-aware.

```swift
class TextView: UIView {
    var state: (title: String?, text: String?) {
        // By telling UIKit that our view needs layout and binding our
        // state in layoutSubviews, we can react to state changes without
        // doing unnecessary layout work.
        didSet { setNeedsLayout() }
    }

    private let titleLabel = UILabel()
    private let textLabel = UILabel()

    override func layoutSubviews() {
        // Changing the labels changes their intrinsic size, do so before you call super's layoutSubviews()
        
        titleLabel.text = state.title
        textLabel.text = state.text

        // Perform default layout
        super.layoutSubviews()

        // Do your custom layout steps (if any)
        ...
    }
}
```

## [#64 Throwing tests and LocalizedError](https://twitter.com/johnsundell/status/956630510628999171)

⚾️ Swift tests can throw, which is super useful in order to avoid complicated logic or force unwrapping. By making errors conform to `LocalizedError`, you can also get a nice error message in Xcode if there's a failure.

```swift
class ImageCacheTests: XCTestCase {
    func testCachingAndLoadingImage() throws {
        let bundle = Bundle(for: type(of: self))
        let cache = ImageCache(bundle: bundle)
        
        // Bonus tip: You can easily load images from your test
        // bundle using this UIImage initializer
        let image = try require(UIImage(named: "sample", in: bundle, compatibleWith: nil))
        try cache.cache(image, forKey: "key")
        
        let cachedImage = try cache.image(forKey: "key")
        XCTAssertEqual(image, cachedImage)
    }
}

enum ImageCacheError {
    case emptyKey
    case dataConversionFailed
}

// When using throwing tests, making your errors conform to
// LocalizedError will render a much nicer error message in
// Xcode (per default only the error code is shown).
extension ImageCacheError: LocalizedError {
    var errorDescription: String? {
        switch self {
        case .emptyKey:
            return "An empty key was given"
        case .dataConversionFailed:
            return "Failed to convert the given image to Data"
        }
    }
}
```

For more information, and the implementation of the `require` method used above, check out *["Avoiding force unwrapping in Swift unit tests"](https://www.swiftbysundell.com/posts/avoiding-force-unwrapping-in-swift-unit-tests)*.

## [#63 The difference between static and class properties](https://twitter.com/johnsundell/status/956277711294656512)

✍️ Unlike `static` properties, `class` properties can be overridden by subclasses (however, they can't be stored, only computed).

```swift
class TableViewCell: UITableViewCell {
    class var preferredHeight: CGFloat { return 60 }
}

class TallTableViewCell: TableViewCell {
    override class var preferredHeight: CGFloat { return 100 }
}
```

## [#62 Creating extensions with static factory methods](https://twitter.com/johnsundell/status/955832453238751232)

👨‍🎨 Creating extensions with static factory methods can be a great alternative to subclassing in Swift, especially for things like setting up UIViews, CALayers or other kinds of styling.

It also lets you remove a lot of styling & setup from your view controllers.

```swift
extension UILabel {
    static func makeForTitle() -> UILabel {
        let label = UILabel()
        label.font = .boldSystemFont(ofSize: 24)
        label.textColor = .darkGray
        label.adjustsFontSizeToFitWidth = true
        label.minimumScaleFactor = 0.75
        return label
    }

    static func makeForText() -> UILabel {
        let label = UILabel()
        label.font = .systemFont(ofSize: 16)
        label.textColor = .black
        label.numberOfLines = 0
        return label
    }
}

class ArticleViewController: UIViewController {
    lazy var titleLabel = UILabel.makeForTitle()
    lazy var textLabel = UILabel.makeForText()
}
```

## [#61 Child view controller auto-resizing](https://twitter.com/johnsundell/status/953999892309045249)

🧒 An awesome thing about child view controllers is that they're automatically resized to match their parent, making them a super nice solution for things like loading & error views.

```swift
class ListViewController: UIViewController {
    func loadItems() {
        let loadingViewController = LoadingViewController()
        add(loadingViewController)

        dataLoader.loadItems { [weak self] result in
            loadingViewController.remove()
            self?.handle(result)
        }
    }
}
```

For more about child view controller (including the `add` and `remove` methods used above), check out *["Using child view controllers as plugins in Swift"](https://www.swiftbysundell.com/posts/using-child-view-controllers-as-plugins-in-swift)*.

## [#60 Using zip](https://twitter.com/johnsundell/status/953302410209976320)

🤐 Using the zip function in Swift you can easily combine two sequences. Super useful when using two sequences to do some work, since zip takes care of all the bounds-checking.

```swift
func render(titles: [String]) {
    for (label, text) in zip(titleLabels, titles) {
        print(text)
        label.text = text
    }
}
```

## [#59 Defining custom option sets](https://twitter.com/johnsundell/status/951830680522117120)

🎛 The awesome thing about option sets in Swift is that they can automatically either be passed as a single member or as a set. Even cooler is that you can easily define your own option sets as well, perfect for options and other non-exclusive values.

```swift
// Option sets are awesome, because you can easily pass them
// both using dot syntax and array literal syntax, like when
// using the UIView animation API:
UIView.animate(withDuration: 0.3,
               delay: 0,
               options: .allowUserInteraction,
               animations: animations)

UIView.animate(withDuration: 0.3,
               delay: 0,
               options: [.allowUserInteraction, .layoutSubviews],
               animations: animations)

// The cool thing is that you can easily define your own option
// sets as well, by defining a struct that has an Int rawValue,
// that will be used as a bit mask.
extension Cache {
    struct Options: OptionSet {
        static let saveToDisk = Options(rawValue: 1)
        static let clearOnMemoryWarning = Options(rawValue: 1 << 1)
        static let clearDaily = Options(rawValue: 1 << 2)

        let rawValue: Int
    }
}

// We can now use Cache.Options just like UIViewAnimationOptions:
Cache(options: .saveToDisk)
Cache(options: [.saveToDisk, .clearDaily])
```

## [#58 Using the where clause with associated types](https://twitter.com/johnsundell/status/950810357492256768)

🙌 Using the `where` clause when designing protocol-oriented APIs in Swift can let your implementations (or others' if it's open source) have a lot more freedom, especially when it comes to collections.

*See ["Using generic type constraints in Swift 4"](https://www.swiftbysundell.com/posts/using-generic-type-constraints-in-swift-4) for more info.*

```swift
public protocol PathFinderMap {
    associatedtype Node
    // Using the 'where' clause for associated types, we can
    // ensure that a type meets certain requirements (in this
    // case that it's a sequence with Node elements).
    associatedtype NodeSequence: Sequence where NodeSequence.Element == Node

    // Instead of using a concrete type (like [Node]) here, we
    // give implementors of this protocol more freedom while
    // still meeting our requirements. For example, one
    // implementation might use Set<Node>.
    func neighbors(of node: Node) -> NodeSequence
}
```

## [#57 Using first class functions when iterating over a dictionary](https://twitter.com/johnsundell/status/950455451799445504)

👨‍🍳 Combine first class functions in Swift with the fact that Dictionary elements are (Key, Value) tuples and you can build yourself some pretty awesome functional chains when iterating over a Dictionary.

```swift
func makeActor(at coordinate: Coordinate, for building: Building) -> Actor {
    let actor = Actor()
    actor.position = coordinate.point
    actor.animation = building.animation
    return actor
}

func render(_ buildings: [Coordinate : Building]) {
    buildings.map(makeActor).forEach(add)
}
```

## [#56 Calling instance methods as static functions](https://twitter.com/johnsundell/status/949317918730440704)

😎 In Swift, you can call any instance method as a static function and it will return a closure representing that method. This is how running tests using SPM on Linux works.

*More about this topic in my blog post ["First class functions in Swift"](https://www.swiftbysundell.com/posts/first-class-functions-in-swift).*

```swift
// This produces a '() -> Void' closure which is a reference to the
// given view's 'removeFromSuperview' method.
let closure = UIView.removeFromSuperview(view)

// We can now call it just like we would any other closure, and it
// will run 'view.removeFromSuperview()'
closure()

// This is how running tests using the Swift Package Manager on Linux
// works, you return your test functions as closures:
extension UserManagerTests {
    static var allTests = [
        ("testLoggingIn", testLoggingIn),
        ("testLoggingOut", testLoggingOut),
        ("testUserPermissions", testUserPermissions)
    ]
}
```

## [#55 Dropping suffixes from method names to support multiple arguments](https://twitter.com/johnsundell/status/948513364015288320)

👏 One really nice benefit of dropping suffixes from method names (and just using verbs, when possible) is that it becomes super easy to support both single and multiple arguments, and it works really well semantically.

```swift
extension UIView {
    func add(_ subviews: UIView...) {
        subviews.forEach(addSubview)
    }
}

view.add(button)
view.add(label)

// By dropping the "Subview" suffix from the method name, both
// single and multiple arguments work really well semantically.
view.add(button, label)
```

## [#54 Constraining protocols to classes to ensure mutability](https://twitter.com/johnsundell/status/948267767744122881)

👽 Using the `AnyObject` (or `class`) constraint on protocols is not only useful when defining delegates (or other weak references), but also when you always want instances to be mutable without copying.

```swift
// By constraining a protocol with 'AnyObject' it can only be adopted
// by classes, which means all instances will always be mutable, and
// that it's the original instance (not a copy) that will be mutated.
protocol DataContainer: AnyObject {
    var data: Data? { get set }
}

class UserSettingsManager {
    private var settings: Settings
    private let dataContainer: DataContainer

    // Since DataContainer is a protocol, we an easily mock it in
    // tests if we use dependency injection
    init(settings: Settings, dataContainer: DataContainer) {
        self.settings = settings
        self.dataContainer = dataContainer
    }

    func saveSettings() throws {
        let data = try settings.serialize()

        // We can now assign properties on an instance of our protocol
        // because the compiler knows it's always going to be a class
        dataContainer.data = data
    }
}
```

## [#53 String-based enums in string interpolation](https://twitter.com/johnsundell/status/945686980125437954)

🍣 Even if you define a custom raw value for a string-based enum in Swift, the full case name will be used in string interpolation.

Super useful when using separate raw values for JSON, while still wanting to use the full case name in other contexts.

```swift
extension Building {
    // This enum has custom raw values that are used when decoding
    // a value, for example from JSON.
    enum Kind: String {
        case castle = "C"
        case town = "T"
        case barracks = "B"
        case goldMine = "G"
        case camp = "CA"
        case blacksmith = "BL"
    }

    var animation: Animation {
        return Animation(
            // When used in string interpolation, the full case name is still used.
            // For 'castle' this will be 'buildings/castle'.
            name: "buildings/\(kind)",
            frameCount: frameCount,
            frameDuration: frameDuration
        )
    }
}
```

## [#52 Expressively comparing a value with a list of candidates](https://twitter.com/johnsundell/status/943510426586959873)

👨‍🔬 Continuing to experiment with expressive ways of comparing a value with a list of candidates in Swift. Adding an extension on Equatable is probably my favorite approach so far.

```swift
extension Equatable {
    func isAny(of candidates: Self...) -> Bool {
        return candidates.contains(self)
    }
}

let isHorizontal = direction.isAny(of: .left, .right)
```

*See [tip #35](https://github.com/JohnSundell/SwiftTips#35-expressively-matching-a-value-against-a-list-of-candidates) for my previous experiment.*

## [#51 UIView bounds and transforms](https://twitter.com/johnsundell/status/943156901428256770)

📐 A really interesting side-effect of a `UIView`'s `bounds` being its rect within its own coordinate system is that transforms don't affect it at all. That's why it's usually a better fit than `frame` when doing layout calculations of subviews.

```swift
let view = UIView()
view.frame.size = CGSize(width: 100, height: 100)
view.transform = CGAffineTransform(scaleX: 2, y: 2)

print(view.frame) // (-50.0, -50.0, 200.0, 200.0)
print(view.bounds) // (0.0, 0.0, 100.0, 100.0)
```

## [#50 UIKit default arguments](https://twitter.com/johnsundell/status/940330427855892480)

👏 It's awesome that many UIKit APIs with completion handlers and other optional parameters import into Swift with default arguments (even though they are written in Objective-C). Getting rid of all those nil arguments is so nice!

```swift
// BEFORE: All parameters are specified, just like in Objective-C

viewController.present(modalViewController, animated: true, completion: nil)

modalViewController.dismiss(animated: true, completion: nil)

viewController.transition(from: loadingViewController,
                          to: contentViewController,
                          duration: 0.3,
                          options: [],
                          animations: animations,
                          completion: nil)

// AFTER: Since many UIKit APIs with completion handlers and other
// optional parameters import into Swift with default arguments,
// we can make our calls shorter

viewController.present(modalViewController, animated: true)

modalViewController.dismiss(animated: true)

viewController.transition(from: loadingViewController,
                          to: contentViewController,
                          duration: 0.3,
                          animations: animations)
```

## [#49 Avoiding Massive View Controllers](https://twitter.com/johnsundell/status/938505299723505664)

✂️ Avoiding Massive View Controllers is all about finding the right levels of abstraction and splitting things up.

My personal rule of thumb is that as soon as I have 3 methods or properties that have the same prefix, I break them out into their own type.

```swift
// BEFORE

class LoginViewController: UIViewController {
    private lazy var signUpLabel = UILabel()
    private lazy var signUpImageView = UIImageView()
    private lazy var signUpButton = UIButton()
}

// AFTER

class LoginViewController: UIViewController {
    private lazy var signUpView = SignUpView()
}

class SignUpView: UIView {
    private lazy var label = UILabel()
    private lazy var imageView = UIImageView()
    private lazy var button = UIButton()
}
```

## [#48 Extending optionals](https://twitter.com/johnsundell/status/938137780760215553)

❤️ I love the fact that optionals are enums in Swift - it makes it so easy to extend them with convenience APIs for certain types. Especially useful when doing things like data validation on optional values.

```swift
func validateTextFields() -> Bool {
    guard !usernameTextField.text.isNilOrEmpty else {
        return false
    }

    ...

    return true
}

// Since all optionals are actual enum values in Swift, we can easily
// extend them for certain types, to add our own convenience APIs

extension Optional where Wrapped == String {
    var isNilOrEmpty: Bool {
        switch self {
        case let string?:
            return string.isEmpty
        case nil:
            return true
        }
    }
}

// Since strings are now Collections in Swift 4, you can even
// add this property to all optional collections:

extension Optional where Wrapped: Collection {
    var isNilOrEmpty: Bool {
        switch self {
        case let collection?:
            return collection.isEmpty
        case nil:
            return true
        }
    }
}
```

## [#47 Using where with for-loops](https://twitter.com/johnsundell/status/935910564865433601)

🗺 Using the `where` keyword can be a super nice way to quickly apply a filter in a `for`-loop in Swift. You can of course use `map`, `filter` and `forEach`, or `guard`, but for simple loops I think this is very expressive and nice.

```swift
func archiveMarkedPosts() {
    for post in posts where post.isMarked {
        archive(post)
    }
}

func healAllies() {
    for player in players where player.isAllied(to: currentPlayer) {
        player.heal()
    }
}
```

## [#46 Variable shadowing](https://twitter.com/johnsundell/status/931549161782169600)

👻 Variable shadowing can be super useful in Swift, especially when you want to create a local copy of a parameter value in order to use it as state within a closure.

```swift
init(repeatMode: RepeatMode, closure: @escaping () -> UpdateOutcome) {
    // Shadow the argument with a local, mutable copy
    var repeatMode = repeatMode
    
    self.closure = {
        // With shadowing, there's no risk of accidentially
        // referring to the immutable version
        switch repeatMode {
        case .forever:
            break
        case .times(let count):
            guard count > 0 else {
                return .finished
            }
            
            // We can now capture the mutable version and use
            // it for state in a closure
            repeatMode = .times(count - 1)
        }
        
        return closure()
    }
}
```

## [#45 Using dot syntax for static properties and initializers](https://twitter.com/johnsundell/status/931270709824884736)

✒️ Dot syntax is one of my favorite features of Swift. What's really cool is that it's not only for enums, any static method or property can be used with dot syntax - even initializers! Perfect for convenience APIs and default parameters.

```swift
public enum RepeatMode {
    case times(Int)
    case forever
}

public extension RepeatMode {
    static var never: RepeatMode {
        return .times(0)
    }

    static var once: RepeatMode {
        return .times(1)
    }
}

view.perform(animation, repeated: .once)

// To make default parameters more compact, you can even use init with dot syntax

class ImageLoader {
    init(cache: Cache = .init(), decoder: ImageDecoder = .init()) {
        ...
    }
}
```

## [#44 Calling functions as closures with a tuple as parameters](https://twitter.com/johnsundell/status/930103466294435840)

🚀 One really cool aspect of Swift having first class functions is that you can pass any function (or even initializer) as a closure, and even call it with a tuple containing its parameters!

```swift
// This function lets us treat any "normal" function or method as
// a closure and run it with a tuple that contains its parameters
func call<Input, Output>(_ function: (Input) -> Output, with input: Input) -> Output {
    return function(input)
}

class ViewFactory {
    func makeHeaderView() -> HeaderView {
        // We can now pass an initializer as a closure, and a tuple
        // containing its parameters
        return call(HeaderView.init, with: loadTextStyles())
    }
    
    private func loadTextStyles() -> (font: UIFont, color: UIColor) {
        return (theme.font, theme.textColor)
    }
}

class HeaderView {
    init(font: UIFont, textColor: UIColor) {
        ...
    }
}
```

## [#43 Enabling static dependency injection](https://twitter.com/johnsundell/status/928630015390027778)

💉 If you've been struggling to test code that uses static APIs, here's a technique you can use to enable static dependency injection without having to modify any call sites:

```swift
// Before: Almost impossible to test due to the use of singletons

class Analytics {
    static func log(_ event: Event) {
        Database.shared.save(event)
        
        let dictionary = event.serialize()
        NetworkManager.shared.post(dictionary, to: eventURL)
    }
}

// After: Much easier to test, since we can inject mocks as arguments

class Analytics {
    static func log(_ event: Event,
                    database: Database = .shared,
                    networkManager: NetworkManager = .shared) {
        database.save(event)
        
        let dictionary = event.serialize()
        networkManager.post(dictionary, to: eventURL)
    }
}
```

## [#42 Type inference for lazy properties in Swift 4](https://twitter.com/johnsundell/status/925826172738514945)

🎉 In Swift 4, type inference works for lazy properties and you don't need to explicitly refer to `self`!

```swift
// Swift 3

class PurchaseView: UIView {
    private lazy var buyButton: UIButton = self.makeBuyButton()
    
    private func makeBuyButton() -> UIButton {
        let button = UIButton()
        button.setTitle("Buy", for: .normal)
        button.setTitleColor(.blue, for: .normal)
        return button
    }
}

// Swift 4

class PurchaseView: UIView {
    private lazy var buyButton = makeBuyButton()
    
    private func makeBuyButton() -> UIButton {
        let button = UIButton()
        button.setTitle("Buy", for: .normal)
        button.setTitleColor(.blue, for: .normal)
        return button
    }
}
```

## [#41 Converting Swift errors to NSError](https://twitter.com/johnsundell/status/923221568175603712)

😎 You can turn any Swift `Error` into an `NSError`, which is super useful when pattern matching with a code 👍. Also, switching on optionals is pretty cool!

```swift
let task = urlSession.dataTask(with: url) { data, _, error in
    switch error {
    case .some(let error as NSError) where error.code == NSURLErrorNotConnectedToInternet:
        presenter.showOfflineView()
    case .some(let error):
        presenter.showGenericErrorView()
    case .none:
        presenter.renderContent(from: data)
    }
}

task.resume()
```

Also make sure to check out [Kostas Kremizas' tip](https://twitter.com/kostaskremizas/status/923228453784170497) about how you can pattern match directly against a member of `URLError`.

## [#40 Making UIImage macOS compatible](https://twitter.com/johnsundell/status/915593457082740736)

🖥 Here's an easy way to make iOS model code that uses `UIImage` macOS compatible - like me and [Gui Rambo](https://twitter.com/_inside) discussed on the [Swift by Sundell Podcast](https://swiftbysundell.com/podcast/7).

```swift
// Either put this in a separate file that you only include in your macOS target or wrap the code in #if os(macOS) / #endif

import Cocoa

// Step 1: Typealias UIImage to NSImage
typealias UIImage = NSImage

// Step 2: You might want to add these APIs that UIImage has but NSImage doesn't.
extension NSImage {
    var cgImage: CGImage? {
        var proposedRect = CGRect(origin: .zero, size: size)

        return cgImage(forProposedRect: &proposedRect,
                       context: nil,
                       hints: nil)
    }

    convenience init?(named name: String) {
        self.init(named: Name(name))
    }
}

// Step 3: Profit - you can now make your model code that uses UIImage cross-platform!
struct User {
    let name: String
    let profileImage: UIImage
}
```

## [#39 Internally mutable protocol-oriented APIs](https://twitter.com/johnsundell/status/914069005786341379)

🤖 You can easily define a protocol-oriented API that can only be mutated internally, by using an internal protocol that extends a public one.

```swift
// Declare a public protocol that acts as your immutable API
public protocol ModelHolder {
    associatedtype Model
    var model: Model { get }
}

// Declare an extended, internal protocol that provides a mutable API
internal protocol MutableModelHolder: ModelHolder {
    var model: Model { get set }
}

// You can now implement the requirements using 'public internal(set)'
public class UserHolder: MutableModelHolder {
    public internal(set) var model: User

    internal init(model: User) {
        self.model = model
    }
}
```

## [#38 Switching on a set](https://twitter.com/johnsundell/status/906097785883242496)

🎛 You can switch on a set using array literals as cases in Swift! Can be really useful to avoid many `if`/`else if` statements.

```swift
class RoadTile: Tile {
    var connectedDirections = Set<Direction>()

    func render() {
        switch connectedDirections {
        case [.up, .down]:
            image = UIImage(named: "road-vertical")
        case [.left, .right]:
            image = UIImage(named: "road-horizontal")
        default:
            image = UIImage(named: "road")
        }
    }
}
```

## [#37 Adding the current locale to cache keys](https://twitter.com/johnsundell/status/900290163376607232)

🌍 When caching localized content in an app, it's a good idea to add the current locale to all keys, to prevent bugs when switching languages.

```swift
func cache(_ content: Content, forKey key: String) throws {
    let data = try wrap(content) as Data
    let key = localize(key: key)
    try storage.store(data, forKey: key)
}

func loadCachedContent(forKey key: String) -> Content? {
    let key = localize(key: key)
    let data = storage.loadData(forKey: key)
    return data.flatMap { try? unbox(data: $0) }
}

private func localize(key: String) -> String {
    return key + "-" + Bundle.main.preferredLocalizations[0]
}
```

## [#36 Setting up tests to avoid retain cycles with weak references](https://twitter.com/johnsundell/status/899982180776017920)

🚳 Here's an easy way to setup a test to avoid accidental retain cycles with object relationships (like weak delegates & observers) in Swift:

```swift
func testDelegateNotRetained() {
    // Assign the delegate (weak) and also retain it using a local var
    var delegate: Delegate? = DelegateMock()
    controller.delegate = delegate
    XCTAssertNotNil(controller.delegate)
    
    // Release the local var, which should also release the weak reference
    delegate = nil
    XCTAssertNil(controller.delegate)
}
```

## [#35 Expressively matching a value against a list of candidates](https://twitter.com/johnsundell/status/899745079987982338)

👨‍🔬 Playing around with an expressive way to check if a value matches any of a list of candidates in Swift:

```swift
// Instead of multiple conditions like this:

if string == "One" || string == "Two" || string == "Three" {

}

// You can now do:

if string == any(of: "One", "Two", "Three") {

}
```

*You can find a [gist with the implementation here](https://gist.github.com/JohnSundell/1956ce36b9303eb4bf912da0de9e2844).*

## [#34 Organizing code using extensions](https://twitter.com/johnsundell/status/897186531592556545)

👪 APIs in a Swift extension automatically inherit its access control level, making it a neat way to organize public, internal & private APIs.

```swift
public extension Animation {
    init(textureNamed textureName: String) {
        frames = [Texture(name: textureName)]
    }
    
    init(texturesNamed textureNames: [String], frameDuration: TimeInterval = 1) {
        frames = textureNames.map(Texture.init)
        self.frameDuration = frameDuration
    }
    
    init(image: Image) {
        frames = [Texture(image: image)]
    }
}

internal extension Animation {
    func loadFrameImages() -> [Image] {
        return frames.map { $0.loadImageIfNeeded() }
    }
}
```

## [#33 Using map to transform an optional into a Result type](https://twitter.com/johnsundell/status/896317661302444033)

🗺 Using `map` you can transform an optional value into an optional `Result` type by simply passing in the enum case.

```swift
enum Result<Value> {
    case value(Value)
    case error(Error)
}

class Promise<Value> {
    private var result: Result<Value>?
    
    init(value: Value? = nil) {
        result = value.map(Result.value)
    }
}
```

## [#32 Assigning to self in struct initializers](https://twitter.com/johnsundell/status/896024128330891264)

👌 It's so nice that you can assign directly to `self` in `struct` initializers in Swift. Very useful when adding conformance to protocols.

```swift
extension Bool: AnswerConvertible {
    public init(input: String) throws {
        switch input.lowercased() {
        case "y", "yes", "👍":
            self = true
        default:
            self = false
        }
    }
}
```

## [#31 Recursively calling closures as inline functions](https://twitter.com/johnsundell/status/894580870786539520)

☎️ Defining Swift closures as inline functions enables you to recursively call them, which is super useful in things like custom sequences.

```swift
class Database {
    func records(matching query: Query) -> AnySequence<Record> {
        var recordIterator = loadRecords().makeIterator()
        
        func iterate() -> Record? {
            guard let nextRecord = recordIterator.next() else {
                return nil
            }
            
            guard nextRecord.matches(query) else {
                // Since the closure is an inline function, it can be recursively called,
                // in this case in order to advance to the next item.
                return iterate()
            }
            
            return nextRecord
        }
        
        // AnySequence/AnyIterator are part of the standard library and provide an easy way
        // to define custom sequences using closures.
        return AnySequence { AnyIterator(iterate) }
    }
}
```

*[Rob Napier](https://twitter.com/cocoaphony) points out that using the above might cause crashes if used on a large databaset, since Swift has no guaranteed [Tail Call](https://en.wikipedia.org/wiki/Tail_call) Optimization (TCO).*

*[Slava Pestov](https://twitter.com/slava_pestov) also points out that another benefit of inline functions vs closures is that they can have their own generic parameter list.*

## [#30 Passing self to required Objective-C dependencies](https://twitter.com/johnsundell/status/892751766227480576)

🏖 Using lazy properties in Swift, you can pass `self` to required Objective-C dependencies without having to use force-unwrapped optionals.

```swift
class DataLoader: NSObject {
    lazy var urlSession: URLSession = self.makeURLSession()
    
    private func makeURLSession() -> URLSession {
        return URLSession(configuration: .default, delegate: self, delegateQueue: .main)
    }
}

class Renderer {
    lazy var displayLink: CADisplayLink = self.makeDisplayLink()
    
    private func makeDisplayLink() -> CADisplayLink {
        return CADisplayLink(target: self, selector: #selector(screenDidRefresh))
    }
}
```

## [#29 Making weak or lazy properties readonly](https://twitter.com/johnsundell/status/890906366143078400)

👓 If you have a property in Swift that needs to be `weak` or `lazy`, you can still make it readonly by using `private(set)`.

```swift
class Node {
    private(set) weak var parent: Node?
    private(set) lazy var children = [Node]()

    func add(child: Node) {
        children.append(child)
        child.parent = self
    }
}
```

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
