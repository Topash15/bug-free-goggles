# Title (replace with your title)

Introductory paragraph (replace this with your text)

## Summary

Briefly summarize the regex you will be describing and what you will explain. Include a code snippet of the regex. Replace this text with your summary.

Matching a URL – /^(https?:\/\/)?([\da-z\.-]+)\.([a-z\.]{2,6})([\/\w \.-]*)*\/?$/

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

  Taking a look at our URL expression, there are two anchors that stand out. The first anchor is listed right at the start. The "^" character means the expression will match the beginning of the string. Without this beginning anchor, there can be characters before the url that we are trying to target.

Without Beginning Anchor

![withoutAnchor](https://user-images.githubusercontent.com/56897774/136708029-1f1aa5e4-e871-492b-8b7b-26fd04470057.png)

With Beginning Anchor

![withAnchor](https://user-images.githubusercontent.com/56897774/136708037-89a4683e-8a3d-4eaa-877d-6a0b3c94d945.png)


  At the other end of the expression is a $. This is the opposite of the "^" beginning anchor. The "$" character matches to the end of the string (or line depending on the multiline flag). Removing the end anchor would allow for text to be added beyond the link that we are targeting.

Without End Anchor

![withoutEndAnchor](https://user-images.githubusercontent.com/56897774/136708316-6fa1c46d-b9f5-4d12-a117-cf67a6f687d1.png)

With End Anchor

![withAnchor](https://user-images.githubusercontent.com/56897774/136708327-184be0fc-d698-4b7b-967a-b91fab67361b.png)

### Quantifiers

{2,6}

? optional

* star

### OR Operator

/d all digits

a-z

### Character Classes

### Flags

### Grouping and Capturing

group 1-4

### Bracket Expressions

### Greedy and Lazy Match

### Boundaries

### Back-references

### Look-ahead and Look-behind

## Author

A short section about the author with a link to the author's GitHub profile (replace with your information and a link to your profile)
