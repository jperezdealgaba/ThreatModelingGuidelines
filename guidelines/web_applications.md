# Web applications

## Common vulnerabilities

- Input validation. **Vulnerability:** Command injection, SQL Injection, Cross Site Scripting (XSS)
- Upload validation. **Vulnerability:** Local File Inclusion (LFI), Remote File Inclusion (RFI) 
- Session management **Vulnerability:** Man in the middle (MITM). 


## Questions

- Can the user input data?
  - Is the input validated? Is it validated also server side?
- Can the user upload data?
	- How is the data uploaded? How is validation done?
- Can users authenticate?
	- How are the users authenticated?
- Which protocols does the website use?
	- Are you using HTTP? HTTPS?

## Resources
- Input validation: https://cheatsheetseries.owasp.org/cheatsheets/Input_Validation_Cheat_Sheet.html
- Man in the middle: https://www.imperva.com/learn/application-security/man-in-the-middle-attack-mitm/#:~:text=A%20man%20in%20the%20middle,exchange%20of%20information%20is%20underway.
