Here's an improved version of your notes with refined wording while keeping the headers similar:

---

# Intro to Web Security

## Same-origin Policy

- Websites in a browser are isolated from each other for security reasons.
    - For example, scripts from evil.com cannot access resources from bank.com.
- Pages from the same site are not isolated since they need to interact and share information.

### How do we determine if origins are the same?

- Origin = protocol + hostname + port 
    - All three components must match for the origins to be considered the same.
- Example URL: `http://www.bank.com/page.html`
    - Protocol: `http`
    - Hostname: `www.bank.com`
    - Default port: `80`
#### Does "www" matter?

Yes, `www.somehost.com` and `somehost.com` are technically different hostnames and can point to different resources.

## Key Security Goals for Websites

- Confidentiality
- Integrity
- Availability
- Privacy

### Examples

#### Risk 1: Preventing malicious sites from accessing local files or programs.
- Visiting a site like awesomevids.com should not result in malware infecting your computer, nor should it be able to read or modify your files.
##### Defenses:
- Javascript is *"sandboxed"*
- Avoid security bugs in browser code
- Privilege separation 
- Automatic updates

#### Risk 2: Malicious websites should not be able to spy or tamper with my informatoin or interactions with other websites (for instance, like a MITM attack)
##### Defenses:

#### Risk 3: We want data stored on a web server to be protected from unauthorized access 
##### Defenses:
- server-side security

## Difference between GET and POST 

- get; requests data from a given source 
    - query string is sent in the URL
- post; gives data to be 'processed' by a given source
    - query tring is sent in the HTTP message body

## Cookies

### Scope

- sent over HTTPs only, which makes them secure
- cookies have an expiration date
    - by default, they last the session length
- cookie cannot be accessed by Javascript. they can only be sent by the browser
    - malicious code therefor cannot access the cookies 

## Common Web Vulnerabilities

- Cross-site request forgery (CSRF)
    - Malicious website forces a victim to execute unwanted actions on another web site which it is already authenticated.
    - Works by using a victims browser, which is trusted by some other website 
    - Usually conducted through social engineering