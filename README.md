# XSS-LABS
CROSS_SITE_SCRIPTING
XSS (Cross-Site Scripting) Practice & Findings

*Status:* Lab / authorized practice only — all testing performed in controlled environments (PortSwigger labs, OWASP Juice Shop, CTFs).

---

## Summary
This folder documents hands-on practice with *Cross-Site Scripting (XSS). I completed all **Apprentice* and *Practitioner* XSS labs on PortSwigger Web Security Academy and applied the same techniques in OWASP Juice Shop. In Juice Shop I identified XSS vectors in review, feedback, address-saving, and customer-chat features. All work is for learning, documentation, and remediation guidance.

---

## What I practiced
- Reflected XSS — identifying inputs reflected in responses and URL parameters.  
- Stored XSS — finding persistent inputs saved to the app and rendered later (reviews, feedback).  
- DOM XSS — client-side injection via unsafe DOM APIs.  
- Payload crafting and iterative bypass attempts (event handlers, attribute contexts, encoding).  
- Verification of impact and safe proof capture (alerts / DOM changes) in lab contexts.

---

## Tools & environment
- PortSwigger Web Security Academy (Apprentice + Practitioner tracks)  
- OWASP Juice Shop (local Docker)  
- Burp Suite Community (Proxy, Repeater)  
- Firefox Developer Tools (Inspector / Console)  
- Kali Linux (VM) for lab tooling

---

## Artifacts (add these files/screenshots to the folder)
- xss-apprentice-proof.png — PortSwigger apprentice lab success screenshot  
- xss-practitioner-proof.png — PortSwigger practitioner lab success screenshot  
- juiceshop-review-xss.png — example stored XSS in product review (sanitized)  
- juiceshop-chat-xss.png — XSS in customer chat (sanitized)  
- dayx-notes.md — short notes: payloads tried (non-actionable), vectors, and remediation

---

## High-level remediation (actionable for developers)
Do *not* publish exploit strings here. Use these safe, general fixes:
- *Output encode* all untrusted data according to context (HTML body, attribute, JS, URL).  
- *Sanitize* and validate inputs server-side (whitelist where possible).  
- *Avoid* insecure DOM APIs (e.g., innerHTML) with untrusted data; use safe DOM methods.  
- *Content Security Policy (CSP)* — implement a strong CSP to reduce impact of injected scripts.  
- *HttpOnly / Secure cookies* to limit JavaScript access to session cookies.  
- *Context-aware escaping* in templates and frameworks (use built-in escaping functions).  
- *Logging & monitoring* — detect anomalous input patterns and alert.

---

## Next steps
- Move from detection to hardened reporting: produce a sanitized write-up per finding with recommended code fixes.  
- Practice end-to-end: discovery → PoC (lab-safe) → remediation suggestion → verifying the fix.  
- Start combining XSS with business logic review (sensitive flows, privilege levels).

---

> *Note:* All testing and screenshots are from authorized lab environments only. Never test these techniques on live systems without written permission.
