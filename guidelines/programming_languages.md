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

## Security considerations

- **W^X protection**: If an attacker has arbitrary memory writing capabilities in the process and can defeat ASLR to locate the buffers used by the JIT compiler, then it's game over. Even if there were W^X protections, there is a legitimate need for the JIT compilers to turn a dynamically written buffer into executable code at run time, it's just a matter of time. For memory fragmentation and optimization concerns, it's highly likely that the JIT compiler uses a continuous memory region for JIT methods. W^X can be applied at a page granularity level, so it's not even practical to do it. While I have no specific knowledge about .NET implementation, it's highly likely that other memory areas not related to the JIT compiler (e.g. thread stacks) have NX already. A JIT compiler is a particular piece software where the W^X principle cannot be applied in a security meaningful way. As for the user security, there are controls to prevent the attacker from having memory write primitives in the runtime and there should be ASLR.
- **Sandboxing**: User space sandboxing is highly discouraged. Modern software relies on the operating system and process-level isolation. It has always been difficult to get it right, has lead to multiple security bugs, and the Spectre family of attacks has exacerbated the problem. Java is moving away from this, for the good. Defense in depth is a desirable principle but it has to be balanced with simplicity: on some occasions, adding layers on top of layers provide a false sense of security and expands the surface for security holes.
- **Library linking**: The environment where an application is compiled is likely not the same as the environment where the application is run. This means that there could be different (but compatible) versions of a library, and it should be handled seamlessly. Tightening a library to a specific build defeats the whole purpose of dynamic linking. This type of features typically rely on a well-known search path (for relative paths) and file system permissions.

## Resources
- W^X: https://www.wikiwand.com/en/W%5EX
- Type Checking: https://www.geeksforgeeks.org/type-checking-in-compiler-design/
