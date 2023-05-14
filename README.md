# All syntax patterns in Dart

# all-syntax-pattern-dart

## Can I read code faster?

I started learning programming two months ago, and I've been having a little trouble reading and understanding source code. It's not that I don't understand the concepts; it's just that I'm not used to the syntax patterns of the programming language.

For example, conditional statements are easy to understand in theory. But when you're trying to read them in real code, it’s easy to get lost.

I've had similar experiences in two other areas: English and mathematics.

English is a somewhat arbitrary language. It has patterns, but there are also a lot of exceptions. As a result, there's no quick and easy way to learn to read English sentences fluently. If you want to read English sentences well, you just have to read a lot. That's the only solution.

Mathematics is a bit different. The biggest difference is that the symbols and syntax of mathematical proofs are 100% invented by people to help people. This means that there are common patterns in mathematical language, and understanding these patterns can really boost your reading speed.

I believe that programming is similar to mathematics in its essence. So I've made a list of possible syntax combinations that can be commonly seen in code. I'm hoping that by studying these patterns, I'll be able to improve my reading speed and fluency when it comes to source code.

---

1. **Single line `if` without curly braces**: This is not recommended, but possible when there's only one statement inside the `if` block.
    
    ```dart
    if (condition) statement;
    ```
    
2. **Single line `if` with curly braces**: Recommended for single statements as it improves readability.
    
    ```dart
    if (condition) { statement; }
    ```
    
3. **Multiline `if` with curly braces**: Recommended for multiple statements.
    
    ```dart
    if (condition) {
      statement1;
      statement2;
    }
    ```
    
4. **`if-else` without curly braces**: Not recommended, but possible when both `if` and `else` blocks have only one statement.
    
    ```dart
    if (condition) statement1;
    else statement2;
    ```
    
5. **`if-else` with curly braces**: Recommended, especially when there are multiple statements.
    
    ```dart
    if (condition) {
      statement1;
    } else {
      statement2;
    }
    ```
    
6. **`if-else`+`if-else` combination without curly braces**: Not recommended, but possible for single statements.
    
    ```dart
    if (condition1) statement1;
    else if (condition2) statement2;
    else statement3;
    ```
    
7. **`if-else`+`if-else` combination with curly braces**: Recommended, especially when there are multiple statements.
    
    ```dart
    if (condition1) {
      statement1;
    } else if (condition2) {
      statement2;
    } else {
      statement3;
    }
    ```
    
8. **Ternary operator**: This is an inline `if-else` expression that returns a value based on the condition.
    
    ```dart
    var result = condition ? valueIfTrue : valueIfFalse;
    
    ```
    
9. **Assignment inside `if` conditions**: Dart allows you to perform an assignment inside an `if` condition using the `=` operator.
    
    ```dart
    int number;
    if ((number = getNumber()) != null) {
      print('Got a number: $number');
    }
    ```
    
10. **`if` in Collection**: Dart allows `if` inside collection literals like lists, sets, and maps. This allows you to conditionally include elements.
    
    ```dart
    var includeZero = true;
    var numbers = [if (includeZero) 0, 1, 2, 3];
    ```
    
11. **`if` in Cascades**: Dart allows you to use `if` in a cascade to conditionally apply a cascade operation.
    
    ```dart
    var buffer = StringBuffer()
      ..write('Hello')
      ..write(' ')
      ..write('World')
      ..write('!')
      ..if (includeNewLine) write('\\n');
    ```
    
12. **Null-aware Assignment with `if`**: You can check for `null` values and assign a default value using `if`.
    
    ```dart
    int number;
    if (number == null) {
      number = 10;
    }
    ```
    
    Starting with Dart 2.12, you can use the null-aware assignment operator `??=` to achieve the same thing:
    
    ```dart
    int number;
    number ??= 10;
    ```
    
13. **Nested `if` statements**: `if` statements can be nested inside other `if` statements.
    
    ```dart
    if (condition1) {
      if (condition2) {
        statement;
      }
    }
    ```
    
14. **`if` with `break` and `continue` in loops**: In a loop (like `for`, `while` or `do-while`), you can use `if` with `break` to exit the loop early, or `continue` to skip the rest of the current iteration.
    
    ```dart
    for (var i = 0; i < 10; i++) {
      if (i == 5) break;  // will stop the loop when i equals 5
      if (i % 2 == 0) continue;  // will skip the loop iteration for even numbers
      print(i);
    }
    ```
    
15. **`if` in `switch` statement**: You can use `if` inside the `case` of a `switch` statement to check further conditions.
    
    ```
    switch (value) {
      case 1:
        if (anotherCondition) {
          //...
        }
        break;
      //...
    }
    
    ```
    
16. **`if` with exception handling**: You can use `if` in `try-catch` blocks to handle exceptions conditionally.
    
    ```dart
    try {
      // some code that might throw exceptions
    } catch (e) {
      if (e is SomeSpecificException) {
        // handle the specific exception
      } else {
        // rethrow the exception
        rethrow;
      }
    }
    ```
    
17. **`if` with `assert`**: You can use `if` with `assert` to conditionally check invariants in your code during development.
    
    ```dart
    if (debugMode) {
      assert(someCondition, 'Some condition must be true here');
    }
    ```
    
18. **`if` with `await`**: You can use `if` with `await` in async functions to conditionally await Futures.
    
    ```dart
    Future<void> fetchData() async {
      var data = await getData();
      if (data.isEmpty) {
        data = await getDefaultData();
      }
      // process data
    }
    ```
    
19. **Chained ternary operators**: You can chain ternary operators to create more complex conditional expressions:
    
    ```dart
    var result = condition1 ? value1
                  : condition2 ? value2
                  : defaultValue;
    ```
    
20. **Lambda functions with `if` statement**: You can use `if` statements inside lambda functions:
    
    ```dart
    var numbers = [1, 2, 3, 4, 5];
    numbers.forEach((number) {
      if (number % 2 == 0) {
        print('$number is even');
      }
    });
    ```
    
21. **`if` in string interpolation**: You can use an `if` expression inside string interpolation to conditionally modify a string:
    
    ```dart
    var isMorning = true;
    var greeting = 'Good ${isMorning ? 'morning' : 'day'}';
    ```
    
22. **`if` in initializers**: You can use `if` in initializers, but it's not common and might be difficult to read:
    
    ```dart
    var value = otherValue;
    if (value == null) value = defaultValue;
    ```
    
23. **`if` in recursive functions**: You can use `if` to control the base case in recursive functions:
    
    ```
    int factorial(int n) {
      if (n <= 0) return 1;
      return n * factorial(n - 1);
    }
    
    ```
    
24. **`if` in constructors**: You can use `if` in constructors to validate input:
    
    ```dart
    class Point {
      double x, y;
    
      Point(this.x, this.y) {
        if (x < 0 || y < 0) {
          throw ArgumentError('Both x and y should be non-negative.');
        }
      }
    }
    
    ```
    
25. **`if` with getter and setter**: You can use `if` in a getter or setter to control how an object's properties are accessed or modified:
    
    ```dart
    class Circle {
      double _radius;
    
      double get radius => _radius;
    
      set radius(double value) {
        if (value < 0) {
          throw ArgumentError('Radius cannot be negative.');
        }
        _radius = value;
      }
    }
    
    ```
    
26. **`if` in mixin**: You can use `if` in a mixin, which is a way of reusing a class's code in multiple class hierarchies:
    
    ```dart
    mixin Logging {
      void log(String message) {
        var shouldLog = true;
        if (shouldLog) {
          print('Log: $message');
        }
      }
    }
    ```
    
27. **`if` with extensions**: You can use `if` in an extension to add new functionality to an existing class:
    
    ```dart
    extension on List {
      void customMethod() {
        if (this.isEmpty) {
          print('List is empty');
        } else {
          print('List is not empty');
        }
      }
    }
    
    ```
    
28. **`if` with late variables**: You can use `if` with late variables to check if they've been initialized:
    
    ```dart
    late int number;
    if (number == null) {
      number = 10;
    }
    ```
    
29. **`if` in factory constructors**: You can use `if` in factory constructors to control the instantiation of a class:
    
    ```dart
    class Shape {
      factory Shape(String type) {
        if (type == 'circle') {
          return Circle();
        } else if (type == 'square') {
          return Square();
        } else {
          throw ArgumentError('Invalid shape type: $type');
        }
      }
    }
    ```
    
30. **`if` in callbacks**: You can use `if` in a callback function, which is a function passed as an argument to another function:
    
    ```dart
    Future<void> fetchData(void Function(String) callback) async {
      var data = await getData();
      if (data != null) {
        callback(data);
      }
    }
    ```
    
31. **`if` with enums**: You can use `if` with enums to perform different actions based on the enum value:
    
    ```dart
    enum Status { online, offline, busy }
    
    void printStatus(Status status) {
      if (status == Status.online) {
        print('User is online');
      } else if (status == Status.offline) {
        print('User is offline');
      } else if (status == Status.busy) {
        print('User is busy');
      } else {
        print('Unknown status');
      }
    }
    ```
    
32. **`if` in command-line applications**: In a command-line application, you might use **`if`** to handle command-line arguments:
    
    ```dart
    void main(List<String> arguments) {
      if (arguments.isEmpty) {
        print('No arguments provided.');
      } else {
        print('Provided arguments: $arguments');
      }
    }
    ```
