# 1. String Pattern? Regex Makes Your Life Easier!

*2020-08-07 by Hongliang Zhu*

<div id="toc">

- [1. String Pattern? Regex Makes Your Life Easier!](#1-string-pattern-regex-makes-your-life-easier)
    - [1.0.1. Definition](#101-definition)
    - [1.0.2. Basics](#102-basics)
    - [1.0.3. Quantifiers](#103-quantifiers)
    - [1.0.4. Class Characters](#104-class-characters)
    - [1.0.5. Special Characters](#105-special-characters)
    - [1.0.6. Groupings](#106-groupings)
    - [1.0.7. Assertions](#107-assertions)
    - [1.0.8. Character In Replacement String](#108-character-in-replacement-string)
    - [1.0.9. References](#109-references)

</div>


### 1.0.1. Definition

* <details open><summary>What is Regex?</summary>

  > Regex, also commonly called regular expression, is a combination of characters that **define a particular search pattern**.

* <details open><summary>When Can I Use Regex?</summary>

  > Regex can be used for matching a string of text, find and replace operations, data validation, etc. For example, with regex you can easily check a user's input for common misspellings of a particular word.

* <details open><summary>Pros and Cons</summary>

  *Pros*: It is a efficient way to do matching on inputs; Those regular expressions are configurable and can be separated from code.

  *Cons*: Hard to read, the performance is a concern.


### 1.0.2. Basics

| CHARACTER |                                 DESCRIPTION                                  |
| :-------: | :--------------------------------------------------------------------------: |
|    `^`    |                            The start of a string                             |
|    `$`    |                             The end of a string                              |
|    `.`    |          Wildcard which matches any character, except newline (\n)           |
|    `|`    | Or, matches the pattern defined on either side, eg: `a|b` matches `a` or `b` |
|    `\`    |                      Used to escape a special character                      |
|    `a`    |                              The character `a`                               |
|   `ab`    |                               The string `ab`                                |


### 1.0.3. Quantifiers

| QUANTIFIER |               DESCRIPTION               |
| :--------: | :-------------------------------------: |
|    `*`     |    Matches 0 or more of the previous    |
|    `?`     |     Matches 0 or 1 of the previous      |
|    `+`     |    Matches 1 or more of the previous    |
|   `{5}`    | Matches exactly 5 times of the previous |
| `{5, 10}`  |  Matches 5 to 10 times of the previous  |


### 1.0.4. Class Characters

| CHARACTER |            DESCRIPTION             |
| :-------: | :--------------------------------: |
|   `\s`    |   Matches a whitespace character   |
|   `\S`    | Matches a non-whitespace character |
|   `\w`    |      Matches a word character      |
|   `\W`    |    Matches a non-word character    |
|   `\d`    |     Matches a digit character      |
|   `\D`    |   Matches a non-digit character    |
|  `[\b]`   |   Matches a backspace character    |
|   `\c`    |    Matches a control character     |


### 1.0.5. Special Characters

| CHARACTER |         DESCRIPTION         |
| :-------: | :-------------------------: |
|   `\n`    |      Matches a newline      |
|   `\t`    |        Matches a tab        |
|   `\r`    |  Matches a carriage return  |
|  `\ZZZ`   | Matches octal character ZZZ |
|  `\xZZZ`  |  Matches hex character ZZZ  |
|   `\0`    |  Matches a null character   |
|   `\v`    |   Matches a vertical tab    |


### 1.0.6. Groupings

|  GROUPS   |                                DESCRIPTION                                |
| :-------: | :-----------------------------------------------------------------------: |
|  `(xyz)`  |                          Grouping of characters                           |
| `(?:xyz)` | Non-capturing group of characters. (Do matching but not record in result) |
|  `[xyz]`  |             Matches a range of characters (e.g. x or y or z)              |
| `[^xyz]`  |                Matches a character other than x or y or z                 |
|   `a-q`   |             Matches a character from within a specified range             |
|   `0-7`   |               Matches a digit from within a specified range               |


### 1.0.7. Assertions

|  ASSERTION   |                                    DESCRIPTION                                     |
| :----------: | :--------------------------------------------------------------------------------: |
|  `(?=xyz)`   |                                 Positive lookahead                                 |
|  `(?!xyz)`   |                                 Negative lookahead                                 |
| `?!= or ?<!` |                                Negative lookbehind                                 |
|     `\b`     | Word Boundary, beginning or end of the word (usually a position between /w and /W) |
|     `\B`     |             Word Boundary, not the beginning or not he end of the word             |
|     `?#`     |                                      Comment                                       |


### 1.0.8. Character In Replacement String

|    CHARACTER    |         DESCRIPTION          |
| :-------------: | :--------------------------: |
| <code>$`</code> | Insert before matched string |
|      `$'`       | Insert after matched string  |
|      `$+`       |     Insert last matched      |
|      `$&`       |     Insert entire match      |
|      `$n`       |  Insert nth captured group   |

  *NOTE: For this part, in python `re.sub(pattern, sub, target)`, `\1` is the replacement for `$&` and others are invalid*


### 1.0.9. References

* [Regex Cheat Sheet](https://www.keycdn.com/support/regex-cheatsheet)

* [Regex 101](https://regex101.com)
