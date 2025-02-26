# Dart Programming Language Documentation

## Introduction
Dart is a client-optimized programming language developed by Google, designed for building web, mobile, and desktop applications. It is primarily used for **Flutter** development and supports features like just-in-time (JIT) and ahead-of-time (AOT) compilation.

## Key Features
- **Optimized for UI Development**: Designed for front-end development, especially with Flutter.
- **Strongly Typed**: Supports both static and dynamic typing.
- **Asynchronous Programming**: Built-in support for `Future` and `Stream`.
- **Garbage Collection**: Automatic memory management.
- **Cross-Platform**: Runs on mobile (iOS, Android), web, desktop, and backend servers.

## Installation
### 1. Install Dart SDK (Standalone)
#### Windows (via Chocolatey):
```sh
choco install dart-sdk
```
#### macOS (via Homebrew):
```sh
brew install dart
```
#### Linux (via Snap):
```sh
sudo snap install dart --classic
```

### 2. Install Dart with Flutter
Dart comes bundled with Flutter. Install Flutter, and Dart will be available automatically:
```sh
git clone https://github.com/flutter/flutter.git -b stable
export PATH="$PWD/flutter/bin:$PATH"
```

## Writing Your First Dart Program
```dart
void main() {
  print('Hello, Dart!');
}
```
Save the file as `main.dart` and run it using:
```sh
dart run main.dart
```

## Dart Basics
### 1. Data Types
Dart supports the following data types:
- **Numbers** (`int`, `double`)
- **Strings** (`String`)
- **Booleans** (`bool`)
- **Lists** (`List`) - Ordered collection of elements.
- **Maps** (`Map`) - Key-value pair storage.
- **Sets** (`Set`) - Unique collection of items.
- **Null** (`null`) - Represents a missing value.

Example:
```dart
void main() {
  int age = 25;
  double pi = 3.14;
  String name = "Dart";
  bool isAwesome = true;
  List<String> colors = ["Red", "Green", "Blue"];
  Map<String, int> scores = {"Alice": 90, "Bob": 85};
  
  print("Name: $name, Age: $age, Pi: $pi");
  print("Colors: $colors, Scores: $scores");
}
```

### 2. Conditional Statements
Dart supports `if-else`, `switch`, and ternary operators.
```dart
void main() {
  int num = 10;
  
  if (num % 2 == 0) {
    print("Even Number");
  } else {
    print("Odd Number");
  }
}
```

### 3. Loops
Dart provides different loops for iteration:
- **For loop**
- **While loop**
- **Do-while loop**

Example:
```dart
void main() {
  for (int i = 0; i < 5; i++) {
    print("Iteration: $i");
  }
}
```

### 4. Functions
Functions help in modularity and reusability.
```dart
double add(double a, double b) {
  return a + b;
}

void main() {
  print("Sum: \${add(5, 3)}");
}
```

### 5. Classes and Objects
```dart
class Car {
  String brand;
  int year;
  
  Car(this.brand, this.year);
  
  void display() {
    print("Brand: $brand, Year: $year");
  }
}

void main() {
  Car myCar = Car("Tesla", 2022);
  myCar.display();
}
```

## Data Structures and Algorithms (DSA)
Dart provides built-in data structures and allows implementing custom algorithms.

### 1. Lists (Arrays)
```dart
void main() {
  List<int> numbers = [1, 2, 3, 4, 5];
  numbers.add(6);
  print(numbers);
}
```

### 2. Stacks (LIFO)
```dart
class Stack<T> {
  List<T> _list = [];
  
  void push(T value) => _list.add(value);
  T pop() => _list.removeLast();
}

void main() {
  Stack<int> stack = Stack<int>();
  stack.push(1);
  stack.push(2);
  print(stack.pop());
}
```

### 3. Queues (FIFO)
```dart
import 'dart:collection';
void main() {
  Queue<int> queue = Queue<int>();
  queue.addLast(1);
  queue.addLast(2);
  print(queue.removeFirst());
}
```

### 4. Searching Algorithms
#### Binary Search
```dart
int binarySearch(List<int> list, int target) {
  int left = 0, right = list.length - 1;
  while (left <= right) {
    int mid = left + (right - left) ~/ 2;
    if (list[mid] == target) return mid;
    if (list[mid] < target) left = mid + 1;
    else right = mid - 1;
  }
  return -1;
}
```

### 5. Sorting Algorithms
#### Bubble Sort
```dart
void bubbleSort(List<int> list) {
  for (int i = 0; i < list.length; i++) {
    for (int j = 0; j < list.length - i - 1; j++) {
      if (list[j] > list[j + 1]) {
        int temp = list[j];
        list[j] = list[j + 1];
        list[j + 1] = temp;
      }
    }
  }
}
```

## Asynchronous Programming
Dart supports async/await for handling asynchronous operations efficiently.
```dart
Future<String> fetchData() async {
  await Future.delayed(Duration(seconds: 2));
  return "Data received";
}

void main() async {
  print("Fetching data...");
  String data = await fetchData();
  print(data);
}
```

## Dart Package Manager (pub)
Dart uses `pub` to manage dependencies.
- Initialize a project: `dart create my_app`
- Add a package: `dart pub add http`
- Get dependencies: `dart pub get`

## Conclusion
Dart is a powerful language optimized for UI development with a simple syntax, asynchronous support, and strong typing. It is widely used with Flutter to build cross-platform applications.

For more details, visit [Dart's official documentation](https://dart.dev).

