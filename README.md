# Deriv Flutter Team Coding Conventions

## what are coding conventions?

Coding conventions are a set of guidelines for a specific programming language that recommend programming style, practices, and methods for each aspect of a program written in that language.

These conventions usually cover file organization, indentation, comments, declarations, statements, white space, naming conventions, programming practices, programming principles, programming rules of thumb, architectural best practices, etc. These are guidelines for software structural quality.

Software programmers are highly recommended to follow these guidelines to help improve the readability of their source code and make software maintenance easier.

## Code Style

---

## Identifiers

Identifiers come in three flavors in Dart:

1.  `UpperCamelCase` names capitalize the first letter of each word, including the first.

    - classes, enum types, typedefs, extensions, and type parameters should capitalize the first letter of each word (including the first word), and use no separators.

2.  `lowerCamelCase` names capitalize the first letter of each word, except the first which is always lowercase, even if it’s an acronym.

    - class members, top-level definitions, variables, parameters, and named parameters should capitalize the first letter of each word except the first word, and use no separators.
    - constant variables, including enum values.

3.  `lowercase_with_underscores` names use only lowercase letters, even for acronyms, and separate words with underscores.

    - libraries, packages, directories, and source files names.
    - import prefixes.

```dart
Good:

    import 'dart:math' as math;
    import 'package:angular_components/angular_components.dart' as angular_components;
```

NOTE:

- Capitalize acronyms and abbreviations longer than two letters like words. (exception: Two-letter acronyms like `IO`, `UI` are fully capitalized.)

```dart
Good:

    class HTTPClient {}
    class UIHandler {}
    class IdGenerator {}

    int userId;
    UIHandler uiHandler;
```

- Using `_, __, etc.` for unused callback parameters.

```dart
Good:

    futureOfVoid.then((_) => print('Operation complete.'));
```

- DON’T use a leading underscore for identifiers that aren’t private.
- DON’T use prefix letters.

```dart
Good:
    const int defaultTimeout = 60;

Bad:

    const int kDefaultTimeout = 60;
```

---

## Ordering imports and exports

- Place `dart` imports before other imports.
- Place `package` imports before relative imports.
- Specify `exports` in a separate section after all imports.
- Sort `sections` alphabetically.

```dart
Good:

    import 'dart:async';
    import 'dart:html';

    import 'package:bar/bar.dart';
    import 'package:foo/foo.dart';

    export 'src/error.dart';
    export 'src/exception.dart';
```

---

## Formatting

change your code to make it more formatter-friendly, The formatter does the best it can with whatever code you throw at it, but it can’t work miracles. If your code has particularly long identifiers, deeply nested expressions, a mixture of different kinds of operators, etc. the formatted output may still be hard to read.

- avoid lines longer than 80 characters.
- use curly braces for all flow control statements.

```dart
Good:

    if (isWeekDay) {
        print('Bike to work!');
    } else {
        print('Go dancing or read a book!');
    }

    if (condition) {
      doSomething();
    }
```
