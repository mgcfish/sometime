#SOMEtime

SOMEtime is a passive plugin for the security scanner BurpSuite which will monitor HTTP Request and Responses to determine if a webpage is vulnerable to Same Origin Method Execution.

For more details on Same Origin Method Execution see [Ben Hayak's talk](https://www.youtube.com/watch?v=UfYfID_r7-U) or our post on [LinkedIn](https://security.linkedin.com/posts/2016/finding-same-origin-method-execution-vulnerabilities)

##How To Use - Burp Pro Passive Scanner Plugin

1. Clone the repository
2. Build the code with Maven
```
$ mvn compile && mvn package
```
3. Load Burp Suite Professional
4. From the _Extender_ tab in Burp Suite,  add `sometime-0.0.1-SNAPSHOT-jar-with-dependencies.jar` as a standard Java-based Burp Extension
5. Enable [Burp Scanner Passive Scanning](http://portswigger.net/burp/help/scanner_scanmodes.html)
6. Browse your target web application. All requests and responses will be tested for Same Origin Method Execution

##Example
There is a directory included in this repository containing proof-of-concept code which showcases the vulnerability. To see the vulnerability, first add 'attacker.com' and 'victim.com' to point to your webserver in '/etc/hosts'. Then, navigate to 'main.html' where the exploit should run. If all works correctly, then there should be an alert pop-up on victim.com, displaying Javascript execution.
