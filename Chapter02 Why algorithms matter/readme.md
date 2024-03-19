Why Algorithms Matter

An algorithm is simply a set of instructions for completing a specific task.


Ordered Arrays

The ordered array is almost identical to the "classic" array. The only difference is that ordered arrays required that the values are always kept in order.
In terms of N, we'd say that for N elements in an ordered array, the insertion took N+2 steps in total.
The fewest steps occur when the new value winds up at the very end, since no shift are necessary. In this case, we take N steps to compare the new value with all N existing valusem plus one step for the inserting itself, yielding a total of N+1 steps.
While insertion is less efficient for an ordered array than for a classic array, the ordered array has a secret superpower when it comes to searching.


Searching an Ordered Array

def linear_search(array: list, search_value: int):
    for index, element in zip(range(len(list)), list):
        if element == search_value:
            return index
        elif element > search_value:
            break
    return None

As you can see, this linear_search method iterates over every element of the array, looking for the search_value. The search stops as soon as the element it's iterating over is greater than the searching_value, since we know that search_value will not be found further within the array.
The big advantage of an ordered array over a classic array is that an ordered array allows for an alternative searching algorithms. Thisalgorithm is know as binary search, and it is a much, much faster algorithm than linear search.


Binary search

Note that binary search is only possible within an ordered array. With a classic array, values can be in any order, and we'd never know whether to look to the left or right of any given value. This is one of the advantages of ordered arrays: we have the option of binary search.

def binary_search(array, searching_value):
    # First, we establish the lower and upper bounds of where the value
    # we're searching for can be. To start, the lower bound is the first
    # value in the array, while the upper bound is the last value:
    
    lower_bound = 0
    upper_bound = len(array) - 1

    # We begin a loop in which we keep inspecting the middlemost value
    # between the upper and lower bounds

    while lower_bound <= upper_bound:
        
        # We find the midpoint between th upper an lower bounds:

        midpoint = (upper_bound + lower_bound) // 2

        # We inspect the value at the midpoint

        value_at_midpoint = array[midpoint]

        # If the value at the midpoint is the one we're looking for, we're done.
        # If not, we change the lower or upper bound based on whether we need
        # to guess higher or lower:

        if search_value == value_at_midlepoint:
            return midpoint
        elif search_value < value_at_midpoint:
            upper_bound = mdpoint - 1
        elif search_value > value_at_midpoint:
            lower_bound = midpoint + 1

    # If we've narrowed the bounds until the've reached each other, that
    # means that the value we're searching for is not contained within
    # this array:

    return None


Binary search vs. linear search

With ordered arrays of a small size, the algorithms of binary search doesn't have much of an advantage over linear search.
With an array containing 100 values, here are maximum number of steps each type of search would take:
    - Linear search: 100 steps
    - Binary search: 7 steps
When we use binary search, however, each guess we make eliminates half of the possible cells we'd have to search.
The pattern is unusually efficient: each time we doubt the data, the binary search algorithm adds just one more step.
So for linear search, each time we doubt the size of the array, we doubt the number of steps of our search. For binary search, though, each time we double the size of the array, we only need to add one more step.
With an array of 10000 elements, linear search can take up to 10000 steps, while binary search takes up to a maximum of just 13 steps. For an array of size one million, linear search would take up to one million steps, while binary search would take up to just 20 steps.
Keep in mind that ordered arrays aren't faster in every respect. As you've seen, insertion in ordered arrays is slower than is standard arrays. But here's the trade-off: by using an ordered array, you have somewhat slower insertion, but much faster search.


Pop Quiz

The question: We said that for an ordered arrays with 100 elements, binary search takes seven steps. How many steps would binary search take on an ordered array containing 200 elements?
The answer: 8 steps.
