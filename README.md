# CASE-STUDY-1

## Group Name: Sitta

## Group Members:
1. Ikram Solehin bin Mohd Rizal 2014303
2. Anwar bin Muzamir 1928317
3. Azrul Zharfan bin Shuhaime 1911399
4. Muhammad Irfan Danial bin Baharim 1927331
## Assigned Tasks for Group Members:

1. CSRF                                                                                            : **Ikram**

2. Secured Cookies                                                                                 : **Irfan**

3. CSP                                                                                             : **Anwar**

4. Information Disclosure                                                                          : **Azrul**

## Table of Contents
1. [Introduction](#introduction)

2. [Identify the Vulnerabilities](#para1)
   1. [CSRF](#para1c)
   2. [Secured Cookies](#para1d)
   3. [CSP](#para1e)
   4. [Information Disclosure](#para1j)

3. [Evaluate the Vulnerabilities](#para2)
   1. [CSRF](#para2c)
   2. [Secured Cookies](#para2d)
   3. [CSP](#para2e)
   4. [Information Disclosure](#para2j)

4. [Prevent the Vulnerabilities](#para3)
   1. [CSRF](#para3c)
   2. [Secured Cookies](#para3d)
   3. [CSP](#para3e)
   4. [Information Disclosure](#para3j)

5. [References](#references)

## Introduction<a name="introduction"></a>
Group Sitta will explore any web application security vulnerabilities that exist in the TikTok website. Tool that is used to perform the security vulnerabilities assessment will be OWASP ZAP which is an open-source web application security scanner which can scans through your web application to identity any security vulnerabilities as possible. An automated scan and manual scan using the OWASP ZAP on TikTok website (https://www.tiktok.com/) and as much as 24 alerts have been detected by the program. Below is the screenshot of the alerts from the scan conducted on TikTok website: 

![Tiktok Alert](https://user-images.githubusercontent.com/129409403/236791808-f51d64e3-0024-4aa3-a16e-9726f7b03510.PNG)

The topic for the vulnerabilities that will be cover is the description of the identified vulnerabilities which consist of description, risk level, confidence level, parameter, evidence and solution. After that, Common Weakness Enumeration (CWE) information that can be related with the vulnerabilities will be list such as CWE ID and CWE description.

## Identify the Vulnerabilities<a name="para1"></a>

### CSRF<a name="para1c"></a>
The vulnerabilities that is found using Automated Scan for (https://www.tiktok.com/) is shown in line of code below:
```
<form class="search-input tiktok-dhqzc6-FormElement ev30f210" action="/search">
```

### Secured Cookies<a name="para1d"></a>
The vulnerabilities found using Automated Scan for Cookie Without Secure Flag( https://www.tiktok.com) shown in line of code below:
```
Set-Cookie: ttwid=1%7CnkDwKYJY_0J8qu0z7yEbYXtLvf11G40zNLQWPTssdbI%7C1683561735%7C104678a03c654a876a9cef2d197d37779978f0c0675e715865c6870408b163ad; Path=/; Expires=Wed, 08 May 2024 16:02:15 GMT; HttpOnly 
```

The vulnerabilities found using Automated Scan for Cookie With SameSite Attribute None(https://www.tiktok.com/community-guidelines) shown in line of code below:
``` 
Set-Cookie: ttwid=1%7C8E8c1sgOCFN9umi9rrzP5cD3w983ohUuG5Gg1p2pZLg%7C1683561735%7C68178a16e8f90a6098459bdaa06d31e97e3cf8b46553bcdd5825f9969d3c19ef; Domain=.tiktok.com; Path=/; 
```

The vulnerabilities found using Automated Scan for Cookie Without SameSite Attribute(https://www.tiktok.com/discover) shown in line of code below:
``` 
Set-Cookie: tt_chain_token=BWi3Nq+ysr0TK62uSs3QQA==; path=/; expires=Mon, 08 May 2023 22:02:15 GMT; domain=.tiktok.com; secure; httponly
```

### CSP<a name="para1e"></a>
The vulnerabilities that is found using Automated Scan for (https://www.tiktok.com/) is shown in line of code below:  
```
script-src 'unsafe-eval' sf16-website-login.neutral.ttwstatic.com s20.tiktokcdn.com *.tiktokcdn-us.com;frame-src *.tiktok.com accounts.google.com www.google.com recaptcha.google.com www.facebook.com *.kakao.com lf16-web.tiktokcdn.com assets.braintreegateway.com appleid.apple.com access.line.me api.twitter.com h.online-metrix.net bytedance:;worker-src https: blob:
```  
The vulnerabilities that is found using Manual Explore for (https://www.tiktok.com/) is shown in line of code below:  
```
script-src 'unsafe-eval' sf16-website-login.neutral.ttwstatic.com s20.tiktokcdn.com *.tiktokcdn-us.com;frame-src *.tiktok.com accounts.google.com www.google.com recaptcha.google.com www.facebook.com *.kakao.com lf16-web.tiktokcdn.com assets.braintreegateway.com appleid.apple.com access.line.me api.twitter.com h.online-metrix.net bytedance:;worker-src https: blob:
```  
### Information Disclosure<a name="para1j"></a>
The vulnerabilities that is found using Automated Scan for Information Disclosure - Debug Error Messages in (https://www.tiktok.com/about) is shown in line of code below:  
```
The response appeared to contain common error messages returned by platforms such as ASP.NET, and Web-servers such as IIS and Apache. You can configure the list of common debug messages.
```  
The vulnerabilities that is found using Automated Scan for Information Disclosure - Sensitive Information in URL in (https://www.tiktok.com/) is shown in line of code below:  
```
The URL contains potentially sensitive information. The following string was found via the pattern: token msToken
https://www.tiktok.com/api/policy/notice/?aid=1988&app_language=en&app_name=tiktok_web&browser_language=en-US&browser_name=Mozilla&browser_online=true&browser_platform=Win32&browser_version=5.0%20%28Windows%29&channel=tiktok_web&cookie_enabled=true&device_id=7230814007669245441&device_platform=web_pc&focus_state=true&from_page=fyp&history_len=1&is_fullscreen=false&is_page_visible=true&locale=en&os=windows&priority_region=&referer=&region=MY&screen_height=768&screen_width=1366&tz_name=Asia%2FKuala_Lumpur&webcast_language=en&x-schedule-vdc=my&msToken=&X-Bogus=DFSzswSOL1kANnN7tCHZ6n2J46Qb&_signature=_02B4Z6wo00001ZOf38wAAIDCfCgYNwpxROGTj.tAAAC.43 HTTP/1.1
```  
The vulnerabilities that is found using Automated Scan for Information Disclosure - Suspicious Comments in (https://lf-rc1.yhgfb-static.com/obj/rc-client-security-sg/secsdk-captcha/@latest/captcha.js) is shown in line of code below:  
```
The following pattern was used: \bUSER\b and was detected in the element starting with: "<script id="__UNIVERSAL_DATA_FOR_REHYDRATION__" type="application/json">{"__DEFAULT_SCOPE__":{"webapp.app-context":{"language":"", see evidence field for the suspicious comment/snippet.
```  

## Evaluate the Vulnerabilities<a name="para2"></a>

### CSRF<a name="para2c"></a>

The rating for the vulnerability using the Automated Scan is shown in the table below:
| RISK | Total URLs | CWE ID | Additional Info |
|---|---|---|---|
| Medium | 6 | 352 | Absence of Anti-CSRF Tokens |

### Secured Cookies<a name="para2d"></a>
The rating for the vulnerability using the Automated Scan is shown in the table below:
| Cookies Type |Total URLs| Risk | CWE ID | Parameter | Additional Info |
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

### Information Disclosure<a name="para2j"></a>
The rating for the vulnerability using the Automated Scan is shown in the table below:
| Cookies Type |Total URLs| Risk | CWE ID | Parameter | Additional Info |
|---|---|---|---|---|---|
| Information Disclosure - Debug Error Messages | 4 | Low | 200 | Internal Server Error | Exposure of Sensitive Information to an Unauthorized Actor|
|  |  |  |  |  |  |
| Information Disclosure - Sensitive Information in URL | 290 | Informational | 200 | Email | Exposure of Sensitive Information to an Unauthorized Actor |
|  |  |  |  |  |  |
| Information Disclosure - Suspicious Comments | 112 | Informational | 200 | User | Exposure of Sensitive Information to an Unauthorized Actor |
|  |  |  |  |  |  |

## Prevent the Vulnerabilities<a name="para3"></a>

### CSRF<a name="para3c"></a>
Use a vetted library or framework that does not allow this weakness to occur or provides constructs that make this weakness easier to avoid. For example, use anti-CSRF packages such as the OWASP CSRFGuard.

OWASP CSRFGuard is a Java-based library that provides developers with configurable filters to help prevent CSRF attacks. The library includes a filter that automatically generates and validates CSRF tokens, making it easier for developers to implement anti-CSRF measures in their applications. By using a well-vetted and tested library like OWASP CSRFGuard, developers can reduce the likelihood of introducing vulnerabilities into their applications and improve the overall security posture of their software.

### Secured Cookies<a name="para3d"></a>
In order to prevent the vulnerability being expose with threat are to make sure that the secure flag is set for cookies. Whenever a cookie contains sensitive information or is a session token, then it should always be passed using an encrypted channel. Besides,the SameSite attribute must be set to either 'lax' or ideally 'strict' for all cookies.

### CSP<a name="para3e"></a>
To prevent the vulnerability to become a threat is to make sure that your web server, application server, load balancer, etc. is properly configured to set the Content-Security-Policy header.  

### Information Disclosure<a name="para3j"></a>
Mitigating the vulnerabilities regarding information disclosure several action is required such as disable debugging messages before pushing to production, do not pass sensitive information in URIs and remove all comments that return information that may help an attacker and fix any underlying problems they refer to.

## References<a name="references"></a>

1. [OWASP ZAP- Alert Details](https://www.zaproxy.org/docs/alerts/)
2. [The MITRE Corporation: CWE-ID 352](https://cwe.mitre.org/data/definitions/352.html)
3. [The MITRE Corporation: CWE-ID 200](https://cwe.mitre.org/data/definitions/200.html)
4. [The MITRE Corporation: CWE-ID 693](https://cwe.mitre.org/data/definitions/693.html)
