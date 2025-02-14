# ZAP report

## Automated tests

### Vulnerability

**Medium risk**
- Content Security Policy (CSP) Header Not Set
    * Content Security Policy (CSP) is a security feature that helps prevent attacks like Cross Site Scripting (XSS) and data injection by     defining trusted content sources. Without a CSP header, the application is vulnerable to these attacks, allowing malicious content to be executed or injected, which could lead to data theft, site defacement, or malware distribution.
- Missing Anti-clickjacking Header
    * The response does not protect against 'ClickJacking' attacks. It should include either Content-Security-Policy with 'frame-ancestors' directive or X-Frame-Options.

### Deviation

**Low risk**
- Application Error Disclosure
    * Page contains an error/warning message that may disclose sensitive information like the location of the file that produced the unhandled exception. This information can be used to launch further attacks against the web application. The alert could be a false positive if the error message is found inside a documentation page.
- X-Content-Type-Options Header Missing
    * The Anti-MIME-Sniffing header X-Content-Type-Options was not set to 'nosniff'. This allows older versions of Internet Explorer and Chrome to perform MIME-sniffing on the response body, potentially causing the response body to be interpreted and displayed as a content type other than the declared content type. Current (early 2014) and legacy versions of Firefox will use the declared content type (if one is set), rather than performing MIME-sniffing.


## Manual exploration






**Tämä on lihavoitu teksti**
* Tämä on kursivoitu teksti *

Tämä on `inline`-koodia.

| Otsikko 1 | Otsikko 2 |
|-----------|-----------|
| Tieto 1   | Tieto 2   |
| Tieto 3   | Tieto 4   |
