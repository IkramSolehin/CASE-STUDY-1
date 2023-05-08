# CASE-STUDY-1

## Group Name:

## Group Members:
1. Ikram Solehin bin Mohd Rizal 2014303
2. Anwar bin Muzamir 1928317
3. Azrul Zharfan bin Shuhaime 1911399
## Assigned Tasks for Group Members:

1. CSRF                                                                                            : **Ikram**

2. Secured Cookies                                                                                 : **Irfan**

3. CSP                                                                                             : **Anwar**

4. Information Disclosure                                                                         : **Azrul**

## Table of Contents
1. [Introduction](#introduction)

2. [Identify the Vulnerabilities](#para1)
   1. (#para1a)
   2. (#para1b)
   3. [CSRF](#para1c)
   4. [Secured Cookies](#para1d)
   5. [CSP](#para1e)
   6. [JS Library](#para1f)
   7. [HTTPS implementation (TLS/SSL)](#para1g)
   8. [Cookie Poisoning](#para1h)
   9. [Potential XSS](#para1i)
   10. [Information Disclosure](#para1j)

3. [Evaluate the Vulnerabilities](#para2)
   1. [Server OS and Server-Side Scripting used (Windows or Linux, PHP or ASP.net or JavaScript, etc.](#para2a)
   2. [Hash Disclosure](#para2b)
   3. [CSRF](#para2c)
   4. [Secured Cookies](#para2d)
   5. [CSP](#para2e)
   6. [JS Library](#para2f)
   7. [HTTPS implementation (TLS/SSL)](#para2g)
   8. [Cookie Poisoning](#para2h)
   9. [Potential XSS](#para2i)
   10. [Information Disclosure](#para2j)

4. [Prevent the Vulnerabilities](#para3)
   1. [Server OS and Server-Side Scripting used (Windows or Linux, PHP or ASP.net or JavaScript, etc.](#para3a)
   2. [Hash Disclosure](#para3b)
   3. [CSRF](#para3c)
   4. [Secured Cookies](#para3d)
   5. [CSP](#para3e)
   6. [JS Library](#para3f)
   7. [HTTPS implementation (TLS/SSL)](#para3)
   8. [Cookie Poisoning](#para3h)
   9. [Potential XSS](#para3i)
   10. [Information Disclosure](#para3j)

## Introduction<a name="introduction"></a>
Group Sitta will explore any web application security vulnerabilities that exist in the TikTok website. Tool that is used to perform the security vulnerabilities assessment will be OWASP ZAP which is an open-source web application security scanner which can scans through your web application to identity any security vulnerabilities as possible. An automated scan and manual scan using the OWASP ZAP on TikTok website (https://www.tiktok.com/) and as much as 24 alerts have been detected by the program. Below is the screenshot of the alerts from the scan conducted on TikTok website: 

![Tiktok Alert](https://user-images.githubusercontent.com/129409403/236791808-f51d64e3-0024-4aa3-a16e-9726f7b03510.PNG)

The topic for the vulnerabilities that will be cover is the description of the identified vulnerabilities which consist of description, risk level, confidence level, parameter, evidence and solution. After that, Common Weakness Enumeration (CWE) information that can be related with the vulnerabilities will be list such as CWE ID and CWE description. Lastly, list of Common Vulnerabilities and Exposure (CVE) that is closely related to the vulnerabilities will be list for understanding the threat that comes with the vulnerabilities.

## Identify the Vulnerabilities<a name="para1"></a>

### Server OS and Server-Side Scripting used (Windows or Linux, PHP or ASP.net or JavaScript, etc.<a name="para1a"></a>
### Hash Disclosure<a name="para1b"></a>
### CSRF<a name="para1c"></a>
### Secured Cookies<a name="para1d"></a>
### CSP<a name="para1e"></a>
The vulnerabilities that is found using Automated Scan for (https://www.tiktok.com/) is shown in line of code below:  
```
script-src 'unsafe-eval' sf16-website-login.neutral.ttwstatic.com s20.tiktokcdn.com *.tiktokcdn-us.com;frame-src *.tiktok.com accounts.google.com www.google.com recaptcha.google.com www.facebook.com *.kakao.com lf16-web.tiktokcdn.com assets.braintreegateway.com appleid.apple.com access.line.me api.twitter.com h.online-metrix.net bytedance:;worker-src https: blob:
```  
The vulnerabilities that is found using Manual Explore for (https://www.tiktok.com/) is shown in line of code below:  
```
script-src 'unsafe-eval' sf16-website-login.neutral.ttwstatic.com s20.tiktokcdn.com *.tiktokcdn-us.com;frame-src *.tiktok.com accounts.google.com www.google.com recaptcha.google.com www.facebook.com *.kakao.com lf16-web.tiktokcdn.com assets.braintreegateway.com appleid.apple.com access.line.me api.twitter.com h.online-metrix.net bytedance:;worker-src https: blob:
```  
### JS Library<a name="para1f"></a>
### HTTPS implementation (TLS/SSL)<a name="para1g"></a>
### Cookie Poisoning<a name="para1h"></a>
### Potential XSS<a name="para1i"></a>
### Information Disclosure<a name="para1j"></a>
The vulnerabilities that is found using Automated Scan for Information Disclosure - Debug Error Messages is shown in line of code below:  
```
-
```  
The vulnerabilities that is found using Automated Scan for Information Disclosure - Sensitive Information in URL is shown in line of code below:  
```
-
```  
The vulnerabilities that is found using Automated Scan for Information Disclosure - Suspicious Comments is shown in line of code below:  
```
-
```  

## Evaluate the Vulnerabilities<a name="para2"></a>

### Server OS and Server-Side Scripting used (Windows or Linux, PHP or ASP.net or JavaScript, etc.<a name="para2a"></a>
### Hash Disclosure<a name="para2b"></a>
### CSRF<a name="para2c"></a>
### Secured Cookies<a name="para2d"></a>
The rating for the vulnerability using the Automated Scan is shown in the table below:
| Cookies Type |Total Risk| Risk | CWE ID | Parameter | Additional Info |
|---|---|---|---|---|---|
|Cookie Without Secure Flag| 7 | Low | 614 | ttwid | Improper Restriction of Names for Files and Other Resources|
|  |  |  |  |  |  |
| Cookie With SameSite Attribute None | 5 | Low | 1275 | ttwid | Sensitive Cookie with Improper SameSite Attribute |
|  |  |  |  |  |  |
| Cookie without SameSite Attribute | 11 | Low | 1275 | tt_chain_token | Sensitive Cookie with Improper SameSite Attribute |
|  |  |  |  |  |  |


### CSP<a name="para2e"></a>
The rating for the vulnerability using the Automated Scan is shown in the table below:  
| RISK | CWE ID | Parameter | Additional Info |
|---|---|---|---|
|Medium|693|Content-Security-Policy|The frame-ancestors and form-action directives, are not defined, or are overly broadly defined.|  

The rating for the vulnerability using Manual Explore is shown in the table below:  
| RISK | CWE ID | Parameter | Additional Info |
| --- | --- | --- | --- |
|Medium|693|Content-Security-Policy|The frame-ancestors and form-action directives, are are among the directives that do not fallback to default-src, missing/excluding them is the same as allowing anything.|
### JS Library<a name="para2f"></a>
### HTTPS implementation (TLS/SSL)<a name="para2g"></a>
### Cookie Poisoning<a name="para2h"></a>
### Potential XSS<a name="para2i"></a>
### Information Disclosure<a name="para2j"></a>
The rating for the vulnerability using the Automated Scan is shown in the table below:
| Cookies Type |Total Risk| Risk | CWE ID | Parameter | Additional Info |
|---|---|---|---|---|---|
| Information Disclosure - Debug Error Messages | 2 | Low | 200 | - | Exposure of Sensitive Information to an Unauthorized Actor|
|  |  |  |  |  |  |
| Information Disclosure - Sensitive Information in URL | 1 | International | 200 | Email | Exposure of Sensitive Information to an Unauthorized Actor |
|  |  |  |  |  |  |
| Information Disclosure - Suspicious Comments | 19 | International | 200 | - | Exposure of Sensitive Information to an Unauthorized Actor |
|  |  |  |  |  |  |

## Prevent the Vulnerabilities<a name="para3"></a>

### Server OS and Server-Side Scripting used (Windows or Linux, PHP or ASP.net or JavaScript, etc.<a name="para3a"></a>
### Hash Disclosure<a name="para3b"></a>
### CSRF<a name="para3c"></a>
### Secured Cookies<a name="para3d"></a>
In order to prevent the vulnerability being expose with threat are to make sure that the secure flag is set for cookies. Whenever a cookie contains sensitive information or is a session token, then it should always be passed using an encrypted channel. Besides,the SameSite attribute must be set to either 'lax' or ideally 'strict' for all cookies.


### CSP<a name="para3e"></a>
To prevent the vulnerability to become a threat is to make sure that your web server, application server, load balancer, etc. is properly configured to set the Content-Security-Policy header.  

### JS Library<a name="para3f"></a>
### HTTPS implementation (TLS/SSL)<a name="para3g"></a>
### Cookie Poisoning<a name="para3h"></a>
### Potential XSS<a name="para3i"></a>
### Information Disclosure<a name="para3j"></a>
Mitigating the vulnerabilities regarding information disclosure several action is required such as disable debugging messages before pushing to production, do not pass sensitive information in URIs and remove all comments that return information that may help an attacker and fix any underlying problems they refer to.
