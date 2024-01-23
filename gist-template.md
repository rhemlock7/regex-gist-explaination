# Computer Science for JavaScript: Regex Tutorial

Regular Expressions (Regex) are a powerful tool enabling developers to create patterns for string matching. 

In this tutorial, I provide a comprehensive breakdown of the regex required to validate a VISA credit card. This regex ensures that a given string represents a valid VISA credit card so that customers do not enter fake credit cards and steal a company's product.

We will dive into components of regex, such as anchors, quantifiers, grouping constructs, bracket expressions, character classes, the OR operator, flags, and character escapes.

## Summary

The regex pattern needed to find a VISA credit card looks something like this:

    /^4[0-9]{12,15}$/

The pattern above checks for a string that starts with a '4' and is followed by 12 to 15 digits. This regex captures the common format of VISA credit cards.

If we wanted to find any credit card, our regex would have to be much broader. All VISA credit cards start with the number 4 followed by 12-15 digits, making it easier to identify.

If a string matches this expression it will return a boolean (true/false). This helps developers when creating conditional statements later on.

## Table of Contents

- [Anchors](#anchors)
- [Quantifiers](#quantifiers)
- [Grouping Constructs](#grouping-constructs)
- [Bracket Expressions](#bracket-expressions)
- [Character Classes](#character-classes)
- [The OR Operator](#the-or-operator)
- [Flags](#flags)
- [Character Escapes](#character-escapes)

## Regex Components
Regex components are the building blocks for creating regular expressions. They include various symbols/characters that form a pattern for matching strings.

Here's a breakdown from our VISA credit card example earlier:

    /^4[0-9]{12,15}$/

- ^: Anchors the pattern at the beginning of the string.
- 4: Matches the digit '4', indicating VISA.
- [0-9]{12,15}: Matches between 12 and 15 digits from (0-9).
- $: Anchors the pattern at the end of the string.
- /: Wraps the entire expression to indicate it is regex.

### Anchors
With regex, anchors represent the a specific position within a string. In our example, the ^ symbol matches the start of the string, ensuring that the pattern following it occurs at the beginning. The $ symbol matches the end of the string to represent the end of the expression.

Here are a few more examples of anchors:

- \b - Word Boundary Anchor:
    - Asserts a word boundary.

- \B - Non-Word Boundary Anchor:
    - Asserts a non-word boundary.

- \A - Start of String Anchor:
    - Asserts the start of the string.

- \Z - End of String Anchor:
    - Asserts the end of the string, or before the newline at the end of the string.

### Quantifiers
Quantifiers in regex specify the quantity of characters or groups. They provide flexibility in defining patterns by indicating the number of times certain characters may occur.

Our VISA credit card example contains this quantifier:

    {12,15}

It specifies that there must be between 12 and 15 occurrences of the preceding digits. This is important because anything shorter or longer would not be a valid credit card number.

### Grouping Constructs
Grouping constructs in regex allow you to create sub-patterns and apply quantifiers to them as a whole. They are enclosed in parentheses ().

Our credit card example does not contain grouped contructs, but here are a few other examples:

##### ( ... ) - Capturing Group:
Groups elements together and captures the matched portion for back-referencing.

    /(ab)+/

##### (?: ... ) - Non-Capturing Group:
Groups elements without capturing for back-referencing.

    /(?:ab)+/


### Bracket Expressions
Bracket expressions define a character set, and the pattern matches any single character from that set.

In our VISA credit card example brackets are used, but they are NOT a bracket expression. Our VISA example uses [0-9] instead of something like [a-z]. The difference is we are using digits instead of letters.

Here is an example that allows you match for vowels:

    /[aeiou]/

### Character Classes
Character classes can look like this, \d, and they offer a concise way to represent common sets of characters.

For example, \d is a shorthand notation to match any digit in an expression. Predefined categories for specific characters can enhance readability and streamline the construction of complex patterns.

### The OR Operator
The OR operator (|) in regular expressions is an alternative matching mechanism for multiple patterns that matches the one on the left or the right. 

For example, cat|dog matches either "cat" or "dog".

This flexibility is particularly useful when there are several valid alternatives for a particular pattern.

### Flags
Flags in regular expressions modify the behavior of the pattern matching process. Flags offer control over case sensitivity, global search, and other aspects, tailoring the matching behavior to specific requirements.

Common flags include "g" for global search, "i" for case-insensitive search, and "m" for multiline matching. There are no flags in our VISA credit card example.


### Character Escapes
In regex, character escapes are used to represent characters with special meanings, allowing them to be matched literally. The backslash \ serves as the escape character, followed by a character or sequence that represents a special character.

These escapes are useful when you want to match specific characters literally, even if they have special meanings in regex. For instance, \d allows you to match a digit without interpreting it as a quantifier or special character.

Here are a few examples of Character Escapes:
- \d - Digit Escape:
    - Matches any digit (equivalent to [0-9]).
- \w - Word Character Escape:
    - Matches any word character (alphanumeric or underscore).
- \s - Whitespace Character Escape:
    - Matches any whitespace character (spaces, tabs, line breaks).
- \\. - Dot Escape:
    - Matches a literal dot (period).

## Author
My name is Ryan Hemlock. I am a web developer student with the University of Pennsylvania's LPS coding bootcamp. You can find my GitHub profile here: https://github.com/rhemlock7 
