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