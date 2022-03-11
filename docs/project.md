{% include nav.html %}
# [My GitHub](https://github.com/PunarvasuS/DataStructures/)
# [My Replit](https://replit.com/@LordPotashmallo/)

# Data Structures Project

## 3/10/22 - [Menu](https://replit.com/@LordPotashmallo/Menu)

```
menu.py:

import math 

# Creates Title 
border = "=" * 40
banner = f"\n{border}\nWhat do you want to do with the list\n{border}"

def menu():
  print(banner)
  options = [
    ["swap", "swap.py"], 
    ["matrix", "matrix.py"], 
    ["tree", "tree.py"], 
  ]

  functions = {}
  functions[0] = ["Exit"] 
  for op in options:
    index = len(functions)
    functions[index] = op

  for key, value in functions.items():
    print(key, '->', value[0])

#  number = 1 
#  for thing in functions: 
#    print( str(number) + " " + str(thing)
#    number = int(number) + 1  

  choice = input("What function would you like: ")

  try: #try converting to integer
    #convert to number
    choice = int(choice)
    if choice == 0: #exit choice, stop loop
      return        #return means leave function
    try:  #try to run as playground function
      action = functions.get(choice)[1]
      exec(open(action).read())
    except:
      try:  #try to run as function
        action()
      except:
        print(f"Bad action: {action}")
      #end function try
    #end playground try
  except ValueError: #not a number error
    print(f"Not a number: {choice}")
  except: #traps all other errors
    print(f"Invalid choice: {choice}")

  menu()

if __name__ == "__main__": 
  menu()
```

## 3/10/22 - [Animation](https://replit.com/@LordPotashmallo/Animation)

```
import time

# terminal print commands
ANSI_CLEAR_SCREEN = u"\u001B[2J"
ANSI_HOME_CURSOR = u"\u001B[0;0H\u001B[2"
OCEAN_COLOR = u"\u001B[44m\u001B[2D"
SHIP_COLOR = u"\u001B[32m\u001B[2D"
RESET_COLOR = u"\u001B[0m\u001B[2D"

def ocean_print():
# print ocean
print(ANSI_CLEAR_SCREEN, ANSI_HOME_CURSOR)
print("\n\n\n\n")
print(OCEAN_COLOR + "  " * 35)

# print ship with colors and leading spaces
def ship_print(position):
print(ANSI_HOME_CURSOR)
print(RESET_COLOR)
sp = " " * position
print(sp + "  ___________________")
print(sp + " | |         0     \ \ ")
print(sp + " | |        /|\     \ \______")
print(sp + " | |        / \           | | ")
print(sp + " | |______________________/ / ")
print(sp + "    / /                \ \ ")
print(sp + "   ___                  ___ ")
print(sp + "  /   \                /   \   ")
print(sp + " |  O  |              |  O  |  ")
print(sp + "  \___/                \___/   ")
print(RESET_COLOR)

# ship function, iterface into this file
def ship():
ocean_print()
# loop control variables
start = 0  # start at zero
distance = 60  # how many times to repeat
step = 2  # count by 2

# loop purpose is to animate ship sailing
for position in range(start, distance, step):
ship_print(position)  # call to function with parameter
time.sleep(.1)

ship()
```

## 3/9/22 - [Christmas Tree](https://replit.com/@LordPotashmallo/TreePyramid)

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

My friend Ethan Guo's attempt at this challenge:

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