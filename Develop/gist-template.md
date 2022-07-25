# Computer Science for JavaScript Challenge: Regex Tutorial

So the purpose of this gist is to explain how a specific regex works and we will also go over how it works in general. 

## Summary

```
/^([a-z0-9_\.-]+)@([\da-z\.-]+)\.([a-z\.]{2,6})$/ 
```
Above in the code snippet, is the regex example that will be explained in this tutorial. This regex is specific to the pattern of an email. 

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
So basically the most common pattern of an email address is composed of 4 main groups, and they are:
- String of characters and/or digits and/or dots, hyphens and/or underscores
- The at sign (@)
- The domain name that can be a string of characters and/or digits
- The extension preceeded by a dot (.)

### Anchors
So basically anchors are used to contain the email expression. So looking at the example, we see that `^` is in the beginning, and `$` is at the end.
### Quantifiers
So my understanding is that the `+` character will match one or more of what we are searching for. So `[a-z0-9_\.-]+` means any characters of `[a-z0-9_\.-]` and more will be a matching record
### OR Operator
So the OR operator `|` or `[]` definition is any charaters specified between the opening and closing brackets will be matched. So in our email example, there are actually 3 times this occurs. 
So the first bracket expression is `[a-z0-9_\.-]` and what this means is that this includes case sensitive characters from a-z, numbers from 0-9, also an underscore, as well as periods and hyphens. The second bracket expression is`[\da-z\.-]`   and what this means is that it includes all digits `/d`, case sensitive characters from a-z, periods and hyphens. The last bracket expression is`[a-z\.]` and this one means that it includes case sensitive characters from a-z and periods.
### Character Classes
In the email example expression, the character class `/d` is used when we want to match any digit from 0 to 9.
### Flags
ok so my understandin is that flags affect the match result. There are 3 of them in this email example. 
```
i
With this flag the search is case-insensitive: no difference between A and a.

g
With this flag the search looks for all matches, without it – only the first match is returned.

m
With this flag, when enabled (^) and ($) will match the start and end of a line instead of the whole string.
```
### Grouping and Capturing
ok so in the email example, there are 3 groups being captured. Group 1 is the username which is `[a-z0-9_\.-]`.
the second one is the email service being used `[\da-z\.-]`.
third is the domain extention, so like .com or .net or .gov. `[a-z\.]{2,6}`
### Bracket Expressions
So the bracket expression `[]` indicate a set of characters to match. 

### Greedy and Lazy Match
So in the email example we use the greedy quantifiers `+` and `{}`, which means it allows the match to expand. 

### Boundaries
It sounds like Boundaries such as `/b` and `/B` are anchor like such as `$` and `^`. My understanind is, they perform a "whole words only" search. There does not appear to be any in the email example.
### Back-references
So my understanding is that Back-references provide a way to identify a repeated character within a string. 
### Look-ahead and Look-behind
So it sounds like Look-ahead and Look-behind, collectively called “lookaround”, search for a set of 2 criteria in sequence and returns a match for whatever is in "ahead" or "behind" it depending on the criteria specified in the regex.
## Author

If you have any question, reach out to me at my [github profile](https://github.com/VN135766)
