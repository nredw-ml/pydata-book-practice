# Chapter 3, Section 3.1: Data Structures and Sequences

## Conceptual Questions & Answers

**Q: What is the key difference between tuples and lists in terms of mutability? What happens when you have a mutable object (like a list) inside a tuple?**  
My answer: Tuples are immutable and lists are mutable. While a list is mutable, if it is inside of a tuple then it will not be modifiable after assignment. For tup = ('a', [1, 2], 'b'), you would not be able to modify the list, i.e., you could not do tup[1] = [2,4].  
Correct: Tuples are immutable (can't change which objects they reference) and lists are mutable. However, if a mutable object like a list is inside a tuple, you CAN modify the contents of that list (e.g., tup[1].append(3)), but you CANNOT replace the list object itself (e.g., tup[1] = [2, 4]).

**Q: When would you choose to use list.append() + list.extend() vs list concatenation with +? What are the performance implications?**  
My answer: You would choose list.append() or list.extend() when you are trying to build up a large list, as concatenation with + is a relatively more expensive operation in terms of computation as a new list must be created on each use. In memory, with list.append() or list.extend(), the same object is still referenced once the operation is complete, while with concatenation with +, a new object is created and therefore a new reference in memory is created. Additionally, .append() will wholesale add the entire object into the list that is passed into it, while .extend() will iteratively add each element in a sequence passed to it.

## Key Takeaways
- Mutable objects inside immutable tuples can still be modified in-place - the tuple holds references that can't change, but mutable objects themselves can
- List concatenation with + creates a new list object each time (expensive for loops), while extend() modifies the existing list in-place (more efficient)
- Recursion allows functions to call themselves to handle arbitrary levels of nesting - each call handles one level and returns results up the chain

## Functions/Methods Practiced
- **tuple**: count()
- **list**: append(), insert(), pop(), remove(), extend(), sort()
- **dict**: get(), pop(), keys(), values(), items(), update(), setdefault()
- **set**: union(), intersection(), difference(), add(), remove()
- **built-in**: enumerate(), sorted(), zip(), reversed(), isinstance(), hash()

## Practice Problem Results
- **Easy**: ✓ solved independently
- **Medium**: ✓ solved independently
- **Hard**: ✓ solved with hints

## To Review (Optional)
- Common pitfall: Never use Python built-in names (list, dict, tuple, set, etc.) as variable names

---

**Date completed**: October 21, 2025  
**Time spent on practice**: 90 minutes  
**Overall confidence**: High