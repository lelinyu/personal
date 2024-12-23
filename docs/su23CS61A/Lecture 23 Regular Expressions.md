# Lecture 23 Regular Expressions

1. Questions
    1. When do you need to use the backslash, such as in phone number quantifier example
    2. Does raw strings have to be double quotes or can it be single quotes?
2. Regex
    1. Sequence of characters that specifies a pattern, usually utilized by string searching algorithms
    2. Not a programming language, just a standard that is implemented
    3. Using regex to specify a pattern we want to find within a string
3. Matching exact strings
    1. Most characters in RegEx will match exactly the characters as they appear in the expression
    2. Some characters in regex have reserved meanings
        1. Have to use escape sequence to search for those characters
        2. expression: \{abc}\ → {abc}
4. The Dot character
    1. reserved character that will match any single character that is not a new line
    2. . can basically be anything
    3. Expression: .a.a.a
    4. Fully matched by: banana, aaaaaa
5. Custom Character Classes
    1. Character classes match any of a set of characters - one instance of a character class will match exactly one character
    2. Expression: [ab]c[ab]c
        1. Its basically, either use a or b, then c, then a or b, then c
        2. Only 4 characters longth with that pattern
    3. Can use a dash to get entire groups of characters
        1. Expressions: [a-z] [0-9]
            1. All the characters between those numbers
            2. Fully matched by a0, b8, z0, g5
    4. **Note: Parentheses and Brackets are different**
    5. **Note: Whitespace matters**
6. Common Character Classes
    1. Shorthands for common character classes
        1. Put on cheatsheet or study guide, don’t need to necessarily memorize
    2. . matches any non-newline character
    3. \d matches digits, equivalent to [0-9]
    4. \w matches “word characters”, equivalent to [A-Za-z0-9_]
    5. \s matches whitespace characters
    6. [^] matches any character except whatever comes after [^]
    7. \D matches any non-digit character (opposite of \d)
        1. Also \S and \W (capital)
        2. can also use the not shorthand
7. Examples:
    1. [^ab]c
        1. Any character that is not an ‘a’ or ‘b’ followed by a ‘c’
        2. Correct: cc, zc, !c
        3. Incorrect: ab, bc
    2. a*b
        1. b, ab, aaaaaaaab
    3. a+b
        1. ab, aaaaaaaaab
        2. Note: only b doesn’t work, because we need at least a
8. Quantifiers
    1. allow us to specify multiple occurrences of the same character or character class
    2. a* zero or more occurrences of a
    3. a+ one or more occurrences of a
    4. a? zero or one occurrences of a
    5. a{2} two occurrences of a
    6. a{2,4} two, three, or four occurrences of a
    7. a{2,} at least 2 occurrences of a
9. Combining patterns
    1. The pipe | operator matches either the expression on its left or its right
    2. Basically an or statement
        1. But cannot be both
    3. Example:
        1. \d+|Inf
        2. Correct: Inf, 8
        3. Incorrect: 8Inf
    4. You can use parentheses to group expressions
        1. (<3)+
            1. <3, <3<3<3
10. Anchors
    1. Another unique expression
    2. They don’t match characters-instead, they match positions in a string where an expression could land
    3. ^ matches the beginning of a string
    4. $ matches the end of a string
    5. \b matches a “word” boundary” (whitespace, punctuation)
    6. Examples:
        1. ^aw+
            1. Correct: aww, awwwwwwwwwww
            2. Incorrect: aww aww ← second aww won’t be highlighted only first one
11. **Note: ^ has two meanings**
    1. [^a] → inverse (used inside character class)
    2. ^a → start of string (used outside character class)
12. Regular Expressions in Python
    1. We use the re module in Python
    
    ```python
    import re
    
    re.search(<pattern>, <string>)
    #Returns a Match object representing the first occurrence of <pattern> in <string>
    
    #usually used with bool
    bool(re.search())
    ```
    
13. Raw Strings
    1. Python has escape characters built in to string evaluation such as the new line character
    2. Regex has \, we use raw strings without Python thinking \ is python
    3. print(r”hellow\nthere!”)
        1. >>> hello\nthere
    4. Use raw strings with regex
14. Match objects
    1. Re module has methods that attempt to match a pattern to a string- if they find a match, they’ll return a match object
    2. If they don’t find a match, they’ll return None (falsey)
    3. re.search
    4. re.fullmatch(<pattern>, <string>)
        1. Returns a match object requiring that pattern entirely matches string
    5. re.match
        1. String must start with pattern
    6. Examples:
        1. Our first value is the first value that matches the pattern
        2. mat = re.search
        3. >>>mat.group(0)
        4. ‘35’
15. Capturing groups
    1. When we use parentheses to group sub-expressions, they define capture groups that we can then access individually
16. Other re functions
    1. re.finall
        1. Returns a list of all substrings within <string> that match <pattern>, read from left to right
    2. re.sub (<pattern>, <repl>, <string>)
        1. pattern is replace with repl
17. Center embedding
    1. Context-free grammars (CFGs)
        1.