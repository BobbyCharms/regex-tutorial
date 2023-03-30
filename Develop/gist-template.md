# Regular Expressions (Regex) - Tutorial on Matching an Email 

This tutorial will walk through the various components of Regular Expressions, also known ans Regex. Specifically it will focus on how one might use Regex to match and email. The Regex for this is `/^([a-z0-9_\.-]+)@([\da-z\.-]+)\.([a-z\.]{2,6})$/`. Below, we'll explain how this breaks down into each secesion and git context into what it's doing. 


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

Regex is considered literal. In order to do this syntatically, the regex pattern must be wrapped in `/`, as per this example which would be the regex for an email: `/^([a-z0-9_\.-]+)@([\da-z\.-]+)\.([a-z\.]{2,6})$/`. 

### Anchors
Anchors begin or end a string in regex. The symbol `^` is the start of the string and the stirng is then ended by a `$` symbol. For the purposes of an email, the pattern would look like `/^regex pattern$/`.

### Quantifiers
Quantifiers provide guidelines on the frequency of a pattern match. For the purposes of an email, we could use limitations on the length of the unqiue email or the length of the domain name. Quantifiers are denoted by using the `{}` symbols. The coding boot camp article for regex of a username provides the following specifications on quantifiers: 
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
The OR operator `|` allows for their to be multiple patterns that could be a match. For the purpose of an email this could be used to ensure the email is a specific type of domain such as `com|net|org|edu` etc. 

### Character Classes
Character classes are used to specify the characters that are allowed to be matched in a given pattern. In our example we see `[a-z0-9_\.-]` listed as the characters allowed for a unique email name. This means that the lower case characters a-z as well as the numerical characters 0-9 and the special characters _\._ could all be included in the unique name for the email. 

### Flags
Flags are used for different options for a regex pattern. For emails, we could use use the `i` case to make the pattern case-insensitive. As shown here: 
`/^([a-z0-9_\.-]+)@([\da-z\.-]+)\.([a-z\.]{2,6})$/i`

### Grouping and Capturing
Grouping allows you to break up the pattern into different pieces. In the context of an email, we have three groups, denoted by the `()` around each group. 

Group 1 - the unique email name: `([a-z0-9_\.-]+)`
Group 2 - the domain name: `([\da-z\.-]+)`
Group 3 - the second part of the domain name: `([a-z\.]{2,6})`

### Bracket Expressions
Bracket expressions allow for a matching a set of characters. Very similar to charcter classes, this is the specific denoation that marks what is allowed in a given pattern.

### Greedy and Lazy Match
Put simply, greedy patterns will match as many patterns as possible while lazy will match as few as possible. Greedy matching is the defualt behavior for regex. For an email, we might want to include the `?` match indciator to idtentify it as lazy so that it only matches the email without include extra characters like an empty space. 

### Boundaries
Boundaries, in the context of an email match, can be used similarlly to greedy or lazy match. For our purposes, we would include the boundaries around the email regex. That might look something like: `/\b([a-z0-9_\.-]+)@([\da-z\.-]+)\.([a-z\.]{2,6})\b/`

### Look-ahead and Look-behind
These are denoted by (?=pattern)" and "(?<=pattern)", respectively. For an email, they might be used to ensure that the username and domain name are valid. And ecample would be: `/(?<=^| )([a-z0-9_\.-]+)@([\da-z\.-]+)\.([a-z\.]{2,6})(?=$| )/`

## Author

This articule was written by Robert Charming, github: BobbyCharms. The aritcle references [https://coding-boot-camp.github.io/full-stack/computer-science/regex-tutorial] and used OpenAI to explain some of the concepts to the author. 
