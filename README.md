# Regex-Hex-Tutorial

# Regex : Hex Value Tutorial 
The hexadecimal (also known as base 16 or hex) is a positional numeral system that uses 16 distinc symbols. The symbols are "0"-"9" to represent values 0 to 9 and "A"-"F", or "a"-"f", to represent values 10 to 15.

One of the many uses of the hex system are hex color codes. A hex color code is a hexadecimal representation of a color in RGB format. RGB format defines a color by the amount of red, green and blue.

In some cases we can define a hex color code using only three characters. This can be used when the same character is used twice to represent each value in the RGB combination. For example: `#FFCC00` can be rewritten as `#FC0`. Depending on the application, the numeral sign can also be left out of the hex code.

## Summary
We are going to take a look at a regular expression to match any hexadecimal code in a strign of characters. 

A regular expression, or regex, is a sequence of characters that defines a search pattern for text. Those characters can be literal characters or meta characters. To built regex we often use meta characters, which represent a wider set of characters.

The regex that we are going to analyze is:
`/^#?([a-f0-9]{6}|[a-f0-9]{3})$/`

This particular regex allows us to find any hex code, whether it begins with a numeral sign (#) or not, and whether it has 6 or 3 characters (digits and leters) in it. 

## Table of Contents

- [Anchors](#anchors)
- [Quantifiers](#quantifiers)
- [Grouping Constructs](#grouping-constructs)
- [Character Classes](#character-classes)
- [The OR Operator](#the-or-operator)

## Regex Components

### Anchors
In this particular case we are using two anchors or position meta characters in our regex: `^` and `$`.
The `^` meta characters represents the beginning of string or a line, and the `$` represents the end of a string or a line. For example, `^abc` will match any line or string that begins with abc, while `xyz$` will match any line or string that ends with xyz.
Our regex uses these particular characters in combination to make sure that we are maching the full expresion from beginning to end.

### Quantifiers
This regex uses two types of quantifiers: `?` and `{n}`.

The `?` quantifier matches any preceding character 0 or 1 times. This makes the `?` a sort of conditional inside regex. In our regex, since `?` is preceded by #,  our expression will match either a string that begins with # or not.
The other quantifier used in our regex is `{n}`, which is used twice (`{6}` and `{3}`). This meta character matches exactly the preceding character n-times.

### Grouping Constructs
This regex expresion has one big group: `([a-f0-9]{6}|[a-f0-9]{3})`. This grouping is used alongside an OR Operator, which will be covered in that section
### Character Classes
In our regex we have one character class that is repeated twice: `[a-f0-9]`. A character class matches any character enclosed in brackets. For example: `[abc]` will match "a" or "b" or "c". `[-.]` will match "-" or ".". 

Inside our character class we have two ranges: `a-f` and `0-9`. This means that it maches any character "a" through "f" (lowercase, it won't match uppercase), and "0" through "9".  Other examples: `[m-p]` matches "m", "n", "o" or "p". `[3-5]` matches "3", "4" or "5".
### The OR Operator
As I mentioned in the grouping section, our regex has one big group, divided by an OR operator `|`. In the group `([a-f0-9]{6}|[a-f0-9]{3})` we have two expresions: `[a-f0-9]{6}` and `[a-f0-9]{3}`. This means that our regex will match any of those two expresions. 

In conclusion our regex `/^#?([a-f0-9]{6}|[a-f0-9]{3})$/`, would be described as follows:

"Every sequence of characters that starts with # or not, followed by 6 charcaters "a" through "f" and "0" through "9", OR followed by 3 charcaters "a" through "f" and "0" through "9"."
## link to gist

https://gist.github.com/aali9/6c6289fd08c5a7737c4d0cc4d76d987c

## Author



Anfal Ali
[GitHub](https://github.com/aali9)