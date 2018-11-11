# CodePathweek7
# Project 7 - WordPress Pentesting

Time spent: 5 hours spent in total

> Objective: Find, analyze, recreate, and document **five vulnerabilities** affecting an old version of WordPress

## Pentesting Report

Exploit 1. Upload Same Origin Method Execution (SOME)
  - [ ] Summary: 
    - Vulnerability types: Same Origin Method Execution (SOME)
    - Tested in version: 4.2
    - Fixed in version: 4.2.8
  - [ ] GIF Walkthrough: 
  - [ ] Steps to recreate: 
  - [ ] Affected source code:
    - [Link 1](https://core.trac.wordpress.org/browser/tags/version/src/source_file.php)
Exploit 2. Unauthenticated Stored Cross Site-Scripting (XSS)
  - [ ] Summary: 
    - Vulnerability types: Cross Site-Scripting (XSS)
    - Tested in version: 4.2
    - Fixed in version: 4.2.1
  - [ ] GIF Walkthrough: 
  - [ ] Steps to recreate: 
        1. <a title='x onmouseover=alert(unescape(/hello%20world/.source))
style=position:absolute;left:0;top:0;width:5000px;height:5000px
AAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAA
  - [ ] Affected source code:
    - [Link 1](https://core.trac.wordpress.org/browser/tags/version/src/source_file.php)
Exploit 3. Application Denial of Service (DoS)
  - [ ] Summary: 
    - Vulnerability types: 4.2
    - Tested in version: 4.9.4
    - Fixed in version: unpacthed
  - [ ] GIF Walkthrough: 
  - [ ] Steps to recreate: 
  - [ ] Affected source code:
    - [Link 1](https://core.trac.wordpress.org/browser/tags/version/src/source_file.php)
Expoint 4: Authenticated Stored Cross-Site Scripting (XSS) in YouTube URL Embeds
  - [ ] Summary: 
    - Vulnerability types:
    - Tested in version:
    - Fixed in version: 
  - [ ] GIF Walkthrough: 
  - [ ] Steps to recreate: 
        1. Create a new post
        2. In the post body, write this code:
            [embed src='https://youtube.com/embed/12345\x3csvg onload=alert("No Body Is Safe!")\x3e'][/embed]
        3. Save your changes, when you go to the post on the site you will see an embeded link
        4. Click the embeded link and a alert window will pop up with the message “No Body Is Safe!”
  - [ ] Affected source code:
    - [Link 1](https://core.trac.wordpress.org/browser/tags/version/src/source_file.php)
## Assets

List any additional assets, such as scripts or files

## Resources

- [WordPress Source Browser](https://core.trac.wordpress.org/browser/)
- [WordPress Developer Reference](https://developer.wordpress.org/reference/)

GIFs created with [LiceCap](http://www.cockos.com/licecap/).

## Notes

Describe any challenges encountered while doing the work

## License

    Copyright 2018 Oleksandr Bihary

    Licensed under the Apache License, Version 2.0 (the "License");
    you may not use this file except in compliance with the License.
    You may obtain a copy of the License at

        http://www.apache.org/licenses/LICENSE-2.0

    Unless required by applicable law or agreed to in writing, software
    distributed under the License is distributed on an "AS IS" BASIS,
    WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied.
    See the License for the specific language governing permissions and
    limitations under the License.
