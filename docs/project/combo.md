{% include nav.html %}
{% include project.html %}

## 03/24/22 [Combinations](https://replit.com/@LordPotashmallo/Menu#week_2/combo.py)

### Key Learnings:
- Reused old files/functions (recur_factorial)
- Don't need 'self.comb', but have it anyways
- var comb stores the combinations formula but with recur_factorial

```
from week_2 import fibfac

class Combination: 
  def __init__(self):
    self.comb = 1
  def __call__(self, n, r):
    if r > n: # checks if r is less than n; r must be less than n to work 
      print("Number of choosing objects cannot be greater than total amount of objects")
    elif r == n: #  checks if r is the same as n 
      return self.comb
    else: # follows formula to calculate combination
          # uses recur_factorial made in other file 
      comb = fibfac.recur_factorial(n) / (fibfac.recur_factorial(r) * fibfac.recur_factorial(n - r))
      return int(comb)

def comb_test_oop(): 
  comb_of = Combination()
  n = int(input("Enter total number of objects: "))
  r = int(input("Enter number of choosing objects: "))
  print(comb_of(n,r))

def comb_test_imp():
  n = int(input("Enter total number of objects: "))
  r = int(input("Enter number of choosing objects: "))
  print(combo(n,r))


def combo(n, r):
  if r > n: 
    # checks if r is less than n; r must be less than n to work 
        print("Number of choosing objects cannot be greater than total amount of objects")
  elif r == n: 
    #  checks if r is the same as n 
    print("1")
  else: 
    # follows formula to calculate combination
    # uses recur_factorial made in other file 
    comb = factorial.recur_factorial(n) / (factorial.recur_factorial(r) * factorial.recur_factorial(n - r))
    print(int(comb))
```
