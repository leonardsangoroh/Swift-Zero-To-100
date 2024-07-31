# Introduction to Swift

## Constants & Variables
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

- Check Prefix & Suffix
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

## Storing & Finding Data in Dictionaries
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
    let booksRead: Set<String> = Set(["The Subtle Art...", "How to Make Friends & Influence People"])
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
    if temp > 20 && temp < 30 {
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
    // loop variable - exists only inside the loop body & will change to a new value in the next loop iteration

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
## Skipping Loop Items with Break & Continue
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
        if i.isMultiple(of: number1) && i.isMultiple(of: number2) {
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
        if i.isMultiple(of: 3) && i.isMultiple(of: 5) {
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
        if number > 1 && number <= 10_000 {
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

## Creating & Using Closures
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
- Swift's structs let us creat our own custom, complex data types, complete with their own variables, and functions
- Variables & constants that belong to structs are called properties
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

    
    // reading from & writing to computed properties
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
- There are of two forms; didSet & willSet
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

## Static Properties & Methods
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
## Mixing Static & Non-Static Properties and Methods
- Rule One: You can't refer non-static properties and methods from static properties or methods
- Rule Two: To access static code from non-static code, use your type's name e.g. School.studentCount, or use Self to refer to the current type

**Difference btw self & Self** <br>
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