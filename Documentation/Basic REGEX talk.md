<h1 style="text-align:center">Regex Basics</h1>  

## Table of Contents <!-- omit in toc -->
- [What is "RegEx" ?](#what-is-regex-)
- [Basics](#basics)
  - [Common Tokens](#common-tokens)
  - [Quantifiers](#quantifiers)
    - [Modifiers](#modifiers)
  - [Special Characters](#special-characters)
  - [Groups](#groups)
- [Example :](#example-)

## What is "RegEx" ?
[Wikipedia](https://en.wikipedia.org/wiki/Regular_expression) definiton  
RegEx, or Regular Expression what you use to match patterns

If you want to learn it with an interactive website : [RegexOne](https://www.regexone.com/)  
(Keep in mind that this is meant to teach you the basics, so read what's asked of you in each "exercise", as otherwise it can easily be cheesed)

Test and debug your regex : 
[Regex101](https://regex101.com/)

## Basics

### Common Tokens
- `.` : Match any character (except for `newline` or `line terminators`)
- `\d` : Match any digit (Equivalent to `[0-9]`)
- `\w` : Match any word character (Equivalent to `[a-zA-Z0-9_]`)
- `^` : Used at the start of the regex. Matches the start of a line.

### Quantifiers
- `+` : One or more of. For example, `A+` will match any amount of `A`.
- `?` : Zero or one of. 
- `*` : Any Amount of.
- `{ }` : Match what's before it, as many times as you set it to. For example `A{8}` will match 8 `A` in a row
- `{ , }` : Match what's before it, between the 2 values. For example, `B{2,5}` will match `B` between 2 to 5 times.

#### Modifiers
- `+?` : One or more of, as few times as possible
- `??` : Zero or one, as few times as possible
  
### Special Characters
- `|` : OR. Matches everything on the right or everything on the left. Can be restricted by using groups.
- `\` : Escape the character placed right after, and match it literally. For example, `\?` will match `?`

### Groups
- `( )` : Capture group. This makes everything captured inside this referencable (`$1`)
- `(?<> )` : Named Capture Group. Same as above, but you can reference it with the name. `(?<foo>bar)` > `${foo}`
- `(?> )` : Atomic Group. Non-capturing group. Isn't named and cannot be referenced. 
- `[ ]` : Match a set of characters that's defined inside. For example `[a-z]` will match any lowercase letter once
- `[^ ]` : Reverse Match. Any character included here will not be matched. Example `[^A-Z]` will match anything __except__ `A-Z`

## Example : 
[Here's a basic example](https://regex101.com/r/dbuFGN/1)  
In case the link is dead or doesn't work : 
```
^[A-Z][\w]{2} (?>quick )?brown (?<animal>fox|dog) [a-z]{4,5} (?>ov|und)er\ the lazy .{3}
```
```
The quick brown fox jumps over the lazy dog
The brown fox jumps over the lazy dog
The quick brown dog jumps over the lazy fox
The quick brown fox jump over the lazy dog
The quick brown fox jumps under the lazy dog
```
This is just a basic example to illustrate some of RegEx use.  