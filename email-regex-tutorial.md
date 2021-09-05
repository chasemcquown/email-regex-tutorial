# Email Regex Tutorial

The purpose of this tutorial is to explain the different components of a regex. We'll cover how these different components can be pieced together to find strings within a block of text.

## Summary

The regex that will be covered in the following tutorial can be used to identify emails. Each portion of this regex `/^([a-z0-9_\.-]+)@([\da-z\.-]+)\.([a-z\.]{2,6})$/` plays an important role in identifying the key parts of what make up an email address.

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

Anchors, such as ^, represent the beginning of a string. When you use ^, this will instruct the regex to to start at the beginning of the string and match the characters that follow the ^. Take this regex for matching an email as an example `/^([a-z0-9_\.-]+)@([\da-z\.-]+)\.([a-z\.]{2,6})$/`. The $, which is also an anchor, will instruct the regex to match anything before the $, which indicates the end of the line. In other words, the ^ and the $ tell the regex to match any of the specified characters between them.

### Quantifiers

Quantifiers, tell the regex how many matches of a character or grouping of characters must be found. In the email example, we use + twice, which is telling the regex to match one or more of the characters we included in the grouping. We us it at the end of the first grouping , as seen here: `([a-z0-9_\.-]+)` and at the end of the second goruping, as seen here: `([\da-z\.-]+)`

### OR Operator

In the email example we use [] as an or operator. In our case, we will match any strings with either the characters a-z, the numbers 0-9 or an underscore, backslash, period, or hyphen. We used square brackets in the first grouping: `[a-z0-9_\.-]`, the second grouping: `[\da-z\.-]`, and the third goruping: `[a-z\.]`.

### Grouping and Capturing

In the regex for matching emails, we use () 3 seperate times. The parentheses are used before the at symbol, in between the at symbol and the period, and after the period. The parentheses are used to match the characters inside of them. This is advantageous since it allows us to use regex operators on whatever characters are grouped together. Before the @ sign: `([a-z0-9_\.-]+)`, after the @ sign: `([\da-z\.-]+)`, and at the end of our string: `([a-z\.]{2,6})`. You may also notice the use of the + quantifier that we were able to apply to gorupings when needed.

### Bracket Expressions

We used bracket expressions in the email example as an or operator. We did so in order to match any of the characters that we included inside of the brackets, and exclude any of the characters that we didn't include. We used square brackets in the first grouping: `[a-z0-9_\.-]`, the second grouping: `[\da-z\.-]`, and the third goruping: `[a-z\.]`.

### Greedy and Lazy Match

The + quantifier is an example of a greedy match, since we want as many matches as we can possibly get, which is why it's used in the email regex. A ?, although not included in the email example, would be an example of a lazy match. This is because it will match something as many times as it appears in the a string. Our greedy matches can be seen here in the first grouping: `([a-z0-9_\.-]+)`, and here in the second grouping: `([\da-z\.-]+)`.

## Author

Made with ❤️ by Chase McQuown. [My GitHub](https://github.com/chasemcquown)
