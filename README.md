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