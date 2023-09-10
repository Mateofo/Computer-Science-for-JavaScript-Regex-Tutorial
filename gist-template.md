# Homework-17 Regex

Introductory paragraph (replace this with your text)

## Summary

In this tutorial, we'll break down a regular expression used to validate and match email addresses. The regex ensures that the email follows the format of a username, the "@" symbol, and a domain name. We'll provide a detailed explanation of each part of the regex and its role in email validation. Here's the regex we'll be discussing:

^[a-zA-Z0-9._%+-]+@[a-zA-Z0-9.-]+\.[a-zA-Z]{2,}$

## Table of Contents

- [Anchors](#anchors)
- [Quantifiers](#quantifiers)
- [Grouping Constructs](#grouping-constructs)
- [Bracket Expressions](#bracket-expressions)
- [Character Classes](#character-classes)
- [The OR Operator](#the-or-operator)
- [Flags](#flags)
- [Character Escapes](#character-escapes)

### Anchors

Anchors act as markers that guide regex to start or conclude its matching precisely where specified. The `^` symbol denotes the start of a line or string, while the $ symbol denotes the end. Anchors help us define strict boundaries for pattern matching within text.

### Quantifiers

Quantifiers in regular expressions allow you to define the quantity or repetition of characters or groups in a pattern. They let you specify how many times a particular element should occur to consider it a match. Quantifiers offer flexibility and efficiency in matching repetitive patterns within text.

Here are some essential quantifiers:

"+" (One or More):
The plus symbol + indicates that the preceding character or group must appear at least once, but can repeat more times.

Example: a+ will match one or more consecutive "a" characters.

"*" (Zero or More):
The asterisk symbol * signifies that the preceding character or group can appear zero or more times.

Example: b* will match zero or more consecutive "b" characters.

"?" (Zero or One):
The question mark symbol ? specifies that the preceding character or group can appear zero or one time, making it optional.

Example: colou?r will match both "color" and "colour."

"{n}" (Exactly n Times):
Curly braces {n} denote that the preceding character or group must appear exactly n times.

Example: d{3} will match "ddd" but not "dd" or "dddd."

"{n,}" (At Least n Times):
Curly braces {n,} indicate that the preceding character or group must appear at least n times.

Example: e{2,} will match "ee," "eee," and so on.

"{n,m}" (Between n and m Times):
Curly braces {n,m} specify that the preceding character or group should appear between n and m times, inclusive.

Example: f{2,4} will match "ff," "fff," and "ffff."

Quantifiers streamline the process of matching repetitive patterns and reduce the need for manually listing each occurrence. By incorporating quantifiers, you can efficiently capture varying repetitions of characters, making your regex more versatile and concise.

### Grouping Constructs

Grouping constructs in regular expressions allow you to treat multiple characters or subpatterns as a single unit. This unit can then be quantified, matched, or referenced as a whole. Grouping constructs enhance pattern organization, clarity, and control, making complex patterns more manageable.

There are two primary types of grouping constructs:

Parentheses ( ) for Capturing Groups:
Parentheses ( ) group characters or subpatterns together, creating a single unit that can be quantified or referenced later.

Example: (ab)+ will match sequences of "ab" such as "ab," "abab," and so on.

Non-Capturing Groups (?: ):
Non-capturing groups (?: ) also group characters, but they do not capture or store the matched content. They are useful when you want to apply quantifiers to a group but don't need to reference the matched text.

Example: (?:x|y) will match either "x" or "y" but won't capture the matched value.

Grouping constructs offer several benefits:

Quantification: You can apply quantifiers like *, +, or ? to the entire group.
Alternation: Use the OR operator | inside groups to create alternatives.
Backreferences: Capturing groups can be referenced later in the pattern using \1, \2, etc.

### Bracket Expressions

Bracket expressions in regular expressions allow you to define a set of characters that you want to match. They provide a compact way to specify a range or a collection of characters that should be considered as a match. Bracket expressions enhance pattern flexibility by allowing you to match any character within a specified set.

Here are the key components of bracket expressions:

Square Brackets [ ]:
Square brackets [ ] enclose the characters you want to match. They represent a character set.

Example: [aeiou] will match any vowel character.

Ranges -:
A hyphen - inside square brackets indicates a range of characters. It allows you to match any character within that range.

Example: [a-z] will match any lowercase letter.

Negation ^:
Placing a caret ^ as the first character inside square brackets negates the set, matching any character that is not in the specified set.

Example: [^0-9] will match any non-digit character.

Escaping :
Special characters inside square brackets can be treated as literals by escaping them with a backslash \.

Example: [\$] will match a literal dollar sign.

In summary, bracket expressions offer a compact and efficient way to define sets of characters you want to match. They allow for individual character matching, ranges, negation, and escaping of special characters. Bracket expressions are particularly useful when you want to match a specific category of characters within a pattern.

### Character Classes

Character classes in regular expressions provide a way to match specific categories of characters. They allow you to specify a group of characters that you want to match, making it easier to work with common character types. Character classes simplify pattern creation by providing predefined categories that match a wide range of characters.

Here are the key points about character classes:

Predefined Classes:
Predefined character classes represent common character categories. Some examples include:

\d: Matches any digit (equivalent to [0-9]).
\w: Matches any word character (letters, digits, or underscores).
\s: Matches any whitespace character (spaces, tabs, line breaks).
\D, \W, \S: Negations of the above classes.
Custom Classes [ ]:
You can create custom character classes using square brackets [ ]. Inside the brackets, you list the characters you want to match.

Example: [aeiou] will match any lowercase vowel.

Ranges -:
Just like in bracket expressions, you can use a hyphen - to define character ranges within character classes.

Example: [a-z] will match any lowercase letter.

Negation ^:
Placing a caret ^ at the beginning of a character class negates it, matching any character not in the class.

Example: [^0-9] will match any non-digit character.

Escaping :
Special characters inside character classes can be escaped with a backslash \ to match them literally.

Example: [.] will match a literal period.

Character classes simplify pattern creation by offering predefined sets of characters and the flexibility to create custom sets. They're particularly useful when you need to match characters of a specific category, like digits, letters, or whitespace, within your regular expression pattern.

### The OR Operator

The OR operator in regular expressions allows you to specify alternatives for matching. It's represented by the vertical bar | and enables you to choose one pattern or another. This operator provides a way to create flexible patterns that match different variations of text.

Here's how the OR operator works:

Pattern1 | Pattern2:
The vertical bar | separates two alternative patterns. The regex engine will try to match either Pattern1 or Pattern2. If either one matches, the entire expression is considered a match.

Grouping with Parentheses:
You can use parentheses ( ) to group parts of your pattern when using the OR operator. This ensures that the alternatives are applied to a specific part of the pattern.

Example: (cat|dog) will match either "cat" or "dog."

The OR operator is handy for situations where multiple variations of a word or expression are acceptable. It simplifies pattern creation and makes your regular expressions more concise and readable.

In summary, the OR operator in regular expressions provides a powerful way to specify alternatives for matching. By using the vertical bar | to separate patterns, you can create versatile patterns that accommodate different variations of text within a single expression.

### Flags

Flags in regular expressions are modifiers that change how a regex pattern is interpreted and applied. They provide additional control over matching behavior and help customize the regex to suit specific requirements. Flags are typically appended after the closing delimiter of the regex pattern.

Here are some common flags and their functionalities:

Case Insensitive (i):
The i flag makes the regex case-insensitive, allowing it to match characters regardless of their case.

Example: /apple/i will match "apple," "Apple," and "aPpLe."

Global (g):
The g flag enables global matching, meaning the regex will search for all occurrences of the pattern within the text.

Example: /cat/g will find all instances of "cat" in the text.

Multiline (m):
The m flag enables multiline mode, causing ^ and $ anchors to match the start and end of each line within the text.

Example: /^start/m will match "start" at the beginning of each line.

Sticky (y):
The y flag enables sticky matching, ensuring that the regex starts matching at the exact position specified by the lastIndex property of the regex object.

Example: /pattern/y will match only if the lastIndex position is at the start.

Flags provide a way to customize how a regex behaves. By using flags, you can control whether the matching is case-sensitive, global, multiline, or sticky. Flags allow you to fine-tune your regex to achieve the desired matching behavior in different scenarios.

### Character Escapes

Character escapes in regular expressions provide a way to match special characters or characters with special meanings as literal characters. They allow you to treat characters that would normally have special regex significance as ordinary characters. Character escapes are achieved by preceding the special character with a backslash \.

Here's how character escapes work:

.:
The backslash \ followed by a period . matches a literal period.

Example: \. will match a literal period.

\:
The backslash \ followed by a backslash \\ matches a literal backslash.

Example: \\ will match a literal backslash.

\d, \w, \s:
Special character escapes represent predefined character classes.

\d: Matches any digit character (equivalent to [0-9]).
\w: Matches any word character (letters, digits, or underscores).
\s: Matches any whitespace character (spaces, tabs, line breaks).
\D, \W, \S:
Adding an uppercase letter to the above escapes negates them.

\D: Matches any non-digit character.
\W: Matches any non-word character.
\S: Matches any non-whitespace character.
\n, \t, \r:
Special escape sequences match specific control characters.

\n: Matches a newline character.
\t: Matches a tab character.
\r: Matches a carriage return character.
Character escapes are used to ensure that characters with special meanings in regex are treated literally. They are particularly useful when you need to match characters like periods, backslashes, or control characters without their special regex interpretations.

## Author

A short section about the author with a link to the author's GitHub profile (replace with your information and a link to your profile)
