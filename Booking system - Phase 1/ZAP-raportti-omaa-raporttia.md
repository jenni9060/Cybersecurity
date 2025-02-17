# ZAP report - Own raport from tests


### Vulnerability

**High risk**
- Path Traversal
    * The Path Traversal attack technique allows an attacker access to files, directories, and commands that potentially reside outside the web document root directory. An attacker may manipulate a URL in such a way that the web site will execute or reveal the contents of arbitrary files anywhere on the web server. Any device that exposes an HTTP-based interface is potentially vulnerable to Path Traversal.


- SQL Injection
    * SQL injection may be possible. The parameter value being modified was NOT stripped from the HTML output for the purposes of the comparison. Data was returned for the original parameter. The vulnerability was detected by successfully restricting the data originally returned, by manipulating the parameter.

   

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




### Vulnerability

**High risk**
- In database, passwords are not encrypted which is high risk vulnerability





