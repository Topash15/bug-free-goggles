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

Quantifiers go after a token and indicate that the preceeding requirements must be met a certain amount of times.

The first quantifier in our expression is the "?" character which says that the preceeding token is optional. Let's look at that group of our expression: (https?:\\/\\/)?
There are actually two of the optional quantifiers in this section. The first one listed after the https refers to the "s" character. This allows for us to find links that begin with http or https. The second optional quanitifier comes after the entire group. This one says that the entire group is optional. As you can see below, we can find www.google.com even though it does not have a http:// or https:// at the beginning. That is thanks to this quantifier.

![optional quantifer example](https://user-images.githubusercontent.com/56897774/136709011-45e62a33-96e9-4b80-81f5-761331884852.png)

The next type of quantifier in our expression is the "\*" character. This quantifier allows for all of the preceeding token to be matched. We can see this in our group for finding what it beyond the ".com" portion of the link. That group looks like this: ([\\/\\w \\.-]\*)
This group is looking for any slashes, words, periods, and/or hyphens. If we remove the star quantifier, we will only get the last character found by our expression. See the bottom of this screenshot where the Group 4 text is displayed:

![no star quantifier](https://user-images.githubusercontent.com/56897774/136709383-9e9cb958-b723-4cf0-9fd1-95afe86caa6e.png)

Adding the "\*" after the character set lets us capture the portion rather than the last character:

![star quantifier](https://user-images.githubusercontent.com/56897774/136709430-d30d6306-29d1-453b-849a-adfca34ab112.png)

We also have a "+" quantifier which is similar to the star, but it will match 1 or more of the token that preceeds it. In our case, it's used in group 2: ([\da-z\.-]+)
Without the plus, we would only be able to find a single character website.

![without plus](https://user-images.githubusercontent.com/56897774/136709855-a923eeaa-3855-46ac-8363-5a9044948513.png)

 Why can't we use a star quantifier in this case? The star will grab the entire section of the URL that we want, *but* the star quantifier will also allow for nothing to be selected. Our expression would recognize any lowercase text that follows a period as a URL if we used the star. The plus requires at least one character to match *and* it will grab all that follows within the parameters.

Now for our last quantifier. The star quantifier let us select 0 or more instances of our token, the plus quantifier lets us select 1 or more instances, and the optional quantifier lets us select 0 or 1 instance. What if we want a string that's a certain length? Let's take a look at the part of the expression that is grabbing the "com" section of our link. That group looks like: "([a-z\.]{2,6})" Those curly brackets are the key. The 2 and 6 signify that we want between 2 and 6 characters for this group. With this quantifier, the first number is the minimum amount and the second is the maximum. If you want to jus tset a minimum, you can put a single number followed by a comma in the curly brackets like so: {2,}

### OR Operator

### Character Classes

In order to determine which characters we want to select, we need to provide a character class in our expression. One type of character class that's listed within our expression is "/d". This stands for all digits and will select characters if they are a number between 0-9. Another class listed is the "/w" which stands for all words. Words are considered any alphanumeric character so it will select and lowercase and uppercase letter as well as an number between 0-9. If there are more specific characters that you want to select, you would specify with a character set. A character set requires squared brackets "[]"


### Flags

### Grouping and Capturing

You'll notice that the expression has a few parentheses pairs. This helps us to breakdown our selection into groups that can be used later. The whole URL will be matched, but you can see below that the link is broken up into 4 groups. Group 1 lists the http://, group 2 gives the "www." and the website's name, group 3 gives the domain (in this case .com), and group 4 gives any further information on the link. The group names are defaulted, but they can be assigned. If you put "?<Beginning>" within the parentheses of a group, it would assign the name Beginning to that group.
  
  ![image](https://user-images.githubusercontent.com/56897774/136715557-701605f9-83a6-4751-95a2-eb0db3878e97.png)


### Bracket Expressions

### Greedy and Lazy Match

### Boundaries

### Back-references

### Look-ahead and Look-behind

## Author

A short section about the author with a link to the author's GitHub profile (replace with your information and a link to your profile)
