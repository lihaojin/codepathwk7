# codepathwk7
# Project 7 - WordPress Pentesting

Time spent: **6** hours spent in total

> Objective: Find, analyze, recreate, and document **five vulnerabilities** affecting an old version of WordPress

## Pentesting Report
1. User Enumeration
  - [ ] Summary: 
    - Vulnerability types:
    - Tested in version: 4.2
    - Fixed in version: 4.4
  - [ ] GIF Walkthrough: <img src='https://raw.githubusercontent.com/lihaojin/codepathwk7/master/Exploit 1 XSS.gif'/>
  - [ ] Steps to recreate: 
  - On log in, type in different username and password combinations.
  - When a valid username is entered with an incorrect password, the log in page will indicate that it is an incorrect    password for given username. 
  
  - [ ] Affected source code:
    
2. Authenticated Shortcode Tags XSS
  - [ ] Summary: 
    - Vulnerability types: XSS
    - Tested in version: 4.2
    - Fixed in version: 4.7.2
  - [ ] GIF Walkthrough: <img src='https://raw.githubusercontent.com/lihaojin/codepathwk7/master/Exploit 2 XSS.gif'/>
  - [ ] Steps to recreate: 
- Paste the following in the comment section and post it as admin.

```
<a href = "XSS" onmouseover=alert(1) rel="nofollow">CLICK ME!</a>
```

- Then hover over the link in the comment.
  - [ ] Affected source code:
    - [Link to Source](https://github.com/WordPress/WordPress/commit/f72b21af23da6b6d54208e5c1d65ececdaa109c8)
    
3. Authenticated Stored Cross-Site Scripting (XSS)
  - [ ] Summary: 
- Vulnerability types: XSS
- Tested in version: 4.2.2
- Fixed in version: 4.2.3
  - [ ] GIF Walkthrough: <img src='https://raw.githubusercontent.com/lihaojin/codepathwk7/master/Exploit 3 XSS.gif'/>
  - [ ] Steps to recreate: 
  - First log in to an account where you can make posts.
  - Create or edit a post and paste the following code into the html editor.
  ```
  <a href="[caption code=">]</a><a title=" <Event-attribute-with-JS-code-here>  ">link</a>
  ```
  - [ ] Affected source code:
    - [CVE-2015-5622](https://cve.mitre.org/cgi-bin/cvename.cgi?name=CVE-2015-5622)
    - [CVE-2015-5623](https://cve.mitre.org/cgi-bin/cvename.cgi?name=CVE-2015-5623)


## Assets

List any additional assets, such as scripts or files

## Resources

- [WordPress Source Browser](https://core.trac.wordpress.org/browser/)
- [WordPress Developer Reference](https://developer.wordpress.org/reference/)

GIFs created with [LiceCap](http://www.cockos.com/licecap/).

## Notes

Recreating the exploits.

## License

    Copyright [2018] [Haojin Li]

    Licensed under the Apache License, Version 2.0 (the "License");
    you may not use this file except in compliance with the License.
    You may obtain a copy of the License at

        http://www.apache.org/licenses/LICENSE-2.0

    Unless required by applicable law or agreed to in writing, software
    distributed under the License is distributed on an "AS IS" BASIS,
    WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied.
    See the License for the specific language governing permissions and
    limitations under the License.
