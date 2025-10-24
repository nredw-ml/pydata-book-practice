# Chapter 3, Section 3.2: Functions

## Conceptual Questions & Answers

**Q: A colleague writes a function to track how many times it's been called, but it always returns 1. What's the problem, and what are TWO different ways to fix it?**  
My answer: The problem is that whenever count_calls is called, it is redefining the count back to zero each time. One way they could fix the function is to define count in the namespace outside of the function, and then refer to it using the global keyword. A better way would be to still define it outside of the function, but then update the function to accept count as an argument rather than using the global keyword.  
Correct: While passing count as an argument would require manually tracking state each time, a better second approach is using a closure with `nonlocal` to encapsulate the state without global variables.

**Q: What's the key difference between a list comprehension `[x**2 for x in range(1000000)]` and generator expression `(x**2 for x in range(1000000))`?**  
My answer: Version A is a list comprehension, which will return a list from executing the for loop. However, Version B is a generator, and will not execute until passed into a function to iterate over it (such as list). Version B would be a better choice for preserving memory until the generator is actually needed and called, as opposed to Version A which executes immediately and will be stored in memory.

**Q: Why does `list(clean)` return an empty list after `list(upper)` was called, when `upper = map(str.upper, clean)`?**  
My answer: Does this have something to do with generators only executing when called? I'm not sure.  
Correct: Iterators (including map objects) can only be consumed once. When you call `list(upper)`, it consumes both `upper` and `clean`. After that, `clean` is exhausted and returns an empty list.

**Q: What's potentially dangerous about using `except:` to catch all exceptions, and how would you improve it?**  
My answer: This can be dangerous because you're now suppressing all exceptions, even legitimate bugs. For example you might want to throw an exception still for TypeErrors, such as if a sequence was passed into the function.  
Correct: Should catch specific exceptions like `ValueError` for conversion failures, allowing other exceptions to surface as bugs.

## Key Takeaways
- Dictionary `in` operator checks keys by default (not values) - this is O(1) fast and the most common use case
- List `.extend()` modifies in-place and returns `None` - use `+` for concatenation when you need the result assigned
- Recursive functions must have a return statement to pass results back up the call chain - forgetting this causes `None` returns

## Functions/Methods Practiced
- **dict**: items(), values(), keys()
- **list**: extend(), append() (and understanding + concatenation)
- **built-in**: isinstance(), set(), list()
- **itertools**: groupby()
- **Keywords**: global, nonlocal, yield, assert

## Practice Problem Results
- **Easy (flatten function)**: ✓ solved independently
- **Medium (invert_dict)**: ✓ solved with hints
- **Hard (merge_dicts)**: ✓ solved with hints

## To Review (Optional)
- `defaultdict` from collections module - more elegant way to handle "key doesn't exist yet" pattern
- Best practices for when to use recursion vs iteration

---

**Date completed**: October 24, 2025  
**Time spent on practice**: 90 minutes  
**Overall confidence**: High