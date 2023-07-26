# Regex Tutorial: US phone number regex

Regular Expression aka regex, contains a set of characters that can be used for specific search pattern criteria.  
Regex can be used to find certain patterns in large text data, such as searching for emails or phone numbers.  
This also allows the data to be validated so that it matches the search criteria.  
This can also allow many programs such as text editors to easily extract data or replace strings. 

## Summary

This tutorial will contain notes from various sources to explain the components found in a regex.  
We will also use the following regex as an example when we look at each component.  
Regex:  /^(\()?\d{3}(\))?(-|\s)?\d{3}(-|\s)\d{4}$/  
Usage:  Match a 10 digit North American phone number (3 digit area code) + (subscriber number which show up as 3 digit and 4 digits)


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
Anchors make use of the caret symbol ( ^ ) and dollar sign ( \$ ).  
The ^ indicates a specific criteria at the start of a string, while $ looks for specific criteria at the end of a string.  

In our regex example:   /^(\()?\d{3}(\))?(-|\s)?\d{3}(-|\s)\d{4}$/   
The ^ looks for the start of the area code, the \$ looks for the subscriber number.

### Quantifiers
A quantifier specifies how many times an element should occur in the string.  
Quantifiers (taken from w3schools.com)  
n+: Matches any string that contains at least one n.  
n*: Matches any string that contains zero or more occurrences of n.  
n?: Matches any string that contains zero or one occurrence of n.  
n{X}: Matches any string that contains a sequence of X n's.  
n{X,Y}: Matches any string that contains a sequence of X to Y n's.  
n{X,}: Matches any string that contains a sequence of at least X n's.  
n$: Matches any string with n at the end of it.  
^n: Matches any string with n at the beginning of it.  
(?=n): Matches any string that is followed by a specific string n.  
(?!n): Matches any string that is not followed by a specific string n.  

This can allow the regex to match patterns with different lengths.  

The phone number regex uses \d{3} to match 3 digits and \d{4} to match 4 digits. 

### OR Operator
The ( | )  acts as the OR operator. 
The phone number regex makes use of this with (-|\s)?, which makes the hyphen between phone numbers optional.  
This will allow it to return a phone number that has hyphens as well as a 10 digit phone number with no hyphens.  


### Character Classes
A character class lets us define a group of characters that we want to match.  
This can be numbers from 0-9,  A-Z for upper case letters, a-z for lower case letters, or anything specified from the numbers and letters, such as abc123.  

In the phone number regex,  \d: Matches any digit from 0 to 9.  

### Flags
Flags can be used to control how the regex is interpreted.  Think of these as additional options.  

Flags (taken from MDN web docs)  
d: Generate indices for substring matches. (Corresponding property: hasIndices)  
g: Global search. (Corresponding property: global)  
i: Case-insensitive search. (Corresponding property: ignoreCase)  
m: Allows ^ and $ to match newline characters. (Corresponding property: multiline)  
s: Allows . to match newline characters. (Corresponding property: dotAll)  
u: "Unicode"; treat a pattern as a sequence of Unicode code points. (Corresponding property: unicode)  
v: An upgrade to the u mode with more Unicode features. (Corresponding property: unicodeSets)  
y: Perform a "sticky" search that matches starting at the current position in the target string. (Corresponding property: sticky)                                   

This phone number regex does not make use of flags.  


### Grouping and Capturing  
Grouping and capturing allows the creation of subexpressions.  This helps organize patterns.  
Grouping is done with parantheses () which will treat the content inside as a single unit.  (ab) will look for ab specifically.  

Capturing stores and can return text that matches the criteria.  

The phone number regex looks for 3 groups,  the first 3 digit area code, the 3 digit of the subscriber number, and then the last 4 digits.

### Bracket Expressions
Bracket expressions are enclosed in square brackets. [aeiou] will match any vowel, [0-9] will match any number 0 - 9.  

The phone number regex uses [-\s] to match either a hyphen or blank space.  

### Greedy and Lazy Match
This regex uses a greedy match by default with the empty bracket ( {} ) allowing as many matches as possible.  
Adding a ? after the quantifier would make it a lazy match, or match as few as possible.  

### Boundaries
Similar to the anchors,  the caret and dollar sign notes the start and end of the string.  

### Back-references  
Backreferences lets you match the same text that was stored in a capture group.  
There is no backreference used in the phone number regex.

### Look-ahead and Look-behind
This allows regex to essentially preview data before and after a matching pattern without using the specified criteria.  
Additional conditions are set to create more precision in the results. These conditions are not returned in the final matching result.  

The phone number regex does not use any look-ahead or look-behind options.

## Author

  Please contact [CML120](https://github.com/CML120) at cheelor922@gmail.com with any questions.


### Sources
https://coding-boot-camp.github.io/full-stack/computer-science/regex-tutorial
https://www.sitepoint.com/learn-regex/  
https://developer.mozilla.org/en-US/docs/Web/JavaScript/Guide/Regular_expressions  
https://www.w3schools.com/jsref/jsref_obj_regexp.asp  
https://medium.com/factory-mind/regex-tutorial-a-simple-cheatsheet-by-examples-649dc1c3f285 
https://codingnconcepts.com/java/java-regex-to-validate-phone-number/



