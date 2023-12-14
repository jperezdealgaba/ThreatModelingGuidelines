# Programming Languages

## Common vulnerabilities

- Memory errors. **Vulnerability:** Buffer Overflow, Use-After-Free (UAF), Buffer Over Read
- Dependencies. **Vulnerability:** Library hijacking, Library Sideloading, Supply Chain attack


## Questions

- Is it a managed programming language?
	- Does it use a JIT (Just-in-time) compiler?
	- Can it run unmanaged code?
		- Can the user manage the memory?
	- Does it have W^X protection?
	 - Does it perform code isolation?
- Is it an unmanaged programming language?
	- How is memory handled?
- Can it achieve type-safety? How is it achieved?
- Are libraries statically or dynamically linked?
- Can the programming language use compilation flags?
	- Which flags are used?
	- Are there security-related flags?
- Does it perform type checking at the time of compilation?
- How are dependencies implemented into the code?

## Resources
- W^X: https://www.wikiwand.com/en/W%5EX
- Type Checking: https://www.geeksforgeeks.org/type-checking-in-compiler-design/
