# CSRF Mitigation

## 1. Mitigation

The primary mitigation for Cross-Site Request Forgery (CSRF) is an unpredictable anti-CSRF token.

The token should be:

- Unique
- Unpredictable
- Associated with the user's session
- Validated on every state-changing request

---

## 2. Anti-CSRF Token

A protected state-changing request should contain a valid CSRF token.

Example:

```text
POST /change-password

The request should contain the appropriate anti-CSRF token.

3. Token Validation

The server should verify that the submitted token matches the token associated with the authenticated user's session.

If the token is missing or invalid, the server should reject the request.

4. SameSite Cookies

Cookies can use the SameSite attribute to reduce cross-site request risks.

Example:

SameSite=Lax

or, where appropriate:

SameSite=Strict
5. Origin and Referer Validation

For sensitive state-changing operations, the server can also validate the Origin or Referer headers where appropriate.

This provides an additional layer of protection against unauthorized cross-site requests.

6. Re-authentication

Sensitive actions such as password changes can require the user to authenticate again before the operation is completed.

7. Validation

After implementing CSRF protection, a request without a valid anti-CSRF token should be rejected by the application.

This prevents unauthorized cross-site requests from performing protected state-changing actions.

8. Conclusion

CSRF protection should combine server-side token validation with appropriate cookie and request-origin controls to protect authenticated state-changing operations.


**File path:**

Mitigation-Notes/CSRF-Mitigation.md