# Cross-Site Scripting (XSS) Attack Scenario

## 1. Vulnerability

Cross-Site Scripting (XSS) is a web application vulnerability in which attacker-controlled script content is executed in a user's browser.

XSS occurs when an application accepts untrusted input and displays it without proper output encoding or validation.

---

## 2. Target

**Application:** DVWA (Damn Vulnerable Web Application)

**Security Level:** Low

**Modules Tested:**
- Reflected XSS
- Stored XSS

---

## 3. Reflected XSS Attack

Reflected XSS occurs when malicious input is immediately reflected by the web application in its response.

### Payload Used

```html
<script>alert('XSS')</script>

The payload was entered into the Reflected XSS input field in DVWA.

4. Observed Result

After submitting the payload, a JavaScript alert box was displayed in the browser.

This demonstrated that the application reflected the user-controlled input without proper output encoding, allowing the browser to interpret the input as executable JavaScript.

5. Stored XSS Attack

Stored XSS occurs when malicious input is stored by the application and executed when the affected content is viewed.

Payload Used
<script>alert('XSS')</script>

The payload was submitted through the Stored XSS functionality of DVWA.

6. Observed Result

The submitted JavaScript was stored by the application.

When the affected page or stored content was loaded again, the JavaScript alert was executed in the browser.

This demonstrated the behavior of Stored XSS.

7. Impact

XSS may allow attacker-controlled JavaScript to execute in a victim's browser.

Depending on the application and browser context, XSS may affect:

Web page content
User actions
Application sessions
Sensitive information accessible to client-side scripts
User interaction with the application
8. Evidence

Screenshots of the XSS testing are included in the repository.

The evidence includes:

Reflected XSS payload and result
Stored XSS payload and result

Screenshots are stored in:

Screenshots/XSS/
9. Mitigation

XSS can be mitigated using multiple security controls:

Context-aware output encoding
Input validation
Content Security Policy (CSP)
Secure cookie attributes
Proper handling of untrusted user input

The primary defense is to encode untrusted output according to the context in which it is displayed.

10. Content Security Policy

Content Security Policy provides an additional layer of protection against XSS.

Example Apache configuration:

Header always set Content-Security-Policy "default-src 'self'"

This restricts the sources from which the browser can load content.

11. Secure Cookies

Where applicable, sensitive cookies should use appropriate security attributes:

HttpOnly
Secure
SameSite

The HttpOnly attribute prevents client-side JavaScript from directly accessing the cookie.

12. Validation

After implementing appropriate output encoding and security controls, untrusted input should be treated as data rather than executable JavaScript.

The same XSS payload should therefore no longer execute as JavaScript.

13. Conclusion

The XSS testing demonstrated that improperly handled user input can be interpreted and executed as JavaScript in a user's browser.

Both Reflected XSS and Stored XSS were tested in the controlled DVWA laboratory environment.

Context-aware output encoding, input validation, Content Security Policy, and appropriate cookie security provide important layers of protection against XSS.

14. Disclaimer

All testing documented in this repository was performed against a controlled DVWA laboratory environment for educational and security testing purposes only.


**File path:**

Attack-Scenarios/XSS.md