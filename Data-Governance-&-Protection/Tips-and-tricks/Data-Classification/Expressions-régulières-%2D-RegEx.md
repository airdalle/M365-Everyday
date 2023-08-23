[[_TOC_]]

# Definition
Wikipedia : 
> A sequence of characters that forms a search pattern, mainly for use in pattern matching with strings, or string matching.

# RegEx sandbox : build, test, and debug regex
https://regex101.com/
https://www.rexegg.com

# Regex generator
https://regex-generator.olafneumann.org/

# Exemples de Regex
## Mot de passe
* > (?=[^\s]\*[a-z])(?=[^\s]*[A-Z])(?=[^\s]*[0-9])(?=[^\s]\*[~!@#$%^&*\-_+=`|\\(){}\[\]:;"'<>,.?\/])(?=[^\s]{10,})(?![^\s]*(http|www|\.com|\.org))[^\s]\*
==> https://regex101.com/r/GQNbz1/1

A tester : 
* > (?=[^\s]*[a-z])(?=[^\s]*[A-Z])(?=[^\s]*[0-9])(?=[^\s]*[~!@#$%^&*\-_+=`|\\(){}\[\]:;"'<>,.?\/°¨£¤§])(?=[^\s]{8,})(?![^\s]*(http|www|\.com|\.org))[^\s]*
* > (?=[^\s]*[[:lower:]])(?=[^\s]*[[:upper:]])(?=[^\s]*[[:digit:]])(?=[^\s]*[[:punct:]])(?=[^\s]{8,})(?![^\s]*(http|www|\.com|\.org))[^\s]*

## Date
* **YYYYMMDD**
> \d{4}(0[1-9]|1[0-2])(0[1-9]|[12][0-9]|3[01])

