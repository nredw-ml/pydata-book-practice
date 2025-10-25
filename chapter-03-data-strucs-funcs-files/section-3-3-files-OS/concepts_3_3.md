# Chapter 3, Section 3.3: Files and the Operating System

## Conceptual Questions & Answers

**Q: Why is it important to always specify `encoding="utf-8"` when opening files in Python, even though it works without it? What problem can occur if you don't specify encoding?**  
My answer: It's important to specify the encoding because the default encoding varies from platform to platform, and may yield different results with the same code if not explicitly given.

**Q: What's the difference between opening a file with mode "w" versus mode "x"? When would you choose one over the other?**  
My answer: Opening a file with mode "w" will create a new file but also erase any existing files with the same name, while "x" will attempt to create a new file but fail if it already exists. You would choose to use "w" if you wanted to overwrite existing files, but "x" if it was important to ensure that existing files remained intact.

**Q: What does the `with` statement do when working with files, and why is it recommended over manually calling `open()` and `close()`?**  
My answer: The with statement will automatically close files after exiting the code block for which it is called. It is recommended over manually opening and closing because it prevents accidentally forgetting to close the file, which will cause the file to remain in memory and waste resources once it is no longer needed.

**Q: What's the difference between text mode (default) and binary mode ("rb" or "wb") when opening files? Give an example of when you'd need to use binary mode.**  
My answer: Text mode works at the Unicode character or string level of the data, whereas binary mode works at the individual bytes of data without the encoding. An example of when you'd need to use binary mode might be when working with data that has different encoding but needs to be combined or manipulated.  
Correct: Text mode is for human-readable text files (CSV, JSON, .txt) where Python handles encoding/decoding automatically. Binary mode is for non-text files like images, audio, video, executables (e.g., `open("photo.jpg", "rb")`), or when you need exact byte-level control without any encoding interpretation.

## Key Takeaways
- Always specify `encoding="utf-8"` to ensure consistent cross-platform behavior and avoid mojibake corruption
- The `with` statement guarantees file cleanup even if errors occur, preventing resource leaks
- File modes have important safety distinctions: "w" overwrites, "x" fails safely if file exists

## Functions/Methods Practiced
- **File operations**: open(), read(), readlines(), write(), writelines(), close()
- **File context management**: with statement
- **String methods**: strip(), split(), lower(), replace()
- **List comprehensions**: filtering and transforming file lines

## Practice Problem Results
- **Easy**: ✓ solved with hints (word counter - needed guidance on counting words across all lines)
- **Medium**: ✓ solved independently (text file cleaner - 30 min, solid implementation)
- **Hard**: skipped (section assessed as USEFUL, not CRITICAL - prioritizing time for core pandas/NumPy)

## To Review
- Binary mode use cases - when exactly to use "rb"/"wb" for different file types

---

**Date completed**: October 25, 2025  
**Time spent on practice**: 1 hour 20 minutes  
**Overall confidence**: High