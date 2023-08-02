# Title REGEX for Matching an HTML Tag 

In this GIST, I will breakdown in explanation the various part of an HTML tag REGEX string. 

## Summary

The REGEX - Matching an HTML Tag – /^<([a-z]+)([^<]+)*(?:>(.*)<\/\1>|\s+\/>)$/
The purpose of this regular expression is to match a complete HTML tag. It is a string that includes a search pattern meant for validating an HTML tag. The string can contain matching lowercase letters "a-z", numbers, characters, and self closing tags.

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
There are two anchors in this regular expression. They are the caret symbol ^ which is used at the beginning of the regular expression and the dollar sign $ which is used at the end of the regular expression. Both of these anchors in conjunction ensure that the entire string contains only an HTML tag and that there will not be a match if there other characters before or after the HTML tag in this string.


### Quantifiers
There are three quantifiers in this expression. 
The plus sign + is used after the character class [a-z] to indicate that there should be one or more lowercase letters (a-z) within the tag name for matching. This quantifier ensures that the tag name contains at least one lowercase letter.
The asterisk * is used after the character class [^<] to indicate that there can be zero or more attributes that are not an opening angle bracket < for matching attributes if they exist.
The asterisk * is used after the non-capturing group (?:>(.)</\1>|/>) to indicate that there can be zero or more of any type of characters (.) between the opening and closing tags. This quantifier permits the presence of content between the opening and closing tags and matches the content if it exists.

### OR Operator
The caret symbol ^ at the beginning of the regular expression indicates the start of the string to ensure that the HTML tag can be found at the beginning.

The opening angle bracket in the string "<" matches the actual character "<" and the closing angle bracket ">" matches the actual character ">".

For (?:), this is the start of a non-capturing group that is used in this case for grouping without capturing the matched result

For </\1>, this matches the closing tag of the same name captured in the first capturing group (\1 refers to the first capturing group). The backslash before the closing angle bracket "<" escapes it to treat it as a literal character.

The vertical bar "|" is the alternation operator (logical OR). It allows for either the previous capturing group (content between opening and closing tags) or the following part of the string to be matched.

For \s+/>, this part of the string is used for matching self-closing tags like <br />. The \s+ is used for matching one or more whitespace characters, and the /> is used for matching with the actual character "/>".

The dollar sign "$" at the end of the regular expression indicates the end of the string to ensure that the HTML tag can be found at the end.

### Character Classes
The following character classes were used in the REGEX string:
(.)
\s
[a-z]
\/\

### Flags
There are no flags placed at the end of this REGEX. 

### Grouping and Capturing
For ([a-z]+), this is a capturing group that matches one or more lowercase letters (a-z) to capture the tag name. The parentheses  () in this case defines the capturing group.

For ([^<]+)*, this is is another capturing group that matches zero or more characters that are not an opening angle bracket "<" to capture any attributes of the HTML tag. The square brackets [] is used to define a character class, and the ^ inside the character class [] disregards the <> class by matching any character except the one defined.

For (.*), this is a capturing group that matches zero or more of any character to captures the content between the opening and closing tags. The dot . matches any character except newline, and the asterisk * signifies zero or more occurrences.

### Bracket Expressions
Below are bracket expressions used with grouping and capturing:
[a-z]
[^<]

### Greedy and Lazy Match
In this case, there are greedy matches used in different parts of the regular expression.

Greedy Matching:

For ([a-z]+), this part of the string matches the tag name and uses greedy matching. The plus sign + is considered to be a greedy quantifier that will match as many lower case letter characters as possible. It will consume all available lowercase letters and return characters only if it is necessary to make the rest of the regular expression match.

For ([^<]+)*, this part of the string matches the attributes of the HTML tag and also uses greedy matching. The plus sign + is considered to be a greedy quantifier that will match as many characters as possible that are not an opening angle bracket "<". It will consume all available characters that are not "<" and return characters only if it is necessary to make the rest of the regular expression match.

For (.*<\/\1>), this part of the string matches the content between the opening and closing tags. The dot (.) matches any character except a newline, and the asterisk * is a greedy quantifier by default.

### Boundaries
There are no word boundaries in this HTML Tag regular expression /^<([a-z]+)([^<]+)*(?:>(.*)<\/\1>|\s+\/>)$/.

### Back-references
There is one backreference (\1) in this HTML Tag regular expression /^<([a-z]+)([^<]+)*(?:>(.*)<\/\1>|\s+\/>)$/.

### Look-ahead and Look-behind
There are no look-ahead and look-behind assertions in this HTML Tag regular expression /^<([a-z]+)([^<]+)*(?:>(.*)<\/\1>|\s+\/>)$/.

## Author
Cassie Owens is developer who lives in South Florida and enjoys exploring the JavaScript programming language, SQL, and NoSQL techniques. 
GitHub Profile - https://github.com/Cassieellaelaine
