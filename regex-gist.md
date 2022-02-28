# Computer Science: Regex Tutorial

  In this tutorial I will take you through the foundations of Regex, also known as Regular Expression. 
  This will create a better understanding of how usernames, emails, passwords, etc. are matched.
  Hopefully when you reach the end of this tutorial you will be able to demonstrate your comfortability with Regex. 

## Summary
  For this tutorial, I will go over how to use regular expressions in order to match an email.
  This list of characters that will be used for this are:
  /^([a-z0-9_\.-]+)@([\da-z\.-]+)\.([a-z\.]{2,6})$/
  
  We will focus on trying to get a match with this assortment of characters. 
  You can specify the length and order of these characters in regex. 
  We will work together to create an email that matches the criteria the you set.
  
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
To start off we will begin by talking about anchors and how to apply them in our experience with regex. 
First off, it's important to note that anchors are **not** used to match any characters. 
They are primarily used before, after and between characters. This is used to hold our match into a certain position. 
This can be done using the ^ (caret) symbol and $ (dollar sign) symbol

For example if you apply ^a in abc, it would match a as it is first.

However if you apply ^b in abc, it would not match see as how b cannot be matched after the first character in the string.

Example: 

Say we wanted to match the beginning of our string so we use ^z

The string applied is: `zebras are my favorite animal.`

The string should match.

### Quantifiers
When it comes to specifying the length of your string this is what you would use in order to do that.
Quantifiers help indicate the number of characters and expressions that needed to match.
The Quantifiers for Regex are as follows:
  * 0 or More
  + 1 or More
  ? 0 or One
  {n} Exact Number
  {n,m} Min and Max range of numbers
  
  Example:
  
  If I were to say 3*, that is setting the criteria to be that the email should match zero or more "3" characters
  
  Code Example:
  
  zebra{2}
  
  `I love my zebra. I love my zebraa. I love my zebraaa.`
  
  In the top example the second sentence in this string would match seeing as how it has the exact number of a's that I set the criteria for
  

### OR Operator
The OR operator is a pretty straightforward expression that will allow you to have two options available.
This is typically done using the | (bar) symbol. Each separated option should be held within parentheses.
For example:

 ` I love (zebras|giraffes).`
 
 There this expression with match either of the following strings:
 
 ` I love zebras.`
        OR
 ` I love giraffes.`

### Character Classes

When it comes to character classes, you can single out certain characters you want the regex engine to match with or you can even make a range of characters that the engine could choose from.
This can be done with the [] brackets symbol.
For example:

If I wanted to match "recognize" despite the differences in UK and US spellings

I would use [sz]

so that both `recognise` and `recognize` could match

When it comes to trying to match ranges, you would just apply your range within the character classes
For example:

`[A-Z,a-z,0-9]`

### Flags
Regex has flags you can include as an option that allow for different functionality. 
They can be used separately or together in any order

Examples of Flags and their functionality:

- `d`: Generate indices for substring matches.
- `g`: Global Search
- `i`: Case-insensitive search
- `m`: Multi-line search
- `s`: Allows . to match newline characters
- `u`: Treat a pattern as a sequence of unicode code points
- `y`: Perform a "sticky" search that matches starting at the current position in the target string

### Grouping and Capturing

Grouping and capturing is a way to find a specific character or phrase.
This is a way to treat multiple charcters as a single unit.
This is typically done using the `()` (parentheses) symbols.

For example 
The string you are using to match is: `Erin cooked cupcakes in the kitchen.`

The grouping used could be: `/c(o|u)/g`s so that we would match the following



### Bracket Expressions
Brackets are used to indicate a set of characters to match. Any chracter within the brackets will match.

For example:

If you wanted to match `zebra` in the criteria of ([abc])

then the "b" and "a" in the word "zebra" would then match

### Greedy and Lazy Match

When it comes to Greedy and Lazy Match
The Greedy Match tries to match the longest possible string while the Lazy Match will try to match the smallest possible string.
By default, all quantifiers are greedy as they are trying to match the longest possible string.
To Lazy Match, you would add a `?`

### Boundaries

Word boundaries are used to find whole words. Much rather that matching a character on it's own, word boundaries primarily serve to mark the beginning and the end of an alphanumeric sequence of characters.
Word Boundaries are typically held by the character `\b`

For example:

If you were to use `\bzebra\b you would get a match in the string ` exclusive zebra zoo`

### Back-references

Back references are used to match the same text that was matched by a capturing group
Back references are typically done with `\1` or `$1`. 

For Example:

If we wanted to find any instance of repeated words in our string we can use the code: 

`\b(\w+)\s\1\b`

If our string was: 

` the zebra ran ran out of the zoo. The zoo keeper couldn't find find them.`

The repeated words would match in this case.

### Look-ahead and Look-behind

Look-ahead and look-behind which when both are combined are considered a look-around. They are typically used to assert that match was succesful or not.

The example code for a look-ahead
`X(?=Y)`

The example code for a look-behind

(?<=Y)X


## Author

Raniah Jeanlys is an aspiring full stack developer. She graduated with a major in Finance and a minor in Law and Justice from North Carolina State University. After graduation she gained experience with Python and its application Financial Technology through the FinTech bootcamp held at UNC Charlotte. Afterwards, to further her experience and learning with programming she decided to take a course about Full Stack Development through a Coding Bootcamp from UNC Chapel Hill. She is working to build her knowledge and practice with programming in the hopes that she will eventually find a job opportunity to meet other programmers and have a growth opportunity.

- [Raniah Jeanlys Github](https://github.com/raniahj)