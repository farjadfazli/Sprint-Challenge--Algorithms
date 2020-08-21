#### Please add your answers to the ***Analysis of  Algorithms*** exercises here.

## Exercise I


a) We will analyze the below code block by comparing how many steps the block takes when n = 1 and compare it to how many steps it takes when n = 10.

If n = 1:
while (a < n * n * n): 
# 2 multiplications (2 steps)
    a = a + n * n 
# 1 multiplication and 1 division (2 steps)
a = 0
# total = 4 steps

If n = 10:
while (a < n * n * n): 
# 20 multiplications (20 steps)
    a = a + n * n 
# 10 multiplications and 10 additions (20 steps)
a = 0
# total = 40 steps

Conclusion: Since increasing the input size by 10x resulted in a 10x increase in the number of steps we can conclude that the time complexity of this code block is linear and increases with O(n).



b) 

sum = 0
    for i in range(n):
# for loop takes n steps to iterate through the range
        j = 1
        while j < n:
            j *= 2
# since j is doubling with every iteration of the while loop and the loop runs until j = n, it will take log(n) steps to complete
            sum += 1
# adding 1 to sum is a constant time operation which is not affected by growth of n

Conclusion: The time complexity of this code block is O(n) * O(log n) = O (n log n)


c)
def bunnyEars(bunnies):
      if bunnies == 0:
        return 0

      return 2 + bunnyEars(bunnies-1)
# Let bunnies = n. Since bunnies is reduced by 1 each time, this recursive call will run n times. If n = 1 it runs once and if n = 10 then it runs 10 times (linear relationship).

Conclusion: The time complexity of this code block is O(n).

## Exercise II

We need to find the floor f such that if an egg is dropped from floor < f it doesn't break. If we think of the n-story building as a sorted list from 1 to n with each entry representing the respective floor, then we can do a binary search to find floor f. This will work in the following way: 

start by dropping egg from floor n // 2

if egg breaks:
    eliminate the floors above and move to the midpoint of the remaining floors
if egg doesn't break:
    eliminate the floors below and move to the midpoint of the remaining floors

Repeat the above if-statements accordingly until you move between consecutive floors f and f - 1. This will result in one broken egg (thrown from floor f) and one intact egg (thrown from floor f - 1). Since we halve the number of floors with each iteration, the time complexity of this task is O(log n).


