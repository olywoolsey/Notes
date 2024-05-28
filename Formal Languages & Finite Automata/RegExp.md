# Regular expressions

A regular expression is a sequence of characters that defines a search pattern. Regular expressions are mainly used to match or search for patterns in text, but they can also be used to perform tasks such as extracting, replacing, or splitting text.

Regular expressions are typically implemented using finite state automata, which are mathematical models that can be used to recognise patterns within input. Finite state automata are well-suited to this task because they are efficient at identifying patterns in large amounts of data and can be easily implemented in software.

There are many different variations of regular expressions, but most follow a common syntax that uses special characters to represent different types of patterns. For example, the special character "." can be used to match any single character, and the special character "*" can be used to match zero or more occurrences of the preceding character.

Regular expressions are often used in text processing tools such as text editors, search utilities, and programming languages. They are a powerful and flexible tool for working with text, and are widely used in a variety of applications.

There are many different variations of regular expression syntax, but most regular expressions follow a common set of rules and use a similar set of special characters. Here is a list of some common special characters that are used in regular expressions:

1. .: This character matches any single character.
2. *: This character matches zero or more occurrences of the preceding character.
3. +: This character matches one or more occurrences of the preceding character.
4. ?: This character matches zero or one occurrence of the preceding character.
5. ^: This character matches the beginning of a line.
6. $: This character matches the end of a line.
7. [...]: This character class matches any single character that is contained within the square brackets. For example, [abc] matches the characters "a," "b," or "c."
8. [^...]: This negated character class matches any single character that is not contained within the square brackets. For example, [^abc] matches any character that is not "a," "b," or "c."
9. \: This character is used to escape special characters, allowing them to be treated as literal characters.


Here are a few examples of regular expressions and the patterns they match:

1. dog: This regular expression matches the characters "dog" literally.
2. .og: This regular expression matches any three-character string that ends with "og," such as "dog," "log," or "bog."
3. do.: This regular expression matches any three-character string that starts with "do" and ends with any single character, such as "dog," "dot," or "doc."
4. d[aeiou]g: This regular expression matches any three-character string that starts with "d" and ends with "g," and has a single vowel character in between, such as "dag," "dog," or "dig".
5. d[a-z]g: This regular expression matches any three-character string that starts with "d" ends with "g" and has a single lowercase letter in between, such as "dog," "dcg," or "dzg."

