{% include nav.html %}
{% include project.html %}

## 3/9/22 - [Christmas Tree](https://replit.com/@LordPotashmallo/Menu#week_0/tree.py)

### Key Learnings:
- replit mobile (the mobile site) is actually usable!
  - i used it to write this program
- Brian Tang added some more details (colored portions of the tree)
- [More Details](#details)

```
import math

try:
  layers = int(input("How many layers of the pyramid (enter an integer): "))
except:
    print("That\'s not an integer! Please run again.")
    exit()
star = "* "
x = 1
spaceNum = layers

print("Here's your tree")

while x <= layers:
  print((spaceNum * " ") + star)
  star += "* "
  spaceNum -= 1
  x += 1

print(" " * math.floor(layers/1.11) + "***")
```
## Details

### Declarations
- The try: except: is to make sure the user input is int, and then continues with the rest of the program
- 'layers' is just the number of layers the tree should have.
- 'star' is a variable made to contain "*" and a space. 
- 'x' is just a variable used to iterate later in the program. 
- 'spaceNum' is a variable created to decrement in the while loop without changing the condition (which is what would happen if i just decremented 'layers' in the while loop)

### Code
- The first line defines the while loop's condition: to iterate until x reaches the amount of layers.
- The second line prints out 'spaceNum' amount of spaces, then prints the first star of that row
- The third line increments 'star's value by "* ", instead of a number amount (it concatenates "+ " to the end of star each iteration of the while)
- The fourth line *decrements* 'spaceNum', as the relationship between 'spaceNum' and the amount of stars in the row should be inverse.
- The fifth line simply increments 'x' so that the loop ends at some point (i forgot to add it on my first run, and it was really annoying)
- Prints asterisks somewhat in the middle of the tree

My friend(Ethan Guo)'s attempt at this challenge:

```
layers = input("How many layers of the pyramid: ")

def pyramid(layers):
  layers = int(layers) 
  current_layer = 1
  while current_layer <= layers: 
    # Create Spaces 
    strspaces = ''
    nspaces = 1 
    while nspaces <= (layers - current_layer):
      strspaces = strspaces + ' '
      nspaces += 1 
    # Create Stars 
    strstars = ''
    nstars = 1 
    while nstars <= current_layer: 
      strstars = strstars + '* '
      nstars += 1 

    print(strspaces + strstars) 
    current_layer += 1 
  '''
  base = layers/2
  base = math.ceil(base)
  print(base)
  base_space = ''
  for q in range(base + 1): 
    base_space = base_space + ' '
  print(base_space + '***') '''
    
pyramid(layers)
```

Ethan's code is much longer than mine, including 2 nested while loops inside of 1 while loop.
He declared quite a few variables inside his function, rather than outside, but I'm not sure if that's a big deal.
He also made a function and then...called it with a variable. A bit unnecessary, but it works, and thats all that matters.
