# Regex Tutorial

## 📖 Summary 
Regex (short for regular expression) is a sequence of characters that define a search pattern. It is a powerful tool used for pattern matching and string manipulation. It allows developers and users to search and manipulate text data with a high level of precision and flexibility. Regular expressions can be used in many programming languages, text editors, and command-line tools to perform various tasks such as searching and replacing text, validating input data, and extracting specific information from a larger string of text.

## 📚 Table of Contents 
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

### ⭐️ Anchors 
In regular expressions, anchors are special characters that allow you to match patterns based on their position within a string. There are two types of anchors:

The caret (^) anchor: This matches the beginning of a string. For example, the regular expression "^Hello" will match any string that starts with "Hello".

The dollar sign ( $ ) anchor: This matches the end of a string. For example, the regular expression "world$" will match any string that ends with "world".

By using anchors, you can control where a pattern should be found within a string. This can be helpful when you want to match patterns that are specific to the beginning or end of a string.

### ⭐️ Quantifiers 
In regular expressions, quantifiers are special characters that specify how many times a character, group, or character class should be matched. Quantifiers allow you to match patterns that occur a specific number of times or within a specific range of times. Here are some common quantifiers:

The asterisk () quantifier: This matches zero or more occurrences of the preceding character or group. For example, the regular expression "ab" will match "a", "ab", "abb", "abbb", and so on.

The plus (+) quantifier: This matches one or more occurrences of the preceding character or group. For example, the regular expression "ab+" will match "ab", "abb", "abbb", and so on, but not "a".

The question mark (?) quantifier: This matches zero or one occurrence of the preceding character or group. For example, the regular expression "ab?" will match "a" and "ab", but not "abb".

The curly braces ({}) quantifier: This allows you to specify a specific number of occurrences of the preceding character or group. For example, the regular expression "a{3}" will match "aaa".

The curly braces ({min, max}) quantifier: This allows you to specify a range of occurrences of the preceding character or group. For example, the regular expression "a{2,4}" will match "aa", "aaa", and "aaaa".

By using quantifiers, you can make your regular expressions more powerful and flexible, allowing you to match patterns that occur in a specific way.

### ⭐️ OR Operator 
In regular expressions, the OR operator allows you to match one of several alternatives. It is represented by the pipe symbol (|) and is used to separate the alternatives that you want to match. Here's an example:

The regular expression "cat|dog" will match either "cat" or "dog".

You can also use parentheses to group the alternatives and apply other regular expression operators to them. For example:

The regular expression "app(le|roach|lepie)" will match "apple", "approach", or "applepie".

Using the OR operator allows you to match different variations of a pattern with a single regular expression. This can be useful in situations where you want to search for multiple possibilities in a text string.
### ⭐️ Character Classes 
In regular expressions, a character class is a way to specify a set of characters that you want to match. Character classes are enclosed in square brackets ([]) and allow you to match any single character from the set of characters you specify.

Here are some examples of character classes:

[abc]: This matches any one of the characters "a", "b", or "c".
[a-z]: This matches any lowercase letter from "a" to "z".
[A-Z]: This matches any uppercase letter from "A" to "Z".
[0-9]: This matches any digit from "0" to "9".
[a-zA-Z]: This matches any letter, regardless of case.
You can also use predefined character classes, such as \d (which matches any digit) and \s (which matches any whitespace character).

By using character classes, you can make your regular expressions more specific and powerful, allowing you to match patterns that contain specific characters or types of characters.
### ⭐️ Flags
In regular expressions, flags are optional parameters that modify the behavior of the regular expression engine. They are used to control how the regular expression matches the text and what information is returned.

Here are some common flags:

Case-insensitive flag (i): This flag makes the regular expression match case-insensitively. For example, the regular expression "/hello/i" will match "Hello", "HELLO", and "hello".

Global flag (g): This flag makes the regular expression match globally. It allows you to match all occurrences of the pattern in the text, rather than just the first one.

Multi-line flag (m): This flag makes the regular expression match across multiple lines. It changes the behavior of the "^" and "$" anchors so that they match the beginning and end of each line, rather than the beginning and end of the entire string.

Unicode flag (u): This flag enables Unicode support in the regular expression. It allows you to match characters outside of the ASCII character set.

By using flags, you can customize the behavior of your regular expressions to match your specific needs.
### ⭐️ Grouping and Capturing
In regular expressions, grouping and capturing refer to the ability to group parts of a regular expression together and capture the matched text.

Grouping is achieved by enclosing part of a regular expression in parentheses. For example, the regular expression "ab(cd)+ef" uses grouping to match one or more occurrences of the "cd" sequence.

Capturing is the ability to extract the text matched by a group and use it in a replacement or further processing. Capturing is done by assigning a name or number to a group using a special syntax.

Here are some examples:

Numbered capturing group: (regex): This captures the text matched by the group and assigns it a number based on the order of appearance in the regular expression. The first capturing group is assigned the number 1, the second capturing group is assigned the number 2, and so on.

Named capturing group: (?<name>regex): This captures the text matched by the group and assigns it a name that can be used to refer to the captured text in a replacement or further processing.

By using grouping and capturing, you can create more complex regular expressions that match specific patterns and extract specific information from text.

### ⭐️ Bracket Expressions
In regular expressions, bracket expressions (also called character classes) are a way to match any single character from a set of characters.

Bracket expressions are enclosed in square brackets ([]), and any character that appears inside the brackets matches any single character from the set.

Here are some examples of bracket expressions:

[abc]: This matches any one of the characters "a", "b", or "c".
[a-z]: This matches any lowercase letter from "a" to "z".
[A-Z]: This matches any uppercase letter from "A" to "Z".
[0-9]: This matches any digit from "0" to "9".
[a-zA-Z]: This matches any letter, regardless of case.
You can also use negation to create a bracket expression that matches any character that is not in the set. This is done by adding a caret (^) immediately after the opening bracket. For example, [^abc] matches any character that is not "a", "b", or "c".

Bracket expressions can be combined with other regular expression constructs, such as quantifiers, to create more complex patterns. By using bracket expressions, you can match specific characters or types of characters in a text string.

### ⭐️ Greedy and Lazy Match
In regular expressions, greedy and lazy matching refer to the way in which the regular expression engine tries to match patterns in the text.

A greedy match tries to match as much of the text as possible, while still allowing the pattern to match. For example, the regular expression "a.*b" with the input "aabcdb" will match the entire string "aabcdb", even though the pattern could also match "aab".

A lazy match, on the other hand, tries to match as little of the text as possible, while still allowing the pattern to match. This is done by adding a question mark (?) after a quantifier. For example, the regular expression "a.*?b" with the input "aabcdb" will match the substring "aab".

The difference between greedy and lazy matching is important when working with patterns that can match multiple parts of a string. Greedy matching can lead to unexpected results if the regular expression matches too much of the text, while lazy matching can be more precise and efficient.

It's worth noting that some regular expression engines, such as the PCRE library used by PHP and many other languages, also support a possessive match. A possessive match is similar to a greedy match, but once a match has been found, the regular expression engine will not backtrack to find a better match. This can be useful for certain types of patterns where backtracking can be expensive or lead to incorrect results.

### ⭐️ Boundaries
In regular expressions, boundaries refer to positions in the text where certain conditions are met. They are used to match patterns that occur at the beginning or end of a word, line, or string.

Here are some common boundary markers in regular expressions:

^ (caret): This matches the beginning of a line or string. For example, the regular expression "^abc" matches "abc" only if it occurs at the beginning of a line or string.

$ (dollar sign): This matches the end of a line or string. For example, the regular expression "abc$" matches "abc" only if it occurs at the end of a line or string.

\b (word boundary): This matches the position between a word character (\w) and a non-word character (\W). For example, the regular expression "\bcat\b" matches "cat" only if it occurs as a whole word, and not as part of another word (like "catch").

\B (non-word boundary): This matches the position between two word characters (\w\w) or two non-word characters (\W\W). For example, the regular expression "\Bcat\B" matches "cat" only if it occurs as part of another word (like "scattered").

Boundaries can be used to create more precise regular expressions that match specific patterns in the text. By using boundaries, you can ensure that your regular expression only matches the parts of the text that you intend to match.

### ⭐️ Back-references
In regular expressions, a back-reference is a way to refer to a previously matched group within the same regular expression.

Back-references are used to match repeated occurrences of a pattern, or to capture and reuse specific parts of the text. They are created by enclosing a group in parentheses, and then referring to that group later in the regular expression using a backslash followed by the group number.

For example, the regular expression "(a+)\1" will match one or more occurrences of the letter "a", followed by the same number of occurrences of "a" that were previously matched. The back-reference \1 refers to the first group, which is the sequence of one or more "a" characters.

Back-references are useful when working with patterns that repeat or have specific sub-patterns that need to be matched or captured. They can be combined with other regular expression constructs, such as quantifiers, to create more complex patterns that match specific parts of the text.

It's important to note that not all regular expression engines support back-references, and the syntax for creating them can vary between engines. It's also important to use back-references carefully, as they can create patterns that are difficult to understand and maintain.

### ⭐️ Look-ahead and Look-behind
In regular expressions, look-ahead and look-behind are zero-width assertions that allow you to match patterns that are followed by or preceded by certain other patterns, without actually including those patterns in the match.

Look-ahead and look-behind assertions are created using parentheses and special characters that specify the type of assertion. Here are some common types of look-ahead and look-behind assertions:

Positive look-ahead (?=): This asserts that the pattern inside the parentheses must be present after the current position in the text, but it doesn't include it in the match. For example, the regular expression "foo(?=bar)" will match "foo" only if it is followed by "bar", but "bar" itself will not be included in the match.

Negative look-ahead (?!): This asserts that the pattern inside the parentheses must NOT be present after the current position in the text. For example, the regular expression "foo(?!bar)" will match "foo" only if it is NOT followed by "bar".

Positive look-behind (?<=): This asserts that the pattern inside the parentheses must be present before the current position in the text, but it doesn't include it in the match. For example, the regular expression "(?<=foo)bar" will match "bar" only if it is preceded by "foo", but "foo" itself will not be included in the match.

Negative look-behind (?<!): This asserts that the pattern inside the parentheses must NOT be present before the current position in the text. For example, the regular expression "(?<!foo)bar" will match "bar" only if it is NOT preceded by "foo".

Look-ahead and look-behind assertions are useful for creating complex regular expressions that match specific patterns in the text. They can be used to match patterns that are not easily captured by other regular expression constructs, such as boundaries and character classes.

## Author
James Inanoria 
GitHub: https://github.com/jxmesin