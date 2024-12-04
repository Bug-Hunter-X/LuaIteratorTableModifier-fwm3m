# Lua Pairs Iterator and Table Modification

This repository demonstrates a common error in Lua related to the `pairs` iterator and table modification during iteration.  The original code attempts a recursive traversal of a nested table.  However, if the table structure is modified during iteration (by adding or removing elements), the `pairs` iterator's behavior becomes unpredictable, often leading to skipped elements or infinite loops. The solution offers a safer approach for iterating over tables that might be modified.

## Bug

The `bug.lua` file contains a function `foo` that recursively iterates over a nested table using `pairs`.  If elements are added or removed within the nested table during iteration, the `pairs` iterator will not correctly process all the table elements. This can lead to unpredictable results and errors. 

## Solution

The `bugSolution.lua` demonstrates how to safely iterate through a table even if it is modified during the process.  This involves creating a copy of the table keys before starting the iteration. 