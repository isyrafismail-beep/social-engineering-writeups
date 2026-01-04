# ParrotPost Phishing Email Analysis

## Overview
This write-up documents the analysis of a phishing email impersonating ParrotPost. The objective of the lab was to identify how the phishing email attempts to steal user credentials and to analyze the underlying technical mechanisms.

## Phishing Email Analysis
The phishing email used social engineering techniques such as urgency and impersonation to trick users into clicking a malicious link leading to a fake login page.

## Technical Analysis

### HTML and JavaScript Inspection
The phishing page contained obfuscated HTML and JavaScript code designed to hide its true functionality. Upon inspection, the code revealed a credential harvesting mechanism that captured user input from the login form.

### Network Traffic Analysis
Using the browser Developer Tools (Network tab), it was observed that credentials were sent via an HTTP GET request upon clicking the login button.

### Credential Harvesting
- Credential capture endpoint: `/cred-capture.php`
- Captured credentials were written to a file named `creds.txt` on the web server
- The flag obtained from the response confirmed successful credential capture

## Indicators of Compromise (IOCs)
- Malicious phishing domain
- Credential capture endpoint: `/cred-capture.php`
- File used for credential storage: `creds.txt`

## Conclusion
This lab demonstrates how phishing attacks can leverage obfuscated client-side code and backend scripts to steal credentials. Analyzing network traffic and source code is critical for identifying and mitigating phishing threats.
