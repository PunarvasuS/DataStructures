{% include nav.html %}
{% include project.html %}

## 3/10/22 - [Menu](https://replit.com/@LordPotashmallo/Menu)

```
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
