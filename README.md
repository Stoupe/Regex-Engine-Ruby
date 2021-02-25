# Basic Ruby Regular Expression Engine

The regular expressions in this project consist only of these elements:

- Any literal character not given a specific meaning below, such as a, matches itself literally in the string.
- The dot character . matches any single character in the string: the regular expression a.c matches the strings "abc", "axc", "a1c", "a<c", etc.
- The asterisk character \* means that the string can include the previous element zero or more times: the regular expression a\* matches the empty string, "a", "aa", "aaa", and so on. This repetition operation always refers to the smallest element directly to the left of the star.
- The pipe/vertical bar character | means that the string can include either what is on the left, or what is on the right: the regular expression a|b matches "a" and "b". This alternation operation always extends as far as possible to both the left and right-hand side, but does not cross an enclosing parenthesis or another alternation (so a|b|c matches any of "a", "b", and "c").
Parentheses group together multiple elements: the regular expression (ab)* matches the empty string, "ab", "abab", "ababab", and so on, while (a|b)c matches "ac" and "bc".
- Any two elements next to one another match any string where the start of the string is matched by the first element, and the next element matches the rest: ab matches "ab"; a\*b matches "b", "ab", "aab", and so on; (ab*|c(d|)) matches "a", "ab", "c", "cd", "abb", and so on.

Only ASCII text will appear in both the regular expressions and the target strings. We are only considering matching the whole string: b does not match a substring from "abc".
