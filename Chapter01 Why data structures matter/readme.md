Data Structures

Data is a board term that refers to all types of information, down to the most basic numbers and strings.
Data structures refer to how data is organized. You're going to learn how the same data can be organized in variety of ways.


The Array: The Foundation Data Structure
The array is one of the most basic data structures in computer science. An array is a list of data elements.
The size of an array is how many data elements the array holds.
The index of an array is the number that identifies where a piece of data lives inside the array.


Data Structure Operations
Many data structures are used in four basic ways, which we refer to as operations. There operation are:
    - READ. Reading refers to looking something up at particular spot within the data structure.
    - SEARCH. Searching refers to looking for a particular value within a data structure.
    - INSERT. Insertion refers to adding a new value to our data structure.
    - DELETE. Deletion refers to removing a value from data structure.


Measuring Speed
However, we can measure the speed of an operation in terms of how many computational steps it takes. If Operation A takes 5 steps, and Operation B takes 500 steps, we can assume that Operation A will always be faster than Operation B on all piece of hardware. Measuring the number steps is, therefore, the key to analyzing the speed of an operation.
Measuring the speed of an operation is also known as measuring its time complexity.


Reading
A computer's memory can be viewed as a giant collection of cells.
When the computer reads a value at a particular index of an array, it can jump straight to that index because of the combination of the following facts about computer:
    1. A computer can jump to any memory address in one step.
    2. Whenever a computer allocates an array, it also makes note ar which memory address the array begins.
Now, these facts explain how the computer can find the first value of an array in a single step. However, a computer can also find the value at any index by performing simple addition.


Searching
Searching an array means looking to see whether a particular value exists within an array and if so, at which index it;s located.
This is an important fact about computers: a computer has immediate access to all of its memory addresses, but it has no idea offhand what values are contained at each memory address.
Another way of saying this is that for N cells in an array, linear search would take a maximum of N steps.
In any case, it's clear that searching is less efficient than reading, since searching can take many steps, while reading always takes just one step no matter the size of the array.


Insertion
The efficiency of inserting a new piece of data int an array depends on where within the array you're inserting it.
The Add to the end of a list, such an insertion takes just one step.
This is true due to another fact about computer: when allocating an array, the computer always keeps track of the array's size.
The inserting a new piece of data at the beginning or in the middle of an array is a different story. In these case, we need to shift piece of data to make room for what we're inserting, leading to additional steps.
The worst-case scenario for insertion into an array - that is, the scenario in which insertion takes the most steps - is when we insert data at the beginning of the array. This is because when inserting at the beginning of the array, we have to move all the other values one cell to the right.
We can say that insertion in a worst scenario can take N+1 steps for an array containing N elements. This is because we need to shift all N elements over, and then finally execute the actual insertion step.


Deletion
Deletion from an array is the process of eliminating the value at a particular index.
Like insertion, the worst-casescenarion of deleting an element is deleting the very first element of the array. This is because index 0 would become empty, and we'd have to shift all the remaining elements to the left to fill the gap.