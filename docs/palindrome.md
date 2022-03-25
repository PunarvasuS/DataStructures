{% include nav.html %}
{% include project.html %}

## [Palindrome](https://replit.com/@LordPotashmallo/Menu#week_2/palindrome.py)
```
import re

class Palindrome:
  def __call__(self, n):
    str(n)
    new_n = (re.sub('[^a-zA-Z0-9]', '', n)).lower()
    return new_n == new_n[::-1]

def tester():
  pal_of = Palindrome()
  str_input = str(input("Enter a string or number (only accepts alphanumeric characters): "))
  if pal_of(str_input):
    print(str_input + " is a palindrome.")
  elif pal_of(str_input) == False:
    print(str_input + " is not a palindrome.")
  else:
    print("Oh no! Something went wrong!")
```
### Note
I remember seeing [this video](https://www.youtube.com/watch?v=zp4BMR88260) by Tom Scott(one of my favorite YouTubers) a while ago, and saw that he used RegEx to compare those letters to a string.
So, I decided I wanted to learn how to use RegEx.
I don't know if this is the best approach, but I learned RegEx, so I went with it. 
### Explanations:

```
(re.sub('[^a-zA-Z0-9]', '', n)).lower()
```
"re.sub" is a RegEx function that uses the syntax "re.sub(pattern, replace, string)". 
- "pattern" is the RegEx pattern you want to use. In my case, it was "[^a-zA-Z0-9]."
- The pattern matches with "any character that is not a-z, A-Z, or 0-9" or more succinctly, "any non-alphanumeric character."
- (going out of order so that it makes more sense) "string" is the string (or character) you want to replace (name of a variable)
- "replace" is the content that you want to replace "string" with (empty space in this case, to remove the character)
- "<string>.lower()" just makes all the letter lowercase so that a = A, b = B, etc. If ".lower()" wasn't there, 'Race car' would not count as a palindrome.

```
return new_n == new_n[::-1]
```
- "<string>[::-1]" is a way to create a new substring of a string that is the original string, but flipped (i.e. 'yellow' would become 'wolley').
- The reason I do this is to check whether or not the string is a palindrome, after the RegEx filtering, by checking the reverse of the string against itself.
If the word is a palindrome, this line will return 'True' (bool value, not string)

The rest of the program is pretty straightforward, it's just making the input a string, then checking if a word is a palindrome but calling the 'Palindrome' class.