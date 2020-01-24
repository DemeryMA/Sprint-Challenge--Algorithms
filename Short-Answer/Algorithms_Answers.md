#### Please add your answers to the ***Analysis of  Algorithms*** exercises here.

## Exercise I

a) O(n) for every additional unit in 'n', the runtime increases by that number.

a < 1 * 1 * 1 = a < 1 a = a+1 runs once a< 2 * 2 * 2 = a < 8 a = a+4 runs twice, etc.



b) The answer is O(n*log n), the for loop is n and the while loop is log n.


c) The answer is O(n) since were subtracting 1 from n

## Exercise II

get mid_point = n // 2

Test to see if egg breaks at mid_point.

if the egg breaks, take lower half of the array, find halfway point and repeat

if the egg doesn't break, take upper half of array, find halway point and repeat.

thrn repeat this process until you only move in one direction by one spot. If the egg breaks, and you move one spot down and the egg doesn't break.. The previous spot is 'f'.

if the egg doesn't break and you move up one and it does break, that last one is your 'f'

Since we are halving every time, the runtime complexity would be O(log n)

def egg_drop(n, f):
    if len(n) <= 1:
      return n
    #divide the floors into two halves until the output is less than f
    mid_point = len(n) <!-- n --> // 2
    x = n[:mid_point]
    y = n[mid_point:]
    if f in x:
      return egg_drop2(x, f)
    elif f in y:
      return egg_drop2(y, f)
    else:
      return "Floor is not in the building"

      
