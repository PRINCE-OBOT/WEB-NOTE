localeCompare() is a method in JavaScript that allows you to compare two strings based on the language-specific sorting rules. It returns a number that indicates whether the first string comes before, after, or is the same as the second string in a given locale.

#### Behaviour 

1. All elements are sorted either in ascending or descending or uniformly.

2. By default if two or more elements are the same but are case sensitive the element with small letters comes before the capital letter.

3. In other to avoid this you may want to avoid the same elements with different case to interchange position. This is why .to lowercase() is used or {sensitivity:"base"}, as this treat it equally without interchanging their position. 

**Syntax:

string1.localeCompare(string2, [locales], [options])

#### string
The string to compare with string1.

#### locales (optional)
– The language or region for sorting. It can be either "fr", "en", "es". It may varies base on **region**, it default is ("en")

#### options (optional) – 

An object specifying how the sorting should behave.

**sensitivity** 
If sensitivity is not provided it behaves like **accents** and **case**, meaning they are not treated the same, lowercase letters comes before them.

*accent*
`"ñ".localeCompare("n")`// 1

*case*
`"N".localeCompare("n")` //1

______but_
{sensitivity : "base"} treat them equally

`"ñ".localeCompare("n", "en", {sensitivity : "base"})`// 0 

`"N".localeCompare("n", "en", {"sensitivity: "base"})` // 0


