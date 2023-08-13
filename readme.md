# Matching a URL with Regex

A regular expression that will help to find strings located within a url

## Summary

Breaking down the following regex code with explanations as to what each part does
```
https?:\/\/(www\.)?[\d-a-zA-Z0-9@:%._\+~#=]{1,256}\.[a-zA-Z0-9()]{1,6}\b([-a-zA-Z0-9()@:%_\+.~#?&//=]*)
```

## Table of Contents

- [Matching a URL with Regex](#matching-a-url-with-regex)
  - [Summary](#summary)
  - [Table of Contents](#table-of-contents)
  - [Regex Components](#regex-components)
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
  - [Author](#author)

## Regex Components

### Anchors
Anchors are used at the front and back ends of a search in order to check if a string fully matches a pattern, however they themselves do not match characters. They strictly affirm a string matches a location. Anchors create parameters.
* Use the ```^``` anchor to match the beginning of the text. 
* Use the ```$``` anchor to match the end of the text.

### Quantifiers
Quantifiers will measure and set the limit on the the number of characters that we are wanting to match in our Regex.
 ```+``` searches the pattern one or more times.
```?``` searches the pattern zero or one time. 
 ```*``` searches the pattern zero or more times.

For example:
``` https? ```  
The ? will make the preceeding item optional.


### OR Operator
The purpose of an OR operator is to match the characters on the left or right of the operator. 
Using the | as in m|M would match either m or an M from the string. 
Take the following regex :
 ```https?:\/\/(www\.)?[\d-a|A``` 
 This would search for an "a" or and "A"

### Character Classes
A character class is  the set of characters that could occur in a string.  
For instance, the \d character class in the above code is looking for any digits, where a \D looks for non-digits. 
\s searches for space symbols, tab and newlines, \S looks for all but \s, \. any characters with the regex 's' flag. 
The \w character is looking for an alphanumeric character.
### Flags
Flags are used at the end of a regex to modify thw parameters of a search. Multiple flags can be set by writing one after another with NO spaces. Flags must be written in lowercase. This URL regex does not contain any flags, however an example of a flag would be if it showed:
```
https?:\/\/(www\.)?[\d-a-zA-Z0-9@:%._\+~#=]{1,256}\.[a-zA-Z0-9()]{1,6}\b([-a-zA-Z0-9()@:%_\+.~#?&//=]*)g
```
the g is a flag for a global expression

Flag Expressions:
* i: Ignores casing. Makes expression case-sensitive
* g: Global. Makes expression search for every occurence
* s: Dot All. Makes the wild characters . match newlines as well
* m: Multiline. Makes boundary characters ^ and $ match beginning and end of every line.
* y: Sticky. Indicates that it matches only from the index indicated by the lastIndex property of this regular expression in the target string (and does not attempt to match from any later indexes)
* u: Unicode. Expression assumes individual characters are code points, not code units and will then match 32 bit characters.
### Grouping and Capturing
Capturing and grouping are a part of a regex pattern that can be enclosed in a parentheses and are a way to treat multiple characters as a single unit. The example expression I chose has many groupings such as: 
```https?:\/\/``` which is looking for the http(s),```(www\.)?[\d-a-zA-Z0-9@:%._\+~#=]``` which will look for the initial domain.
 ```[a-zA-Z0-9()]{1,6}\b([-a-zA-Z0-9()@:%_\+.~#?&//=]``` looks for top level domain.
```*)``` looks for file paths.
### Bracket Expressions
Bracket expressions are used for matching or non-matching list expression and consist of one or more expressions that will be found in square brackets. 
They represent a special character class and are a quantified rule providing range construct. They adapt to a users or applications locale. 
### Greedy and Lazy Match
The definition of a greedy match is a search that will try to find the longest possible string, while a lazy match is search will find the smallest possible string. 
Greedy quantifiers are:
* + = one or more revised gist
* * = Zero or more
* {2,4} = Two to four times as greedy
* 
Lazy quantifier:
- ?
This expression : 
```(https?:\/\/)?``` uses the lazy match of ? and is looking http OR https, ```[a-zA-Z0-9()]{1,6}``` is looking for a-z, A-Z, 0-9; one to six times as greedy.

### Boundaries
Boundaries are similar to an anchor and uses the expression \b for word boundaries and \B for non-word boundaries. They are a zero-length match that marks the beginning and end of an alphanumerical sequence and will make it easier to find whole words. The beginning of this expression ```\b([-a-zA-Z0-9()@:%_\+.~#?&//=]*)``` is searching for a whole word or digit.
### Back-references
Back-references are filters used to match the same text previously matched by a capturing group. An example would be when you desire to search for a repeated word, the first match could use a pattern that extracts a signle word, the second would be a back reference that referes to the captured group. The regex I chose does not include any back-references.
## Author
Regex tutorial created by https://github.com/NickD428 with the help of classmates, and several long google searches!