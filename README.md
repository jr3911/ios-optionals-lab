# Optionals lab

Fork and clone this repo. On your fork, answer and commit the follow questions. When you are finished, submit the link to your repo on Canvas.


## Question 1

`var userName: String?`

Write 3 different ways of safely unwrapping and printing the value of `userName`.  If it is nil, print "No name".

- Method one: Check for nil and force unwrap

- Method two: Optional binding

- Method three: Nil coalescing

```swift
var userName: String?

// Method One: Check for nil and force unwrap
if userName == nil {
    print("No name")
} else {
    print(userName!)
}

// Method Two: Optional binding
if let boundUserName = userName {
    print(boundUserName)
} else {
    print("No name")
}

// Method Three: Nil coalescing
let possibleUserName = userName ?? "Username"
print(possibleUserName)
```


## Question 2

Given optional string `backgroundColor`, write code that safely unwraps and prints it. If backgroundColor is nil, give it a value.

`var backgroundColor: String?`

```swift
var backgroundColor: String?

if let backgroundColor = backgroundColor {
    print(backgroundColor)
} else {
    backgroundColor = "Blue"
    print(backgroundColor)
}
```


## Question 3

Given an optional width and an optional height of a rectangle, write code that calculates and prints the area. Print an error message if either value is nil.

```swift
var width: Double?
var height: Double?

if let width = width {
    if let height = height {
        print(width * height)
    } else {
        print("Error: height is missing")
    }
} else {
    print("Error: width is missing")
}
```


## Question 4

Given the following optional variables `name`, `age` and `height`. Write code so that it prints `name`, `age` and `height` if they all have a value. If any are nil, print an error message. Try using optional binding.

```swift
var name: String?
var age: Int?
var height: Double?

if let name = name, let age = age, let height = height {
    print("Name: \(name), Age: \(age), Height: \(height)")
} else {
    print("Error: not all fields are filled")
}
```


## Question 5

Given the variables `firstName`, `middleName` and `lastName`. Create a variable called `fullName` that is a nicely formatted string.

```swift
var firstName: String = "Johnny"
var middleName: String?
var lastName: String = "Stone"
var fullName = ""

if let middleName = middleName {
    fullName = firstName + " " + middleName + " " + lastName
} else {
    fullName = firstName + " " + lastName
}

print(fullName)

```


## Question 6

Write code that adds 15 to `myIntString`, then prints the sum. Use the `Int()` constructor which returns an optional Int `(Int?)`.

`let myIntString = "35"`

```swift
let myIntString = "35"

var sum = Int(myIntString)! + 15

print(sum)
```

## Question 7

Given an optional tuple of optional Ints, write code to safely unwrap the tuple and calculate the sum of its contents that aren't nil.

```swift
var scores: (Int?, Int?, Int?)?

var testCaseOne: (Int?, Int?, Int?)? = (4, nil, 7)
var testCaseTwo: (Int?, Int?, Int?)? = (nil, nil, 9)
var testCaseThree: (Int?, Int?, Int?)? = (5, 10, 24)

if var testCaseOne = testCaseOne {
    testCaseOne.0 = testCaseOne.0 ?? 0
    testCaseOne.1 = testCaseOne.1 ?? 0
    testCaseOne.2 = testCaseOne.2 ?? 0
    var sum1 = testCaseOne.0! + testCaseOne.1! + testCaseOne.2!
    print("Sum of testCaseOne: \(sum1)")
}

if var testCaseTwo = testCaseTwo {
    testCaseTwo.0 = testCaseTwo.0 ?? 0
    testCaseTwo.1 = testCaseTwo.1 ?? 0
    testCaseTwo.2 = testCaseTwo.2 ?? 0
    var sum2 = testCaseTwo.0! + testCaseTwo.1! + testCaseTwo.2!
    print("Sum of testCaseTwo: \(sum2)")
}

if var testCaseThree = testCaseThree {
    testCaseThree.0 = testCaseThree.0 ?? 0
    testCaseThree.1 = testCaseThree.1 ?? 0
    testCaseThree.2 = testCaseThree.2 ?? 0
    var sum3 = testCaseThree.0! + testCaseThree.1! + testCaseThree.2!
    print("Sum of testCaseThree: \(sum3)")
}
```


## Question 8

Safely unwrap `tuple` if there’s a non-nil tuple value and print it out.

```swift
var tuple: (Int, Int)?
if Bool.random() {
 tuple = (5, 3)
}

if let value = tuple {
    print(tuple)
}
```


## Question 9

Write code that either doubles `myInt` and then prints it, or prints an error message if myInt is nil.

```swift
var myInt: Int?
if Bool.random() {
 myInt = 5
}

if var myInt = myInt {
    myInt = myInt * 2
    print(myInt)
} else {
    print("Error: myInt is nil")
}
```


## Question 10

Write code that prints out the product of `myDouble` and `doubleTwo` or prints an error message if `myDouble` is nil.

```swift
var myDouble: Double?
let doubleTwo: Double = 5

if Bool.random() {
 myDouble = 12
}

if let myDouble = myDouble {
    print(myDouble * doubleTwo)
} else {
    print("Error: myDouble is nil")
}
```


## Question 11

Determine if the variable contains a Boolean or nil value. If nil set the variable to false, else keep it true.

```swift
var isTheGreatest: Bool?

if Bool.random() {
 isTheGreatest = true
}

isTheGreatest = isTheGreatest ?? false

print(isTheGreatest!)
```


## Question 12

Given the code below print the sum of each non-nil element in `myTuple`.

 ```swift
var myTuple: (Int?, Int?, Int?, Int?)

if Bool.random() {
 myTuple.0 = 5
 myTuple.2 = 14
} else {
 myTuple.1 = 9
 myTuple.3 = 10
}

myTuple.0 = myTuple.0 ?? 0
myTuple.1 = myTuple.1 ?? 0
myTuple.2 = myTuple.2 ?? 0
myTuple.3 = myTuple.3 ?? 0

var sum = myTuple.0! + myTuple.1! + myTuple.2! + myTuple.3!
print(sum)

```


## Question 13

Given the helper functions and code below, check to see if your `evolutionaryStone` is able to evolve your pokemon.  The table below shows the appropriate matches of pokemon to stone:

| Pokemon	   | Stone    |
| :--------: | :------: |
| Pikachu	   | Electric |
| Bulbasaur	 | Grass    |
| Charmander | Fire     |
| Squirtle	 | Water    |


```swift
// Helper Functions

func eStone() -> String {
 let random = Int(arc4random_uniform(5))
 switch random {
 case 0:
  return "Electric"
 case 1:
  return "Grass"
 case 2:
  return "Fire"
 case 3:
  return "Water"
 default:
  return "No Stone"
 }
}

func starterPokemon() -> String {
 let random = Int(arc4random_uniform(5))
 switch random {
 case 0:
  return "Pikachu"
 case 1:
  return "Bulbasaur"
 case 2:
  return "Charmander"
 case 3:
  return "Squirtle"
 default:
  return "Not a Pokemon"
 }
}

let pokemon: String?
var evolutionaryStone: String?
pokemon = starterPokemon()
evolutionaryStone = eStone()

var validCombinations = [("Pikachu", "Electric"), ("Bulbasaur", "Grass"), ("Charmander", "Fire"), ("Squirtle", "Water"), ("Not a Pokemon", "No Stone")]

let tryToEvolve = (pokemon, evolutionaryStone)
var confirmation: Bool = false

if let pokemon = tryToEvolve.0 {
    if let evolutionaryStone = tryToEvolve.1 {
        for combination in validCombinations {
            if (tryToEvolve.0!, tryToEvolve.1!) == combination {
                print("You applied \(evolutionaryStone) to \(pokemon). Uh-oh, something's happening!")
                confirmation = true
                break
            }
        }
    }
}

if confirmation == false {
    print("You tried to apply \(evolutionaryStone!) Stone to \(pokemon!)")
    print("Oak's words echoed. There's a time and place for everything, but not now!")
}
```


## Question 14

Given an optional int `numberOfPeople`, write code that unwraps and prints it **only if it is even**. Try using optional binding with a condition.

```swift
var numberOfPeople: Int?

if Bool.random() {
 numberOfPeople = 108       // can plug in any number
}

if let numberOfPeople = numberOfPeople {
    if numberOfPeople % 2 == 0 {
        print(numberOfPeople)
    } else if numberOfPeople % 2 == 1 {
        print("numberOfPeople is odd")
    }
} else {
    print("numberOfPeople is nil")
}
```


## Question 15

Given the array of optional Ints `someNumbers`, write code to find the product of the array not including any nil values.

```swift
var someNumbers: [Int?] = []

for i in 0..<20 {
    someNumbers.append(Bool.random() ? i : nil)
}

var product = 1
for num in someNumbers {
    if let num = num {
        product = product * num
    }
}

print(product)
```


## Question 16

Given the array `poorlyFormattedCityNames`, create a new array with the city names capitalized and any nil values removed.

```swift
let poorlyFormattedCityNames: [String?] = ["new york", "BOSTON", nil, "chicago", nil, "los angeles", nil, "Dallas",]

var properlyFormattedCityNames: [String] = []

for city in poorlyFormattedCityNames {
    if let cityName = city {
        properlyFormattedCityNames.append(cityName.capitalized)
    }
}

print(properlyFormattedCityNames)

// Output: ["New York", "Boston", "Chicago", "Los Angeles", "Dallas"]
```


## Question 17

Given a random array of optional numbers, create a new array of all the even numbers that aren't nil.

```swift
var aBunchOfNumbers: [Int?] = []

for _ in 0..<20 {
 aBunchOfNumbers.append(Bool.random() ? Int(arc4random_uniform(102)) : nil)
}
var onlyEvensNoNils = [Int]()

for num in aBunchOfNumbers {
    if let num = num {
        if num % 2 == 0 {
            onlyEvensNoNils.append(num)
        }
    }
}
print(onlyEvensNoNils)

```


## Question 18

Given the following array of zip codes as strings, write code that turns them into an array of Ints.

`let zipCodeStrings = ["11377", "11101", "11373", "10014", "10003", "11223"]`

```swift
let zipCodeStrings = ["11377", "11101", "11373", "10014", "10003", "11223"]
var intZipCodes = [Int]()

for zip in zipCodeStrings {
    intZipCodes.append(Int(zip)!)
}
print(intZipCodes)

```

## Question 19

Some students were asked some questions about their favorite foods and colors and the answers were stored in an array `studentInfo`.

- Print the names of the students that do not have a favorite color.

- Print the names of the students that don't have a favorite color or a favorite food.

- Create a new array of type `[(String, String, String)]` that contains the students with both favorite colors and foods.

`let studentInfo: [(String, String?, String?)] = [("Bill", "Burgers", "Blue"), ("Rita", nil, "Red"), ("Peter", "Pizza", "Purple"), ("Sarah", "Sandwiches", nil), ("Jeff", nil, nil), ("Lucy", "Leftovers", "Lilac"), ("Mike", "Meat", "Mauve"), ("Gemma", nil, "Green")]`

```swift
let studentInfo: [(Name: String, String?, String?)] = [("Bill", "Burgers", "Blue"), ("Rita", nil, "Red"), ("Peter", "Pizza", "Purple"), ("Sarah", "Sandwiches", nil), ("Jeff", nil, nil), ("Lucy", "Leftovers", "Lilac"), ("Mike", "Meat", "Mauve"), ("Gemma", nil, "Green")]

var studentsWithFavFoodColor: [(String, String, String)] = []

for tuple in studentInfo {
    if tuple.2 == nil {
        print("\(tuple.0) does not have a favorite color")
    }
    if tuple.1 == nil {
        print("\(tuple.0) does not have a favorite food")
    }
    if let food = tuple.1, let color = tuple.2 {
        studentsWithFavFoodColor.append((tuple.0, tuple.1!, tuple.2!))
    }
}
print(studentsWithFavFoodColor)
```

## Question 20

Given an optional array of optional tuples of optional UInt8s,

- Write code to safely unwrap and print the tuples in the array with all 3 RGB values.

- Write code that counts all the nil values.

`let possibleColors: [(r: UInt8?, g: UInt8?, b: UInt8?)?]? = [(128, 21, 7), (0, 0, 0), nil, (nil, 25, 82), (255, 255, 255), nil, (200, 100, nil), (120, nil, 23), (0, 255, 106), (nil, nil, nil), nil, (100, 100, 200)]`

```swift
let possibleColors: [(r: UInt8?, g: UInt8?, b: UInt8?)?]? = [(128, 21, 7), (0, 0, 0), nil, (nil, 25, 82), (255, 255, 255), nil, (200, 100, nil), (120, nil, 23), (0, 255, 106), (nil, nil, nil), nil, (100, 100, 200)]

var nilTracker = 0

for element in possibleColors! {
    if let tuple = element {
        if let r = tuple.0, let g = tuple.1, let b = tuple.2 {
            print((tuple.0!, tuple.1!, tuple.2!))
        } else {
            if tuple.0 == nil {
                nilTracker += 1
            }
            if tuple.1 == nil {
                nilTracker += 1
            }
            if tuple.2 == nil {
                nilTracker += 1
            }
        }
    } else {
        nilTracker += 1
    }
}
print("Number of nil values: \(nilTracker)")
```


## Question 21

Consider the following nested optional. It corresponds to a number inside a box inside a box inside a box.

- Fully force unwrap and print number.

- Optionally bind and print number.

```swift
let number: Int??? = 10

//fully force unwrapped
print(number!!!)

//optionally bound
if let number = number {
    if let number = number {
        if let number = number {
            print(number)
        }
    }
}

```

## Question 22

Given an Array of Optional Strings, write code that concatenates all non-nil values together except for strings with 3 or more vowels.

`let monkeyingAround = ["orangutan", "apes",nil, "monkeys", "gorillas", "lemurs", nil]`

output: `"apesmonkeyslemurs"`

```swift
let monkeyingAround = ["orangutan", "apes",nil, "monkeys", "gorillas", "lemurs", nil]
let vowels = "aeiou"
var countVowels = 0
var newString = ""

for word in monkeyingAround {
    //reset vowel counter back to 0 for each iteration of word through array
    countVowels = 0
    //checks if the element in the array has a value, and not nil
    if let word = word {
        //counts how many vowels are in the word
        for char in word {
        if vowels.contains(char) {
        countVowels += 1
            }
        }
        //skip this word iteration if it has 3 or more vowels
        if countVowels >= 3 {
            continue
        } else {
            newString += word
        }
    }
}
print(newString)

```


## Question 23

Given the value below, print out all of the non-nil Ints it contains by accessing each of them.

`var strangeStructure: ([Int]?, [[Int?]], [[Int]?], Int)? = ([1], [[2,3,4],[],[5,nil],[nil]], [nil, [6,7,8],nil,[],[9]], 10)`

```swift
var strangeStructure: ([Int]?, [[Int?]], [[Int]?], Int)? = ([1], [[2,3,4],[],[5,nil],[nil]], [nil, [6,7,8],nil,[],[9]], 10)

if let strangeStructure = strangeStructure {
    //prints fisrt array in the tuple "strangeStructure"
    if let firstArray = strangeStructure.0 {
        print(firstArray)
    }
    //prints non-nil elements in the second array
    for element in strangeStructure.1 {
        for subElement in element {
            if let subElement = subElement {
                print(subElement)
            }
        }
    }
    //prints non-nil integers/ arrays in the third array
    for element2 in strangeStructure.2 {
        if let subElement2 = element2 {
            print(subElement2)
        }
    }
    //prints last part of tuple because it is definitely an Int
    print(strangeStructure.3)
}
```
