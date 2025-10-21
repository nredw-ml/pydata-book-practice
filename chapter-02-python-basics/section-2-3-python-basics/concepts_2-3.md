# Chapter 2, Section 2.3: Python Language Basics

## Conceptual Questions & Answers

**Q: When you write `a = [1, 2, 3]` and then `b = a`, what happens when you do `a.append(4)`? Why does `b` also show `[1, 2, 3, 4]`?**  
My answer: When you do a.append(4), 4 is appended to the object that is referenced by both a and b. A copy of the object is not made upon assignment of b = a, but rather b is made to point to the same object as a. That is why appending a impacts the values in the list of b as well.

**Q: Python is described as "strongly typed" despite not requiring variable type declarations. What does this mean? Give an example of what Python won't let you do that a weakly typed language might allow.**  
My answer: Python is a strongly typed language because it will not allow for implicit variable changes in operations that other languages might. For example, if you try to add the string '5' to the integer 5, you will receive an error. A weakly typed language might either implicitly cast the string to an integer and result with 10, or cast the integer to a string and return '55'.

**Q: What's the fundamental difference between `a_list[0] = 'new'` and `a_string[0] = 'n'`? Why does one work and the other doesn't?**  
My answer: The fundamental difference is the mutability of the objects in question. For a_list[0] = 'new', this will work because lists are mutable objects in Python and therefore can be updated and changed. However, a_string[0] = 'n' will not work because strings are immutable and therefore not able to be changed; a new string would need to be declared.

**Q: In the expression `if a < b or c > d:`, if `a < b` is True, what happens to `c > d`? Why might this behavior be useful?**  
My answer: In that expression, if a < b is true, then c > d is not even evaluated as the control flow is short circuited. Its usefulness includes performance benefits (expensive computations won't run unnecessarily), safety (can check for None before accessing attributes), and guard clauses (first condition can protect the second from errors).

## Key Takeaways
- Python uses references not copies when assigning objects - understanding this is crucial for working with mutable data structures
- Strong typing prevents implicit type conversions, catching potential bugs early
- Try/except blocks catch specific exception types - ValueError for conversion failures vs TypeError for operation failures

## Functions/Methods Practiced
- **Built-in functions**: id(), isinstance(), type(), float(), int(), str()
- **String methods**: replace(), encode(), decode(), format()
- **Control flow**: if/elif/else, for loops with continue/break, while loops, try/except

## Practice Problem Results
- **Easy**: ✓ solved independently
- **Medium**: ✓ solved with hints
- **Hard**: ✗ not attempted

## To Review (Optional)
- Custom iterator classes with `__iter__` and `__next__` methods (saved for after data structures section)
- The distinction between `type()` checks and `isinstance()` for type validation

---

**Date completed**: October 2025  
**Time spent on practice**: 60+ minutes  
**Overall confidence**: Medium