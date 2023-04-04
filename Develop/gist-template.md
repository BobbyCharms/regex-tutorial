# Regular Expressions (Regex) - Tutorial on Matching an Email 

This tutorial will walk through the various components of Regular Expressions, also known as Regex. Specifically, it will focus on how one might use Regex to match and email. The Regex for this is `/^([a-z0-9_\.-]+)@([\da-z\.-]+)\.([a-z\.]{2,6})$/`. Below, we'll explain how this breaks down into each section and git context into what it's doing. 

## 
Summary of Regex 
Regular expressions or regex is a sequence of characters that can be used for matching a pattern. It can be used to match certain characters, strings, or patterns of characters within a larger text body. Regex is used in many languages, like Javascript, and in text editors, such as Word or Google Docs. 

Regex consists of several characters, including literal, special, and metacharacters. iteral characters are used to match specific characters in a string, such as "a", "b", "c", and so on. Special characters are used to match a specific set of characters, such as "\d" for any digit or "\s" for any whitespace character. Metacharacters are used to define patterns, such as "*" for any number of occurrences or "?" for optional characters.

Regex can be used to search for many different patterns within a text. Some common use cases include emails, phone numbers, or finding a specific word within a larger body of text. 


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
- [Look-ahead and Look-behind](#look-ahead-and-look-behind)

## Regex Components

Regex is considered literal. In order to do this syntactically, the regex pattern must be wrapped in `/`, as per this example which would be the regex for an email: `/^([a-z0-9_\.-]+)@([\da-z\.-]+)\.([a-z\.]{2,6})$/`. 

### Anchors
Anchors begin or end a string in regex. The symbol `^` is the start of the string and the string is then ended by a `$` symbol. For the purposes of an email, the pattern would look like `/^regex pattern$/`.

### Quantifiers
Quantifiers provide guidelines on the frequency of a pattern match. For the purposes of an email, we could use limitations on the length of the unique email or the length of the domain name. Quantifiers are denoted by using the `{}` symbols. The coding boot camp article for regex of a username provides the following specifications on quantifiers: 
They include the following:

*—Matches the pattern zero or more times

+—Matches the pattern one or more times

?—Matches the pattern zero or one time

Examples: 
{ n }—Matches the pattern exactly n number of times

{ n, }—Matches the pattern at least n number of times

{ n, x }—Matches the pattern from a minimum of n number of times to a maximum of x number of times

For an email, this is the `{2,6}` which means that the domain can be between 2-6 characters in length

### OR Operator
The OR operator `|` allows for there to be multiple patterns that could be a match. For the purpose of an email, this could be used to ensure the email is a specific type of domain such as `com|net|org|edu` etc. 

### Character Classes
Character classes are used to specify the characters that are allowed to be matched in a given pattern. In our example, we see `[a-z0-9_\.-]` listed as the characters allowed for a unique email name. This means that the lowercase characters a-z as well as the numerical characters 0-9 and the special characters `_\._` could all be included in the unique name for the email. 

### Flags
Flags are used for different options for a regex pattern. For emails, we could use the `i` case to make the pattern case insensitive. As shown here: 
`/^([a-z0-9_\.-]+)@([\da-z\.-]+)\.([a-z\.]{2,6})$/i`

### Grouping and Capturing
Grouping allows you to break up the pattern into different pieces. In the context of an email, we have three groups, denoted by the `()` around each group. 

Group 1 - the unique email name: `([a-z0-9_\.-]+)`
Group 2 - the domain name: `([\da-z\.-]+)`
Group 3 - the second part of the domain name: `([a-z\.]{2,6})`

### Bracket Expressions
Bracket expressions allow for matching a set of characters. Very similar to character classes, this is the specific denotation that marks what is allowed in a given pattern. `[a-z0-9_\.-]` is an example of a bracket expression, with the character classes inside being the characters that can be matched in this pattern. 

### Greedy and Lazy Match
Put simply, greedy patterns will match as many patterns as possible while lazy will match as few as possible. Greedy matching is the default behavior for regex. For an email, we might want to include the `?` match indicator to identify it as lazy so that it only matches the email without including extra characters like an empty space. 

### Boundaries
Boundaries, in the context of an email match, can be used similarly to greedy or lazy match. For our purposes, we would include the boundaries around the email regex. That might look something like: `/\b([a-z0-9_\.-]+)@([\da-z\.-]+)\.([a-z\.]{2,6})\b/`

### Look-ahead and Look-behind
These are denoted by (?=pattern)" and "(?<=pattern)", respectively. For an email, they might be used to ensure that the username and domain name is valid. An example would be: `/(?<=^| )([a-z0-9_\.-]+)@([\da-z\.-]+)\.([a-z\.]{2,6})(?=$| )/`

## Author

This article was written by Robert Charming, github: https://github.com/BobbyCharms. The article references https://coding-boot-camp.github.io/full-stack/computer-science/regex-tutorial and used OpenAI to explain some of the concepts to the author. 
