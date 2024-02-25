# MAD - Exercise 01
## Tasks
* Watch the Kotlin Crashcourse Video in Moodle or complete the tutorials **[Introduction to programming in Kotlin](https://developer.android.com/courses/pathways/android-basics-compose-unit-1-pathway-1)** and **[Kotlin fundamentals](https://developer.android.com/courses/pathways/android-basics-compose-unit-2-pathway-1
)**.
* Answer the questions inside this Readme.md file and push it to your repository.
* Submit your coding solution of the Number Guessing Game inside the repository.
* Submit the link to your repository in Moodle.

## Questions
### Describe how Kotlin handles null safety. What are nullable types and non-null types in Kotlin? (0,5 points)

Kotlin differs between nullable types and non- nullable types.
non-nullable types are variables that can’t hold null.
```kotlin
val a: String = "value" // non-null type
print(a.length)
```
output:
```kotlin
5
```
nullable types are variables that can hold null.
```kotlin     
val b: String? = "value" // nullable type
b = null
print(b?.length)
```
output:
```kotlin
null
```
In some of the other languages null can cause many problems with Runtime null-pointer-exceptions. Kotlin is Null safe because it has an operator, the ```
 .?```, that tells the compiler that the variable could be null. By doing this if the value gets assigned/reassign null the program won’t crash or throw a null pointer exception. Its stopping any operations with that variable and replaces it with the ```null``` value. Kotlin don’t defaults nullability because of convenience with java objects.

### What are lambda expressions and higher order functions in Kotlin? Why would you store a function inside a variable? (0,5 points)

Lambda expressions are functions that are used like variable values. You can pass functions und return functions with lambda expressions they also can be handled with the ```.?``` operator to provide null safety.
```kotlin
val treat: () -> Unit =              // () -> Unit is the Datatype  
    { println("Have a treat!") }    // this is the value, a function
```
Higher order functions are functions that return a function or takes functions as an argument.
like the ```repeat()``` function. You would store a function inside a variable to make the code more readable, dynamic, and concise.

### Provide a solution for the following number guessing game inside `App.kt`. (3 points)

## Number Guessing Game in Kotlin
The game is a simple number guessing game. The task is to generate a random, max 9-digit, number. The number must **not contain repeating digits**. Valid digits are 1-9.
Ask the user to guess the max 9-digit number. The game is finished when the user guesses the correct digits in the correct order.
In each round, the user gets feedback about the number of correct digits and the number of correct digits in the correct position.
The output should be in the format "n:m", where "n" is the number of digits guessed correctly regardless of their position, 
and "m" is the number of digits guessed correctly at their correct position. Here are some examples:

This example shows the game flow with 4-digits to guess (the default argument)

Generated number: 8576
-	User input: 1234, Output: 0:0
-	User input: 5678, Output: 4:1
-	User input: 5555, Output: 1:1
-	User input: 3586, Output: 3:2
-	User input: 8576, Output: 4:4 -> user wins

Take a look into the provided code structure in `src/main/kotlin/App.kt`. Implement the following methods (lambda expressions):
- _playNumberGame(digitsToGuess: Int = 4)_ (1 point): The main game loop that handles user input and game state. Make use of _generateRandomNonRepeatingNumber_ and _checkUserInputAgainstGeneratedNumber_ here. This function also utilizes a default argument 
- _generateRandomNonRepeatingNumber_ (1 point): A lambda expression that generates a random number with non-repeating digits of a specified length.
- _checkUserInputAgainstGeneratedNumber_ (1 point): A lambda expression that compares the user's input against the generated number and provides feedback.

``CompareResult.kt`` This class is a data structure which helps with bundling the result of the comparison of the user input and the generated number. Look at the toSting() and use it in your output.

Run the project with `./gradlew run` and test your implementation with the provided tests in `src/test/kotlin/AppTest.kt` with `./gradlew test`.

# Project Structure
The project is structured into two main Kotlin files:

**App.kt**: Contains the main game logic and functions.

**AppTest.kt**: Contains unit tests for the various functions in App.kt.

