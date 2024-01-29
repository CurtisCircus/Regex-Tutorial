# Regex Tutorial

Programming is a medium of creation that requires a lot of fine tuning within detail. There are plenty of times withing an application the program needs to be aware of certain combinations of letters, numbers, characters, and more. When it comes to words a developer doesn't want users to be able to use, to the requirements in passwords when making an account, developers don't have the time or code to spare to list out every possibly string of characters that the application can or can't accept. Regular Expressions, or Regex, is what saves so many developers time and effort in being able to have their applications be able to identify patterns in strings that need to be targeted for one reason or another.

## Summary

Since regex can cover practically any amount of information, this tutorial will only be covering the regex for matching Hex values.

/^#?([a-f0-9]{6}|[a-f0-9]{3})$/

To properly explain this regex, this tutorial will cover what every symbol or group of symbols are doing, and what they're called within the terms of a regex.

## Table of Contents

- [Anchors](#anchors)
- [Quantifiers](#quantifiers)
- [OR Operator](#or-operator)
- [Character Classes](#character-classes)
- [Flags](#flags)
- [Grouping and Capturing](#grouping-and-capturing)
- [Bracket Expressions](#bracket-expressions)
- [Greedy and Lazy Match](#greedy-and-lazy-match)
- [Boundaries](#boundaries)
- [Back-references](#back-references)
- [Look-ahead and Look-behind](#look-ahead-and-look-behind)

## Regex Components

### Anchors

Anchors are used to declare the beginning and the end of the regex, to declare the beginning of the regex it would start with ^, and to declare the end of the regex it would end with $. Every regex is wrapped in / for the application to be able to read the regex as a regex. So for the Matching Hex Code regex to tell the program to read the line as a regex, write "/", to start the regex "^" to signify that the regex is starting, and when finished with the regex code write "$" and end it off with another "/" to signify to the program to stop reading for regex.

So in total "/^"..."$/" would be the start and the end of the regex with ^ and $ being the anchors.

### Quantifiers

Quantifiers are the sections of regex's that allows the amount of digits in the regex results, these are usually placed after the code defines what characters they accept in the code. In this regex code, the quantifiers are {6} and {3}, which means that for the first section of code will identify 6 characters and then identify 3 after that.

With what's been described so far, the regex code is "/^"..."{6}"..."{3}"..."$/"

There is also ? which is looking a value of 0 or 1, or more sepcifically looking for if what it's defined to is there or not. Since in our code it is after #, it is basically saying that it will identify a hex value with or without a #.

"/^#?"..."{6}"..."{3}"..."$/"

### OR Operator

Or operator is used in regex so that it can select from two or more options within the code. It's used in this code to be able to identify hex codes that have 6 digits or 3 digits, that way the code won't find any invalid code with a number of digits between 3-6.

To write an or opertaor into the regex code it will go right after the {6}, like so: "/^#?"..."{6}|"..."{3}"...$/".

### Character Classes

Character classes is what defined what characters a regex is looking for, in the Matching Hex Code regex it uses a-f0-9, which tells the code that the only digits they're looking for is any combination of letters a-f or numbers 0-9, it doesn't matter if it's all letters, all numbers, or both intermixed as long as the values aren't outside of what is defined. At the beginning this regex code is the # as mentioned earlier, this would usually be paired in with other character classes, as well as any other special characters, but in this case it needs to be placed in a specific spot so it is not included with the other character classes. Mind that regex is looking for very specific requirements, the regex code being used for this example would not include upper case letters since they're not included in the character class.

"/^#?...[a-f0-9]{6}|[a-f0-9]{3}...$/"

### Flags

### Grouping and Capturing

Grouping and Capturing is used to collect whatever contents is in it and use it as a single output. In the Matching Hex Code regex, it is used to get a single value from the or operator explained earlier.

"/^#?([a-f0-9]{6}|[a-f0-9]{3})$/"

### Bracket Expressions

Bracket expressions are used to define the characters the regex is looking for, as said defined before our regex is looking for a-f0-9 so it is held within brackets.

### Greedy and Lazy Match

Greedy and Lazy Matches are different modes of regex searches, greedy is the default way that the regex searches meaning that it is looking for the maximum about of matches for the criteria, whereas the lazy match is looking for the minumum amount of criteria. To use lazy match the program will be looking for ? used after another quantifer. Our example does not use Lazy Match, but instead the default greedy match.

## Author

Written by Curtis, currently taking a Programming Bootcamp. https://github.com/CurtisCircus