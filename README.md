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