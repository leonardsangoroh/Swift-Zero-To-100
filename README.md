# Introduction to Swift
Welcome to the "Introduction to Swift" repository! This repository aims to take you through the basics of Swift, Apple's programming language for iOS, macOS, watchOS, and tvOS development. <br>
Whether you're new to programming or an experienced developer, this guide will help you understand and get started with Swift.

# Contents
- [Constants and Variables](#constants-and-variables)
- [Strings](#strings)
- [Storing Whole Numbers](#storing-whole-numbers)
- [Arithmetic Operators](#arithmetic-operators)
- [Storing Decimal Numbers](#storing-decimal-numbers)
- [Booleans](#booleans)
- [Store Ordered Data in Arrays](#store-ordered-data-in-arrays)
- [Storing and Finding Data in Dictionaries](#storing-and-finding-data-in-dictionaries)
- [Sets](#using-sets-for-fast-data-lookup)
- [Creating and Using Enums](#creating-and-using-enums-(enumerations))
- [Using Type Annotations](#using-type-annotations)
- [if...else](#check-whether-condition-is-true-or-false)
- [switch...case](#using-switch-statements-to-check-multiple-conditions)
- [Using Ternary Conditional Operator](#using-the-ternary-conditional-operator-for-quick-tests)
- [Using a For Loop](#using-a-for-loop-to-repeat-work)
- [Using a While Loop](#using-a-while-loop-to-repeat-work)
- [Skipping Loop Item with Break and Continue](#skipping-loop-items-with-break-and-continue)
- [Functions](#reusing-code-with-functions)
- [Tuples](#tuples)
- [Customizing Parameter Labels](#customizing-parameter-labels)
- [Providing Default Values for Parameters](#providing-default-values-for-parameters)
- [Handling Errors](#handling-errors-in-functions)
- [Creating and Using Closures](#creating-and-using-closures)
- [Function Types](#function-types-(yes,-functions-have-types-similar-to-int,-double))
- [Passing Functions into Functions](#passing-functions-into-other-functions)
- [Passing a Closure into a function](#passing-a-closure-into-a-function)
- [Trailing Closure Syntax and Shorthand Syntax](#trailing-closure-syntax-and-shorthand-syntax)
- [Accepting Functions as Parameters](#accepting-functions-as-parameters)
- [Creating Structs](#creating-structs)
- [Compute Property Values Dynamically](#compute-property-values-dynamically)
- [Taking Action when a Property Changes](#taking-action-when-a-property-changes)
- [Creating a Custom Initializer](#creating-custom-initializers)
- [Access Control](#limit-access-to-internal-data-using-access-control)
- [Static Properties and Methods](#static-properties-and-methods)
- [Creating Classes](#creating-classes)
- [Inheriting from a Class](#inheriting-from-a-class)
- [Adding Initializers for Classes](#adding-initializers-for-classes)
- [Copying Classes](#copying-classes)
- [De-initializing a Class](#de-initializing-a-class)
- [Working with Variables Inside Classes](#working-with-variables-inside-classes)
- [Protocols and Extensions](#protocols-and-extensions)
- [Protocol Extensions](#protocol-extensions)
- [Protocol-Oriented Programming](#protocol-oriented-programming)
- [Optionals](#optionals)
- [Nil Coalescing](#nil-coalescing)
- [Optional Chaining](#optional-chaining)
- [Optional try](#optional-try)
- [Failable Initializers](#failable-initializers)
- [Typecasting](#typecasting)

## Constants and Variables
- Variable: It's value can vary <br>
- It's good to give a variable a descriptive name <br>
`var greeting = "Jambo" `

- One can change a variable's value over time <br>
```Swift
    greeting = "Bonjour"
    greeting = "Hello"
```


- Constant: Use a constant when the value assigned will not change <br>
`let pi = 3.142`

## Strings
- Strings: characters placed between two double quotes (Lee is a String) <br>
`let name = "Lee"`

- Double-quote in a String: place a \ before the double quote <br>
`let sentence = "This is a \"Stop\" sign"`

- Multi-line Strings: Use three sets of double quotes to create a multi-line string
```Swift
var sentence = """
    A day in
    the life of
    a software dev
    """
```

- Read String Length: .count
```Swift
    let nameLength = name.count
    print(nameLength)
```

- Convert String to Uppercase: .uppercased()
```Swift
    let upperCasedName = name.uppercased()
    print(upperCasedName)
```

- Check Prefix and Suffix
```Swift
    print(sentence.hasPrefix("A day"))
    print(sentence.hasSuffix("Dev"))
```
Swift is case sensitive; the first statement will print 'true' while the second will print 'false' <br>
'dev' is not same as 'Dev'

- Joinig Strings Together: using '+' operator
```Swift
    let fName = "Lee"
    let lName = "Sangoroh"
    let fullName = fName + "Leonard" + lName
```
- Joining Strings Together: Using String interpolation <br>
It's a better way since it's more efficient and you can pull in integers, decimals etc.
```Swift
    let name = "Leonard Sangoroh"
    let age = 23
    let message = "Hello I'm \(name) and I'm \(age) years old"
    print(message) // Hello I'm Leonard Sangoroh and I'm 23 years old
```

Perform calculations insider string interpolation
```Swift
    print("5 x 5 is \(5*5)")
```

## Storing Whole Numbers

- Integers: Can be positive or negative, and are whole numbers
```Swift
    //constant
    let DOB = 2001
    //variable
    var age = 23
```

- Break up numbers: Use underscores to break numbers up
```
    let bigHardToReadNumber = 1000000000
    let bigReadableNumber = 1_000_000_000
```

- Check whether and integer is a multiple of another integer
```Swift
    let number = 36
    print(number.isMultiple(of: 3))
```

## Arithmetic Operators
```Swift
    let score = 100
    let lowerScore = 100 - 10
    let higherScore = 100 + 10
    // addition assignment operator OR shorthand operator
    let highestScore += 20
    let doubledScore = score * 2
    let halfScore = score / 2
```

## Storing Decimal Numbers
```Swift
    let pi = 3.142
```
- Swift considers decimals and integers as different data types
- This means one can't add a decimal and an integer directly

## Booleans

- Store either true or false
```Swift
    let goodDogs = true
    let badDogs = false
```

- Not operator (!): flips a boolean value from true to false, or false to true
```Swift
    var isAuthenticated = true
    isAuthenticated = !isAuthenticated
    print(isAuthenticated) //prints false
```

- Toggle functionality: if you call toggle() on a boolean, it will flip a true value to false, and vice versa
```Swift
    var gameOver = false
    print(gameOver) //prints false

    gameOver.toggle()
    print(gameOver) //prints true
```

## Checkpoint 1
Your goal is to write a Swift playground that:
1. Creates a constant holding any temperature in Celsius.
2. Converts it to Fahrenheit by multiplying by 9, dividing by 5, then adding 32.
3. Prints the result for the user, showing both the Celsius and Fahrenheit values.

```Swift
    var tempCelsius = 24
    var tempFahrenheit = ((tempCelsius * 9) / 5) + 32
    print(tempFahrenheit) 
```

## Store Ordered Data in Arrays
Arrays can only store one data type at a time

```Swift
    var carModels = ["BMW", "Mercedez", "Toyota", "Mazda"]
    var numbers = [1,2,3,4,5,6,7,8,9]
    var temp = [22.3, 25.6, 12.4]
```

- Reading Values From Array
```Swift
    var fastestCar = carModels[0]
```

- Add Items To Array: Only if it was declared as a variable
```Swift
    carModels.append("Mobius")
```

- Declaring an Empty Array
```Swift
    var albums = Array<Stringt>()
    albums.append("African Giant")

    var numbers = [Int]()
    numbers.append(4)
```

- Count Number of Items in Array
```Swift
    var carCount = carModels.count
```

- Remove Items From Array
```Swift
    //remove specific item
    carModels.remove(at: 2)
    // remove all items
    carModels.removeAll()
```

- Check whether Array Contains an Item
```Swift
    if carModels.contains("Toyota") {
        print("Japan Made It")
    }
```

- Sort Items in an Array: Ascending Order <br>
NB: Returns a new array, while the original array remains unchanged
```Swift
    let cities = ["Nairobi", "Tanzania", "Kigali", "Cape Town"]
    print(cities.sorted())
```

- Reverse Items in an Array
```Swift
    print(cities.reversed())
```

## Storing and Finding Data in Dictionaries
Dictionaries don't store items according to their position like arrays do, but instead let us decide where items should be stored. <br>
Dictionaries stores associations between keys of the same type and values of the same type in a collection with no defined ordering <br>
When reading from a dictionary, there's a chance that the key does not exist, or the key has no value, hence it always returns an optional. <br>
When reading from a dictionary, you can provide a default value to use if the key does not exist
```Swift
    let employee = [
        "name" : "Leonard Sangoroh",
        "job" : "Software Engineer",
        "location" : "Nairobi, Kenya"
    ]

    print(employee["name", default: "Unknown"])

    let olympics = [
        2012 : "London",
        2016 : "Rio de Janeiro",
        2020 : "Tokyo"
    ]

    print(olympics[2012, default: "Unknown"])

    //create an empty dictionary
    let heroes = [String : String]
    heroes["Kenya"] = "Dedan Kimathi"
```

The .count and removeAll() functions both exist for dictionaries

## Using Sets for Fast Data Lookup
They are similar to arrays, except that they don't store duplicates and don't store items in any particular order
```Swift
    let people = Set(["Lee", "Natty"])
```

- Declaring an Empty Set
```Swift
    let emptySet = Set<String>()
    emptySet.insert("Filling Set")
```

Alongside .contains(), sets also have the .count and .sorted() functions

## Creating and Using Enums (Enumerations)
An enum is a set of named values that can be created and used in your code <br>
Enums let us define a new data type with a handful of specific values that it can have
```Swift
    enum Weekday {
        case monday
        case tuesday
        case wednesday
        case thursday
        case friday
    }

    var dayOfTheWeek = Weekday.monday

```

Once you assign a value to a variable or constant, its data type becomes fixed <br>
For enums this means once can skip the enum name after the first assignment
```Swift
    var day = Weekday.monday
    day = .tuesday
    day = .friday
```

## Using Type Annotations
Type annotation let's us be specific about the data type we want
```Swift
    let name: String = "Lee"
    let age: Int = 23
    let height: Double = 1.76
    let sharp: Bool = true
    let schoolsLearnt: [String] = ["MEC", "Mang'u", "Strathmore"]
    let details: [String: String] = ["id": "134327"]
    let booksRead: Set<String> = Set(["The Subtle Art...", "How to Make Friends and Influence People"])
```
Declaring an empty array
```Swift
    var countries: [String] = [String]()
    var towns = [String]()
    var cities: [String] = []
```
## Checkpoint 2
This time the challenge is to create an array of strings, then write some code that prints the number of items in the array and also the number of unique items in the array.
```Swift
    var carModels = ["BMW", "Mercedez", "Toyota", "Mazda"]
    print(carModels.count)
    var uniqueCarModels = Set(carModels)
    print(uniqueCarModels.count)
```
## Check whether condition is True or False
Programs very often make choices, and Swift handles this with **if** statements <br>
if statements lets us check whether a condition is true
```Swift
    let score = 85

    if score > 80 {
        print("Great job!")
    }

    // comparison operators also works with strings
    // they are compared alphabetically
    let ourName = "Dave Lister"
    let friendName = "Arnold Rimmer"

    if ourName < friendName {
        print("It's \(ourName) vs \(friendName)")
    }

    if ourName > friendName {
        print("It's \(friendName) vs \(ourName)")
    }

    //equality operator
    let country = "Kenya"

    if country == "Kenya" {
        print("Naipenda nchi yangu \(country)")
    }

    // not equal operator
    if country != "Kenya" {
        print("I haven't been there before")
    }

    //check if a string is empty
    if country.isEmtpy == true {
        print("Empty")
    }

    if country.isEmpty {
        print("Empty")
    }
```

## Checking Multiple Conditions
```Swift
    // using else block for mutually exclusive conditions
    let age = 17

    if age >= 18 {
        print("You can vote")
    } else {
        print("Try again next election")
    }

    // using else if, where you can run a new check if the first one fails
    // there can only be one 'else'
    // 'else' means; if all other conditions have been false
    let a = false
    let b = true

    if a {
        print("Code to run if a is true")
    } else if b {
        print("Code to run if a is false but b is true")
    } else {
        print("Code to run if both a and b are false")
    }
```

- Making more advanced conditions
```Swift
    // if today's temperature is over 20 degrees but under 30 degrees, print a message
    let temp = 25

    if temp > 20 {
        if temp < 30 {
            print("Favorable weather conditions")
        }
    }

    // logical 'and'
    if temp > 20 andand temp < 30 {
        print("Favorable weather conditions")
    }

    // logical 'or'
    let userAge = 14
    let hasParentalConsent = true

    if userAge >= 18 || hasParentalConsent == true {
        print("You can buy the game")
    }

    //shorthand
    if userAge >= 18 || hasParentalConsent {
        print("You can buy the game")
    }
```

- Checking multiple conditions, using enums, and applying logical 'OR'
```Swift
    enum TransportOption {
        case airplane, helicopter, bicycle, car, scooter
    }

    let transport = TransportOption.airplane

    if transport == .airplane || transport == .helicopter {
        print("Let's fly!")
    } else if transport == .bicycle {
        print("I hope there's a bike path…")
    } else if transport == .car {
        print("Time to get stuck in traffic.")
    } else {
        print("I'm going to hire a scooter now!")
    }
```

## Using Switch Statements to Check Multiple Conditions
Switch cases work well with enums since it knows all possible cases the enum can have, Swift will help out on ensuring that all cases are checked and there is no duplicate checks <br>
All switch...cases must be exhaustive; meaning they must all possible values <br>
Swift will execute the first case that matches the condition and go no further

```Swift
    enum Weather { case sun, rain, wind, snow, unkown}

    let forecast = Weather.sun

    switch forecase {
        case .sun:
            print("It should be a nice day")
        case .rain:
            print("Pack an umbrella")
        case .wind:
            print("Wear something warm")
        case .snow:
            print("School is cancelled.")
        case .unknown:
            print("Our forecast generator is broken")
    }
```

- Switch...case can have a 'default' value when there is ambiguity <br>
For example, when switching between Strings, you can't check all possible strings so a default value would be required <br>
The default case will run if all cases have failed to match

```Swift
    let place = "Metropolis"

    switch place {

        case "Gotham":
            print("You're Batman!")
        case "Mega-City One":
            print("You're Judge Dredd!")
        case "Wakanda":
            print("You're Black Panther!")
        default:
            print("Who are you?")
    }
```

**Remember: Swift checks its cases in order and runs the first one that matches. If you explicitly want Swift to carry on executing subsequent cases, use 'fallthrough' just before ending the case code block**

## Using the Ternary Conditional Operator for Quick Tests
The ternary operator lets us check a condition and return one of two values

```Swift
    //create a constant called 'age' and another called 'canVote' that will store whether you can vote
    // WTF(What, True, False) syntax
    let age = 23

    let canVote = age >= 18 ? "Yes" : "No"

    // another example
    let temp = 24
    let generalWeather = temp < 16 ? "It's freezing" : "No need for a heavy jacket"

    //another example
    enum Theme {
        case light, dark
    }

    // if Theme is dark, assign "black" to theme otherwise assign "white" to theme
    let theme = Theme.dark

    let background = theme == .dark ? "black" : "white"
    print(background)
```

## Using a For Loop to Repeat Work

- Print each Item in an Array
```Swift

    // loop body - code inside the braces
    // loop iteration - one cycle through the loop body
    // loop variable - exists only inside the loop body and will change to a new value in the next loop iteration

    let platforms = ["iOS", "macOS", "tvOS", "wathcOS", "visionOS"]

    for os in platforms {
        print("Swift works on \(os))
    }
```
- Loop over fixed range of numbers
```Swift
    // prints 1 to 12 (including 12)
    for i in 1...12 {
        print(i)
    }
```

- Put loops inside loops (nested loops)
```Swift
    for i in 1...12 {
        for j in 1...12 {
            print("\(i) x \(j) is \(i*j)")
        }
    }
```
- Loop over fixed range of numbers
```Swift
    // prints 1 to 11 (excluding 12)
    for i in 1..<12 {
        print(i)
    }
```

- Loop over without need for a variable
```Swift
    // prints 1 to 4 (including 4)
    for _ in 1...4 {
        print("Help")
    }
```
## Using a While Loop to Repeat Work
A while loop continuously executes a loop until the condition is false
- Basic while loop
```Swift
    var countdown = 10

    while countdown > 0 {
        print("\(countdown)")
        countdown -= 1
    }

    print("blast off!")
```

While loops are useful when the iterations of a loop can't be determined at the start <br>
For example; when rolling a virtual dice and ending the loop when 6 is rolled
```Swift
    var roll = 0

    while roll != 6 {
        roll = Int.random(in: 1...6)
        print("I rolled a \(roll)")
    }
```
## Skipping Loop Items with Break and Continue
- Continue: skips the current loop iteration
- Break: exits the loop skips all remaining iterations

```Swift
    // continue
    // if filename does not have ".jpg" as suffix, skip it and move to the next iteration
    let filenames = ["me.jpg", "work.txt", "sophie.jpg", "logo.psd"]

    for filename in filenames {
        if filename.hasSuffix(".jpg") == false {
            continue
        }

        print("Found picture: \(filename)")
    }

    /* break
     checking multiples for two numbers
     if i is a multiple of both 4 and 14, append it to the integer array
     once the 10 multiples are appended, call break to exit the loop
    */
    let number1 = 4
    let number2 = 14
    var multiples = [Int]()

    for i in 1...100_000 {
        if i.isMultiple(of: number1) andand i.isMultiple(of: number2) {
            multiples.append(i)

            if multiples.count == 10 {
                break
            }
        }
    }

    print(multiples)
```

## Checkpoint 3
Your goal is to loop from 1 through 100, and for each number:

- If it’s a multiple of 3, print “Fizz”
- If it’s a multiple of 5, print “Buzz”
- If it’s a multiple of 3 and 5, print “FizzBuzz”
- Otherwise, just print the number.

```Swift
    for i in 1...100 {
        if i.isMultiple(of: 3) andand i.isMultiple(of: 5) {
            print("FizzBuzz")

        } else if i.isMultiple(of: 3) {
            print("Fizz")

        } else if i.isMultiple(of: 5) {
            print("Buzz")

        } else {
            print("\(i)")
        }
    }
```

## Reusing Code with Functions
Functions enable the reuse of code

```Swift
    // create function
    func showWelcome(){
        print("Welcome to my application!")
    }

    // call a function
    showWelcome()

    // parameters in functions
    // function that prints the multiplication table
    func printTimesTable(number: Int, end: Int){
        for i in 1...end {
            print("\(i) x \(number) is \(i * number)")
        }
    }

    // 5 and 20 are arguments
    printTimesTable(number: 5, end: 20)
```
## Returning Values from Functions
```Swift
    func rollDice() -> Int {
        return Int.random(in: 1...6)
    }

    let result = rollDice()

    // example two
    func areLettersIdentical(stringOne: String, stringTwo: String) -> Bool {
        let first = stringOne.sorted()
        let second = stringTwo.sorted()
        return first == second
    }

    // when a function has only one line of code and has promised to return a value,
    // there's no need to write the 'return' keyword
    func areLettersIdentical(string1: String, string2: String) -> Bool {
        string1.sorted() == string2.sorted()
    }

    func pythagoras(a: Double, b: Double) -> Double {
        let input = a * a + b * b
        let root = sqrt(input)
        return root
    }

    let c = pythagoras(a: 3, b: 4)
    print(c)

    // shorten pythagoras()
    func pythagoras(a: Double, b: Double) -> Double {
        sqrt(a * a + b * b)
    }
```

## Returning Multiple Values from Functions

- Return multiple values using an array
```Swift
    func getUser() -> [String] {
        ["Lee", "Sangoroh"]
    }

    let user = getUser()
    print("Name: \(user[0]) \(user[1])")
```

- Return multiple values using a dictionary
```Swift
    func getUser() -> [String: String] {
        [
            "fName" : "Lee", 
            "lName" : "Sangoroh"
        ]
    }

    let user = getUser()
    print("Name: \(user["fName"], default: "Anonymous") \(user["lName"], default: "Anonymous")")
```

## Tuples
Like arrays, dictionaries, and sets, tuples lets us store multiple values in a single variable. <br>
Unlike the rest, tuples have a fixed size and can have a variety of data types
```Swift
    func getUser() -> (firstName: String, lastName: String) {
        (firstName: "Lee", lastName: "Sangoroh")
    }

    let user = getUser()
    print("Name: \(user.firstName) \(user.lastName)")

    /* 
    when returning a tuple from a function, Swift already knows the names you're giving each item in the
    tuple, so there's no need to repeat them when returning
    */
        func getUser() -> (firstName: String, lastName: String) {
            ("Lee", "Sangoroh")
        }

    /* 
    some given tuples may have elements without names
    you will access them using numerical indices
    */
    func getUser() -> (String, String) {
        ("Lee", "Sangoroh")
    }

    let user = getUser()
    print("Name: \(user.0) \(user.1)")

    /*
    if a function returns a tuple you can pull the tuple apart into individual values
    */
    func getUser() -> (firstName: String, lastName: String) {
        (firstName: "Taylor", lastName: "Swift")
    }

    let (firstName, lastName) = getUser()
    print("\(firstName) \(lastName)")

    // if you don't need all values from the tuple
    let (firstName, _) = getUser()
    print(firstName)
```

- Return type is (firstName: String, lastName: String), which is a tuple containing two strings
- The key advantage for tuples over dictionaries is that we can specify exactly which values will exist and what types they have, whereas dictionaries may or may not contain the values we're asking for

## Customizing Parameter Labels
When defining parameters for a function we can add two names; one for use where the function is called and one for use inside the function
```Swift
    func isUppercase(_ string: String) -> Bool {
        string == string.uppercased()
    }

    let string = "HELLO, WORLD"
    let result = isUppercase(string)

    // a name for calling the function and for using inside the function block
    func printTimesTables(for number: Int) {
        for i in 1...12 {
            print("\(i) x \(number) is \(i * number)")
        }
    }

    printTimesTables(for: 5)
```

## Providing Default Values for Parameters
```Swift
    func printTimesTable(for number: Int, end: Int = 12) {
        for i in 1...end {
            print("\(i) x \(number) is \(i * number)")
        }
    }

    printTimesTable(for: 5, end: 12)
    printTimesTable(for: 3)
```

## Handling Errors in Functions

Handling errors involves three steps; <br> 
1. Informing Swift of the possible errors that can happen
2. Writing a function that can flag up errors if they happen
3. Calling the function, and handling any errors that might happen
```Swift
    // define possible errors that might happen i.e. make a new enum that builds on Swift's existing Error type
    enum PasswordError: Error {
        case short
        case obvious
    }
    // the enum does not define what the errors mean, it only brings existence

    // write a function that will trigger one of the errors
    func checkPassword(_ password: String) throws -> String {
        if password.count < 5 {
            throw PasswordError.short
        } 
        if password == "12345" {
            throw PasswordError.obvious
        }
        if password.count < 8 {
            return "OK"
        } else if password.count < 10 {
            return "Good"
        } else {
            return "Excellent"
        }
    }
    /*
    if a function can throw error(s) without handling them itself, make the function as 'throws' before the return type
    if marked with 'throws', the function can but must not throw an error
    */

    // run the function and handle any errors that might happen
    /*
    1. Start a block of work that might throw errors using 'do'
    2. Call one or more throwing functions using 'try'
    3. Handling any thrown error using catch
    */
    let string = "12345"
    do {
        let result = try checkPassword(string)
        print("Rating: \(result)")
    } catch {
        print("There was an error")
    }
    /*
    try - must be written before all functions that can throw an error
    one must be inside a 'do' block when using 'try, and one must have a 'catch' block(s)
    */

    /* when it comes to catching errors, one must have a catch block (that's able to handle every kind of error)
    you can also catch specific errors
    */
    let string = "12345"

    do {
        let result = try checkPassword(string)
        print("Password rating: \(result)")
    } catch PasswordError.short {
        print("Please use a longer password.")
    } catch PasswordError.obvious {
        print("I have the same combination on my luggage!")
    } catch {
        print("There was an error.")
    }
```

## Checkpoint 4
The challenge is this: write a function that accepts an integer from 1 through 10,000, and returns the integer square root of that number. That sounds easy, but there are some catches:
- You can’t use Swift’s built-in sqrt() function or similar – you need to find the square root yourself.
- If the number is less than 1 or greater than 10,000 you should throw an “out of bounds” error.
- You should only consider integer square roots – don’t worry about the square root of 3 being 1.732, for example.
- If you can’t find the square root, throw a “no root” error.

```Swift

    enum Errors: Error {
        case outOfBounds
        case noRoot

    }

    func squareRoot(number: Int) throws -> Int {
        if number > 1 andand number <= 10_000 {
            for i in 1...100 {
                if i*i == number {
                    return i
                } else {
                    throw Errors.noRoot
                }
            }
        }
        
        throw Errors.outOfBounds
    }

    do {
        let result = try squareRoot(number: 35)
    } catch Errors.outOfBounds{
        print("the number entered should be between 1 and 10_000")
    } catch Errors.noRoot {
        print("the number entered has not square root")
    } catch {
        print("There is an error")
    }
```

## Creating and Using Closures
```Swift
    // create closure
    let sayHello = {
        print("Hi there!")
    }

    sayHello()

    // parameter-accepting closure(s)
    let sayHi = { (name: String) -> String in
        // must not use 'return' keyword since its a single line
        "Hi \(name)"
    }
    /*
     no parameter name is required since when the closure is assigned to a variable,
     it acquires the type (String)-> String
     and not type (name: String) -> String
     that is just how it is :)

     this works the same way as creating a copy of a function
     it assumes a different data type and hence no need to mention the parameter name while passing the argument
    */
    sayHi("Lee")
```

## Function Types (Yes, functions have types Similar to Int, Double)
```Swift
    func greetUser() {
        print("Hello")
    }

    var greetCopy = greetUser
    //type annotation for greetCopy
    /*
    - empty parentheses shows the function takes no arguments
    - the arrow prompts the declaration of a return type
    - Void means 'nothing'; meaning the function returns nothing
    */
    var greet: () -> Void = greetUser

    // every function's type depends on the data it receives and returns

    func getUserData(for id: Int) -> String {
        if id == 1989 {
            return "Taylor Swift"
        } else {
            return "Anonymous"
        }
    }

    let data: (Int) -> String = getUserData
    let user = data(1989)
    print(user)
```
## Passing Functions into other Functions
```Swift
    let fullName = ["Leonard", "Lee", "Sangoroh"]
    //will sort alphabetically
    let sortedName = fullName.sorted()
    print(sortedName)

    // sorted allows us to pass in a custom sorting function
    //provided it takes in two strings, and returns a boolean
    // if true first string will be sorted before second
    //if false, second string will be sorted before first

    //sort function to put firstName as the first in the array
    func firstNameFirstSorted(name1: String, name2: String) -> Bool {
        if name1 == "Lee" {
            return true
        } else if name2 == "Lee" {
            return false
        }

        return name1 < name2
    }

    let firstNameFirst = fullName.sorted(by: firstNameFirstSorted)
    print(firstNameFirst)

    /*
    instead of passing a function, you can just write the logic directly into the sorted()
    using a closure
    */
```

## Passing a Closure into a Function
```Swift
    /*
    instead of passing a function, you can just write the logic directly into the sorted()
    using a closure
    */
    let firstNameFirst = fullName.sorted(by: { (nameOne: String, nameTwo: String) -> Bool in
    if nameOne == "Lee" {
        return true
    } esle if nameTwo == "Lee" {
        return false
    }

    return nameOne < nameTwo

    })
```

## Trailing Closure Syntax and Shorthand Syntax
- We will practically do this by using the section above ('Passing a Closure into a Function') for reference
```Swift
    /*
    the function passed into .sorted() must have two string parameters and return a boolean

    so there's no need to specify the types of the two parameters because they must be strings
    and no need to specify the return type since it must be boolean

    //code change
    */
     let firstNameFirst = fullName.sorted(by: { (nameOne, nameTwo) in
    if nameOne == "Lee" {
        return true
    } esle if nameTwo == "Lee" {
        return false
    }

    return nameOne < nameTwo

    })

    // trailing closure syntax
    // allowed when one function accepts another
    let firstNameFirst = fullName.sorted { (nameOne, nameTwo) in
        if nameOne == "Lee" {
            return true
        } esle if nameTwo == "Lee" {
            return false
        }

        return nameOne < nameTwo
    }

    // shorthand syntax
    // swift can automatically provide names for our parameters
    let firstNameFirst = fullName.sorted {
        if $0 == "Lee" {
            return true
        } esle if $1 == "Lee" {
            return false
        }

        return $1 < $2
    }
```
## Other Closure Examples
- The filter() function lets us run some code on every item in the array, and will send back a new array containing every item that returns true for the function. So, we could find all team players whose name begins with T like this:
```Swift
    let allNames = ["Lee", "Leonard", "Sangoroh"]
    let lOnly = allNames.filter { $0.hasPrefix("L")}
```

- The map() function lets us transform every item in the array using some code of our choice, and sends back a new array of all the transformed items
```Swift
    let uppercasedName = allNames.map { $0.uppercased() }
    print(uppercasedName)
```

## Accepting Functions as Parameters
```Swift
    // function accepting a function/closure
    func makeArray (size: Int, using generator: () -> Int) -> [Int] {
        var numbers = [Int]()

        for _ in 0..<size {
            let newNumber = generator()
            numbers.append(newNumber)
        }

        return numbers
    }

    // calling the function and passing a closure using trailing syntax
    let rolls = makeArray(size: 50) {
        Int.random(in: 1...20)
    }

    print(rolls)

    // calling a function and passing a function
    func generateNumber() -> Int {
        Int.random(in: 1...20)
    }

    let newRolls = makeArray(size: 50, using: generateNumber)
    print(newRolls)
```

## A Function with Three Function Parameters
```Swift
    func doImportantWork(first: () -> Void, second: () -> Void, third: () -> Void) {
        print("About to start first work")
        first()
        print("About to start second work")
        second()
        print("About to start third work")
        third()
        print("Done!")
    }

    // calling the function
    doImportantWork {
        print("This is the first work")
    } second: {
        print("This is the second work")
    } third: {
        print("This is the third work")
    }
```
## Checkpoint 5
Your job is to:
- Filter out any numbers that are even
- Sort the array in ascending order
- Map them to strings in the format “7 is a lucky number”
- Print the resulting array, one item per line

```Swift
    let luckyNumbers = [7,4,38,21,16,15,12,33,31,49]

    func mixedFunction(luckyNumbers: [Int]) -> [String] {
        
        let oddNumbers = luckyNumbers.filter { !$0.isMultiple(of: 2)}
        
        let sortedNumbers = oddNumbers.sorted()
        
        let mappedToString = sortedNumbers.map { "\($0) is a lucky number" }
        
        return mappedToString
    }
    var mappedToString = mixedFunction(luckyNumbers: luckyNumbers)

    for string in mappedToString {
        print(string)
    }

    // chaining methods without using temporary variables
    let luckyNumbers = [7,4,38,21,16,15,12,33,31,49]

    func mixedFunction(luckyNumbers: [Int]) -> [String] {
        
        let mappedToString = luckyNumbers.filter{ !$0.isMultiple(of: 2)}.sorted().map{ "\($0) is a lucky number"}
        
        return mappedToString
    }

    var mappedToString = mixedFunction(luckyNumbers: luckyNumbers)

    for string in mappedToString {
        print(string)
    }
```
## Creating Structs
- Swift's structs let us create our own custom, complex data types, complete with their own variables, and functions
- Variables and constants that belong to structs are called properties
- Functions that belong to structs are called methods
- An instance of a struct is created when a constant or variable is created from the struct

```Swift
    // create new type called album with two string constants plus an integer constant and a function
    struct Album {
        let title: String
        let artist: String
        let year: Int

        func printSummary() {
            print("\(title) \(year) by \(artist)")
        }
    }

    let red = Album(title: "Red", artist: "TS", year: 2012)
    let wings = Album(title: "Wings", artist: "BTS", year: 2016)

    print(red.title)
    print(wings.artist)

    red.printSummary()

    // when having changing values in a struct, the variable created from the instance must be a 'var'
    // in case a function is changing a variable, it must start with the keyword 'mutating'
    struct Employee {
        let name: String
        var vacationRemaining: Int = 14

        mutating func takeVacation(days: Int) {
            if vacationRemaining > days {
                vacationRemaining -= days
                print("I'm going on vacation!")
                print("Days remaining: \(vacationRemaining)")
            } else {
                print("Oops! There aren't enough days remaining.")
            }
        }
    }

    var archer = Employee(name: "Lee Archer", vacationRemider: 14)
    var kane = Employee(name: "Harry Kane")

    archer.takeVacation(days: 4)
    print(archer.vacationRemaining)
```

## Compute Property Values Dynamically

A struct can have two types of variables; <br>
    - stored property - variable that holds a piece of data inside an instance of a struct <br>
    - computed property - calculates the value of the property dynamically every time its accessed <br>

```Swift
    struct Employee {
        let name: String
        var vacationAllocated = 14
        var vacationTaken = 0
        // vacationRemaining is calculated by subtracting how much vacation they have taken from how much
        // vacation they were allocated
        // it is not assigned but rather calculated
        var vacationRemaining: Int {
            vacationAllocated - vacationTaken
        }
    }

    var archer = Employee(name: "Sterling Archer", vacationAllocated: 14)
    archer.vacationTaken += 4
    // reading from vacationRemaining
    print(archer.vacationRemaining)
    archer.vacationTaken += 4
    // reading from vacationRemaining
    print(archer.vacationRemaining)

    
    // reading from and writing to computed properties
    var vacationRemaining: Int {
        get {
            vacationAllocated - vacationTaken
        }

        set {
            // newValue is automatically provided by Swift, and stores whatever value the user
            // was trying to assign to the property
            vacationAllocated = vacationTaken + newValue
        }
    }

    var archer = Employee(name: "Sterling Archer", vacationAllocated: 14)
    archer.vacationTaken += 4
    archer.vacationRemaining = 5
    print(archer.vacationAllocated)
```

## Taking Action when a Property Changes
- Swift enables us to set property observers, which are special code blocks that run when properties change
- There are of two forms; didSet and willSet
- didSet; runs when the property just changed
- willSet; runs before the property changes

```Swift
    struct Game {
        var score = 0 {
            didSet {
                print("Score changed to \(score)")
            }
        }
    }

    var game = Game()
    game.score += 10
    game.score -= 3
    game.score += 1

    struct App {
        var contacts = [String]() {
            willSet {
                print("Current value is: \(contacts)")
                print("New value will be: \(newValue)")
            }

            didSet {
                print("There are now \(contacts.count) contacts.")
                print("Old value was \(oldValue)")
            }
        }
    }

    var app = App()
    app.contacts.append("Adrian E")
    app.contacts.append("Allen W")
    app.contacts.append("Ish S")
```

## Creating Custom Initializers
- Initializers are specialized methods designed to prepare a new struct instance to be used
- We can create our own struct as long as we ensure all properties have a value by the time the initializer ends
```Swift
    // our own initializer
    // once you create your custom initializer, Swift assumes that the default one
    // is no longer needed
    struct Player {
        let name: String
        let number: Int

        init (name: String, number: Int) {
            self.name = name
            self.number = number
        }
    }
```
## Limit Access to Internal Data using Access Control
- By default, Swift's structs let us access their properties and methods freely
- Sometimes, you want to hide some data from external access

```Swift
    struct BackAccount {
        // make funds variable inaccessible outside the struct to prevent people
        // from adjusting their real balance
        private var funds = 0

        mutating func deposit(amount: Int) {
            funds += amount
        }

        mutating func withdraw(amount: Int) -> Bool {
            if funds >= amount {
                funds -= amount
                return true
            } else {
                return false
            }
        }

        var account = BankAccount()
        account.deposit(amount: 100)
        let success = account.withdraw(amount: 200)

        if success {
            print("Withdrew money successfully")
        } else {
            print("Failed to get the money")
        }
    }
```
Swift provides us with a couple of access controls; <br>
- private: Don't let anything outside the struct use this
- fileprivate: Don't let anything outside the current file use this
- public: Let anyone, anywhere use this
- private(set): let anyone read this property, but only let methods inside the struct write to it

## Static Properties and Methods
- Each instance of a struct has its own unique copy of properties and methods
- Sometimes, you want to add a property or method to the struct directly and not its instance, which enables you to use them directly
- Uses of static properties and methods include; <br>
    a. creating example data <br>
    b. storing fixed data

- No instance of School is created, its properties and methods are accessed directly
- 'mutating' is also not needed; it's only needed with a regular struct function when an instance of struct was created as a constant
```Swift
    struct School {
        static var studentCount = 0

        static func add(student: String) {
            print("\(student) joined the school")
            studentCount += 1
        }
    }

    School.add(student: "Lee Sangoroh")
    print(School.studentCount)
```
## Mixing Static and Non-Static Properties and Methods
- Rule One: You can't refer non-static properties and methods from static properties or methods
- Rule Two: To access static code from non-static code, use your type's name e.g. School.studentCount, or use Self to refer to the current type

**Difference btw self and Self** <br>
- self: refers to the current value of the struct
- Self: refers to the current type

```Swift
    // where structs are used
    
    // storing shared constant values
    struct AppData {
        static let version = "1.0.0 beta"
        static let saveFileName = "settings.json"
        static let homeURL = "https://www.mumamaler.com"
    }

    // generating examples
    struct Employee {
        let username: String
        let password: String

        static let example = Employee(username: "cfederighi", password: "hairforceone")
    }
```

## Checkpoint 6
 Create a struct to store information about a car, including its model, number of seats, and current gear, then add a method to change gears up or down. Have a think about variables and access control: what data should be a variable rather than a constant, and what data should be exposed publicly? Should the gear-changing method validate its input somehow?

```Swift
    struct Car {
        let carModel: String
        let numberOfSeats: Int
        var currentGear: Int
        
        mutating func gearUp(){
            if currentGear < 10 {
                currentGear += 1
            }
        }
        mutating func gearDown(){
            if currentGear > 1 {
                currentGear -= 1
            }
        }
    }

    var toyota = Car(carModel: "Toyota", numberOfSeats: 5, currentGear: 3)
    print(toyota.currentGear)
    toyota.gearUp()
    print(toyota.currentGear)
```

## Creating Classes
Apart from structs, Classes are also another way of creating custom data types <br>

**Differences between classes and structs** <br>
1. You can make one class build upon functionality in another class, gaining all its properties and methods as a starting point. You can also selectively override some methods.
2. There are no automatically generated memberwise initializers for classes. Either write you own, or assign default values
3. When you copy an instance of a class, both copies share the same data - if you change one copy, the other one also changes <br>
Why? In Swift, class are reference types; meaning when you create an instance of a class and then create a copy of that instance, both the original instance and the copy actually reference the same underlying object in memory. They both point to the same memory location.
**Structs** on the other hand are value types; meaning each instance of a struct has its own unique copy of the data. When you assign a struct instance to another variable, or pass it to a function, Swift creates a copy of that instance.
4. When the final copy of a class instance is destroyed, Swift can optionally run a special function called 'deinitializer'
5. Even if you make a class constant, you can still change its properties as long as they are variables

```Swift
    class Game {
        var score = 0 {
            didSet {
                print("Score is now \(score)")
            }
        }
    }

    var newGame = Game()
    newGame.score += 10
```

## Inheriting from a Class
When a class inherits functionality from another, Swift gives the child class access to the properties and methods of the parent class, allowing us to make small changes to customize the way the new class behaves
```Swift
    class Employee {
        let hours: Int

        init (hours: Int) {
            self.hours = hours
        }

        func printSummary() {
            print("I work \(hours) hours a day.")
        }
    }

    class Developer: Employee {
        func work() {
            print("I'm writing code for \(hours) hours")
        }
    }

    class Manager: Employee {
        func work() {
            print("I'm going to meetings for \(hours) hours")
        }

        // changing a method you inherit (using override)
        override func printSummary() {
            print("I am the boss, I decide how long I will work for")
        }
    }

    // the child classes can refer directly to 'hours'
    let lee = Developer(hours: 18)
    lee.work() // I'm writing code for 18 hours
    let sangoroh = Manager(hours: 6)
    sangoroh.work() // I'm going to meetins for 6 hours
    sangoroh.printSummary() // I work 6 hours a day
```
- If you want your class not to support any inheritance, mark it using 'final' keyword

## Adding Initializers for Classes
- If a child class has any custom initializers, it must always call the parent's initializer after it has finished setting up its own properties, if it has any

```Swift
    class Vehicle {
        let isElectric: Bool

        init(isElectric: Bool) {
            self.isElectric = isElectric
        }
    }

    class Car: Vehicle {
        let isConvertible: Bool

        init(isConvertible: Bool, isElectric: Bool) {
            self.isConvertible = isConvertible
            super.init(isElectric: isElectric)
        }
    }

    let tesla = Car(isConvertible: true, isConvertible: false)
```

**NB:** If a subclass doesn't have any of its own initializers, it automatically inherits the initializers of its parents class.

## Copying Classes
- In Swift, all copies of a class instance share the same data
```Swift
    class User {
        var username = "leonardsangoroh"
    }

    var userOne = User() //leonardsangoroh
    var userTwo = userOne // leonardsangoroh

    userTwo = "leonard"

    // both userOne and userTwo change to 'leonard'
    print(user1.username)  
    print(user2.username)
```

- If you want to create a unique copy of a class instance (deep copy), you need to handle creating a new instance and copy acros all your data safely
```Swift
    class User {
        var username = "Anonymous"

        func copy() -> User {
            let user = User()
            user.username = username
            return user
        }
    }

    // now we can safely call copy() to get an object with the same sarting data, but any future changes won't impact the original
    var anonymous = User(username: "lee")
    var lee = anonymous.copy
```
## De-initializing a Class
Swift's classes can optionally be given a de-initializer
- Deinitializers don't use the func keyword
- They can't take parameters or return data
- They are automatically called when the final copy of a class instance is destroyed
- They are automatically handled by the system
- Structs don't have deinitializers, because you can't copy them

```Swift
    class User {
        let id: Int

        init(id: Int) {
            self.id = id
            print("User \(id): I'm alive!")
        }

        deinit {
            print("User \(id): I'm dead!")
        }
    }

    // creating and destroying instances
    // if we create a User instance inside a loop, it will be destroyes when each loop iteration finishes
    for i in 1...3 {
        let user = User(id: i)
        print("User \(user.id): I'm in control!")
    }
```

## Working with Variables inside Classes
Four options for variables and instance of a class;

- Constant instance, constant property – a signpost that always points to the same user, who always has the same name.
- Constant instance, variable property – a signpost that always points to the same user, but their name can change.
- Variable instance, constant property – a signpost that can point to different users, but their names never change.
- Variable instance, variable property – a signpost that can point to different users, and those users can also change their names.

## Checkpoint 7
- Make a class hierarchy for animals, starting with Animal at the top, then Dog and Cat as subclasses, then Corgi and Poodle as subclasses of Dog, and Persian and Lion as subclasses of Cat.

But there’s more:

- The Animal class should have a legs integer property that tracks how many legs the animal has.
- The Dog class should have a speak() method that prints a generic dog barking string, but each of the subclasses should print something slightly different.
- The Cat class should have a matching speak() method, again with each subclass printing something different.
- The Cat class should have an isTame Boolean property, provided using an initializer.

```Swift
    class Animal {
        let legs: Int
        
        init(legs: Int) {
            self.legs = legs
        }
    }

    class Dog: Animal {
        
        //intrinsically inherits parent class' init method
        
        func speak() {
            print("Wooof!")
        }
    }

    class Cat: Animal {
        
        let isTame: Bool
        
        init(isTame: Bool, legs: Int) {
            self.isTame = isTame
            super.init(legs: legs)
        }
        
        func speak() {
            print("Meeeeow!")
        }
    }

    class Corgi: Dog {
        
        override func speak() {
            print("Corgi Wooof!")
        }
    }

    class Poodle: Dog {
        override func speak() {
            print("Poodle Wooof!")
        }
    }

    class Persian: Cat {
        
        override func speak() {
            print("Persian Meeoooow!")
        }
    }

    class Lion: Cat {
        
        override func speak() {
            print("Lion Meeoooow!")
        }
    }
```

## Protocols and Extensions
Protocols are like agreements in Swift; they let us define what kinds of functionality we expect a data type to support, and Swift ensures that the rest of our code follows those rules <br>
Protocols let us define properties and methods that we want to use without implementing those properties and methods.<br>
Protocols act as blueprints
```Swift
    // this is a new type
    protocol Vehicle {
        // if need be, you can mark methods as throwing or mutating
        func estimateTime(for distance: Int) -> Int
        func travel(distance: Int)
    }

    // we can create structs, classes, or enums that conform to the protocol

    // car struct that conforms to Vehicle Protocol
    struct Car: Vehicle {
        func estimateTime(for distance: Int) -> Int {
            distance/50
        }

        func travel(distance: Int) {
            print("I'm driving \(distance)km")
        }

        // not needed to conform to Vehicle protocol
        func openSunroof() {
            print("It's a nice day!")
        }

    }

    /*
    Swift knows that any type conforming to Vehicle must implement both estimateTime() and travel() methods,
    and so it lets us use Vehicle as the type of our parameter rather than car
    Now the function can be called with any type of data, as long as that type
    conforms to Vehicle protocol e.g. Car, Bus, Train, Plane etc.
    */
    //func commute(distance: Int, using vehicle: Car) {
    func commute(distance: Int, using vehicle: Vehicle) {    
        if vehicle.estimateTime(for: distance) > 100 {
            print("That's too slow!")
        } else {
            vehicle.travel(distance: distance)
        }
    }

    let car = Car()
    commute(distance: 100, using: car)

    struct Bicycle: Vehicle {
        func estimateTime(for distance: Int) -> Int {
            distance / 10
        }

        func travel(distance: Int) {
            print("I'm cycling \(distance)km.")
        }
    }

    let bike = Bicycle()
    commute(distance: 50, using: bike)

```

## Write Protocols to Describe Properties
- Type annotation is required for properties in protocol(s), since we can't provide a default value in a protocol, just as protocols can't provide implementations for methods.
```Swift
    protocol Vehicle {
        // a string called name which must be readable
        // Meaning it could be a constant of a computed property with a getter
        var name: String { get }
        // an integer called currentPassengers that must be read-write
        // could be a variable, or a computed property with a getter and setter
        var currentPassengers: Int { get set }
    }
```
- So now our protocol requires two methods and two properties, meaning that all conforming types must implement those four things in order for our code to work. This in turn means Swift knows for sure that functionality is present, so we can write code relying on it.
```Swift
    func getTravelEstimates(using vehicles: [Vehicle], distance: Int) {
        for vehicle in vehicles {
            let estimate = vehicle.estimateTime(for: distance)
            print("\(vehicle.name): \(estimate) hours to travel \(distance)km")
        }
    }

    getTravelEstimates(using: [car, bike], distance: 150)

```

## Protocol Inheritence
- One protocol can inherit from multiple protocols.
- Unlike classes, you can inherit from multiple protocols at the same time before you add your own customization.
```Swift
    protocol Payable {
        func calculateWages() -> Int
    }

    protocol NeedsTraining {
        func study()
    }

    protocol HasVacation {
        func takeVacation(days: Int)
    }

    // employee protocol brings together all the three protocols
    // we can make new types conform to the single protocol rather than the threes
    protocol Employee: Payable, NeedsTraining, HasVacation { }
```

## Extensions
- Extensions allow us to add methods(functionality) to existing types
```Swift
    // add extension to Int type, add a squared() methods to return current number squared
    extension Int {
        func squared() -> Int {
            return self * self
        }
    }

    let number = 23
    number.squared()
```

- Swift does not allow adding of stored properties in extensions, necessitating the use of computed properties
```Swift
    extension Int {
        var isEven: Bool {
            return self % 2 == 0
        }
    }
```

## Protocol Extensions
- Protocols: let us describe what properties and methods something should have, but don't provide implementation
- Extensions: let us provide implementation of methods, but only affect one data type i.e. one can't add the method to lots of types at the same time
- Protocol Extensions; are like regular extensions, but instead of extending a specific type like Int, we extend a whole protocol so that all conforming types get the changes
```Swift
    // both arrays and sets conform to Swift's collection protocol
    let sangorohs = ["Lee", "Rachael", "Roy"]
    let operations = Set(["addition", "subtraction"])

    // extend collection instead of arrays or sets
    extension Collection {
        func summarize() {
            print("There are \(count) of us: ")

            for name in self {
                print(name)
            }
        }
    }

    //both array and set will have the method
    sangorohs.summarizee()
    operations.summarize()
```

## Protocol-Oriented Programming
- Protocol extensions can provide default implementations for our own protocol methods, hence making it easy for a type to conform to a protocol
- We can extend a protocol to add method implementations, meaning any type conforming to that protocol get those  methods.
```Swift
    //protocol
    protocol Identifiable {
        var id: String { get set }
        func identify()
    }

    // you can make all conforming types implement identity() individually
    // but protocol extensions allow you to provide a default
    extension Identifiable {
        func identify() {
            print("My ID is \(id).")
        }
    }

    // creating a type that conforms to Identifiable
    struct User: Identifiable {
        var id: String
    }

    let lee = User(id: "Lee")
    lee.identify()
```

## When are Protocol Extensions useful?
- Used to add functionality directly to protocols, meaning there's no need to copy that functionality to all structs and classes conforming to the protocol

## Checkpoint 8
Make a protocol that describes a building, adding various properties and methods, then create two structs, House and Office, that conform to it. <br>
Your protocol should require the following:

- A property storing how many rooms it has.
- A property storing the cost as an integer (e.g. 500,000 for a building costing $500,000.)
- A property storing the name of the estate agent responsible for selling the building.
- A method for printing the sales summary of the building, describing what it is along with its other properties.
```Swift 
    protocol Building {
        var numberOfRooms: Int { get }
        var cost: Int { get set }
        var agentName: String { get }
        
        func printSalesSummary() -> Void
        
    }

    extension Building {
        
        func printSalesSummary() -> Void {
            print("""
                \(numberOfRooms)
                \(cost)
                \(agentName)
                """)
        }
    }

    struct House: Building {
        var numberOfRooms: Int
        var cost: Int
        var agentName: String
    }

    struct Office: Building {
        var numberOfRooms: Int
        var cost: Int
        var agentName: String
    }

    let houseOne = House(numberOfRooms: 5, cost: 1_000_000, agentName: "Lee Sangoroh")
    print(houseOne.printSalesSummary())
```

## Optionals
- An optional variable might have a value or might not; it might literally be missing, which is 'nil' in Swift
```Swift
    //make a type optional by adding ? after it
    var age: Int? = nil
    // assign a value
    age = 23
```
## Unwrapping optionals
```Swift
    // if...let
    if let unwrapped = age {
        print("I am \(age)years old") 
    } else {
        print("Missing name.")
    }

    // unwrapping with guard
    // guard let will unwrap an optional
    // but if it finds nil inside it expects you to exit the function loop, or condition you used it in

    // guard let lets your unwrapped variable be used after the guard code
    func greet (_ name: String?) {
        guard let unwrapped = name else {
            print("No name provided")
            return
        }

        print("Hello, \(unwrapped)!")
    }
```

## Force Unwrapping
- Force unwrapping converts an optional to a non-optional
- e.g. Converting a String to an Integer leads to the destination variable being an optional because the converted string could be a word hence not convertinble to an Integer
- However, if you're sure it is an integer, you can force unwrap
- If forcefully unwrapped and found to be nil, the entire code crashes
```Swift
    let str = "7"
    //optional
    let num = Int(str)

    // non-optional
    let num = Int(str)!
```

## Implicitly Unwrapped Optionals
- Regular optional, just that they don't need to be unwrapped to be used
- They exist because sometimes a variable will start life as nil, but will always have a value before you need to use it
```Swift
    let age: Int! = nil
```

## Nil Coalescing
- It ensures that a variable has a value
- The nil coalescing operator unwraps an optional and returns the value inside if there's one. If the optional was nil, a default value is used instead

```Swift
    func username(for id: Int) -> String? {
        if id == 1 {
            return "Lee Sangoroh"
        } else {
            return nil
        }
    }

    // nil coalescing
    let mainUser = username(for: 5) ?? "Anonymous"
    print(mainUser) //prints Anonymous
```

## Optional Chaining
- Swift gives a shortcut to access things like a.b.c and b is an optional. 
- You can write a question mark after it to enable optional chaining (a.b?.c)
- Swift checks whether b has a value, if it's nil, the rest of the line is ignored but if it has a value it will be unwrapped and execution will continue
```Swift
    let names = ["Lee", "Leonard", "Sangoroh"]
    // if first item in array exists, execution continues and fName will contain its uppercased version
    // if first item is not there, execution ends and fName is assigned nil
    let fName = names.first?.uppercased()
```

## Optional try

- Previous do...try...catch
```Swift
    enum PasswordError: Error {
        case obvious
    }

    func checkPassword(_ password: String) throws -> Bool {
        if password == "password" {
            throw PasswordError.obvious
        }

        return true
    }

    do {
        try checkPassword("password")
        print("That password is good!")
    } catch {
        print("You can't use that password.")
    }
```
- There are two alternatives to try; try? and try!
- The first is try?, changes throwing functions into functions that return an optional.
- If the function throws an error you'll be sent nil as the result, otherwise you'll get the return value wrapped as an optional
```Swift
    if let result = try? checkPassword("password") {
        print("Result has \(result)")
    } else {
        print("D'oh.")
    }
```

- The second is try!, which is used when you know the function will not fail. If the function throws an error then all the code crashes
```Swift
    try! checkPassword("Leonard")
    print("Okay")
```

## Failable Initializers

- In Swift, a failable initializer is an initializer that can return nil, indicating that the initialization of the object has failed. This is useful when you need to perform some validation or checks during the initialization process, and there's a possibility that the initialization might not succeed.

- You define a failable initializer by placing a question mark after the init keyword: init?. If the initialization fails, you return nil.
```Swift
    struct Person {
        var name: String
        var age: Int

        init?(name: String, age: Int) {
            if age < 0 {
                // If the age is negative, return nil to indicate initialization failure
                return nil
            }
            self.name = name
            self.age = age
        }
    }

    if let person = Person(name: "John Doe", age: 30) {
        print("Person was created successfully: \(person.name), \(person.age) years old")
    } else {
        print("Failed to create person")
    }

    if let person = Person(name: "Jane Doe", age: -5) {
        print("Person was created successfully: \(person.name), \(person.age) years old")
    } else {
        print("Failed to create person")
    }

```

- In this example, the Person struct has a failable initializer. It checks if the age is less than 0, and if so, it returns nil, indicating that the initialization has failed. When we try to create a Person with a negative age, the initializer fails, and we get nil.

- Failable initializers are useful when dealing with potentially invalid data or when initializing objects that depend on certain conditions being met. They provide a way to safely handle initialization failures without causing runtime errors.

## Typecasting
- Used for filtering sometimes
```Swift
    class Animal {

    }

    class Fish: Animal {

    }

    class Dog: Animal {
        func makeNoise() {
            print("Woof!")
        }
    }

    //array of fish and dogs
    let pets = [Fish(), Dog(), Fish(), Dog()]

    //both Fish and Dog inherit from Animal class, hence type inference is used to make pets an array of Animal

    // if we want to loop over pets and ask all dogs to bark
    // we need to perform a typecase: Swift will check whether each pet is a Dog object
    // if it is we can call makeNoise()
    // we will need the keyword as?, which returns an optional; it will be nil if the typecast fails, or a converted type otherwise

    for pet in pets {
        if let dog = pet as? Dog {
            dog.makeNoise()
        }
    }
```
