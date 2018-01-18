# wapiti-3.0.0
 Wapiti 3.0.0 - The Web-Application Vulnerability Scanner 5:32 PM | Post sponsored by FaradaySEC | Multiuser Pentest Environment Lydecker Black  Wapiti allows you to audit the security of your websites or web applications. It performs "black-box" scans (it does not study the source code) of the web application by crawling the webpages of the deployed webapp, looking for scripts and forms where it can inject data.  Once it gets the list of URLs, forms and their inputs, Wapiti acts like a fuzzer, injecting payloads to see if a script is vulnerable
 What's new in Wapiti 3.0.0 ?

Wapiti can detect the following vulnerabilities :

    File disclosure (Local and remote include/require, fopen, readfile...)
    Database Injection (PHP/JSP/ASP SQL Injections and XPath Injections)
    XSS (Cross Site Scripting) injection (reflected and permanent)
    Command Execution detection (eval(), system(), passtru()...)
    CRLF Injection (HTTP Response Splitting, session fixation...)
    XXE (XML External Entity) injection
    Use of know potentially dangerous files (thanks to the Nikto database)
    Weak .htaccess configurations that can be bypassed
    Presence of backup files giving sensitive information (source code disclosure)
    Shellshock (aka Bash bug)

A buster module also allows to brute force directories and files names on the target webserver.

Wapiti supports both GET and POST HTTP methods for attacks.
It also supports multipart forms and can inject payloads in filenames (upload).
Warnings are raised when an anomaly is found (for example 500 errors and timeouts)
Wapiti is able to make the difference beetween permanent and reflected XSS vulnerabilities.


General features :

    Generates vulnerability reports in various formats (HTML, XML, JSON, TXT...)
    Can suspend and resume a scan or an attack (session mechanism using sqlite3 databases)
    Can give you colors in the terminal to highlight vulnerabilities
    Different levels of verbosity
    Fast and easy way to activate/deactivate attack modules
    Adding a payload can be as easy as adding a line to a text file


Browsing features:

    Support HTTP, HTTPS and SOCKS5 proxies
    Authentication via several methods : Basic, Digest, Kerberos or NTLM
    Ability to restrain the scope of the scan (domain, folder, page, url)
    Automatic removal of one are more parameters in URLs
    Multiple safeguards against scan endless-loops (ifor example, limit of values for a parameter)
    Possibility to set the first URLs to explore (even if not in scope)
    Can exclude some URLs of the scan and attacks (eg: logout URL)
    Import of cookies (get them with the wapiti-getcookie tool)
    Can activate / deactivate SSL certificates verification
    Extract URLs from Flash SWF files
    Try to extract URLs from javascript (very basic JS interpreter)
    HTML5 aware (understand recent HTML tags)
    Several options to control the crawler behavior and limits.
    Skipping some parameter names during attack.
    Setting a maximum time for the scan process.
    Adding some custom HTTP headers or setting a custom User-Agent.


Wapiti is a command-line application.
Here is an exemple of output against a vulnerable web application.
You may find some useful informations in the README and the INSTALL files.
Have any questions ? You may find answers in the FAQ. 

Usage

 ██╗    ██╗ █████╗ ██████╗ ██╗████████╗██╗██████╗ 
 ██║    ██║██╔══██╗██╔══██╗██║╚══██╔══╝██║╚════██╗
 ██║ █╗ ██║███████║██████╔╝██║   ██║   ██║ █████╔╝
 ██║███╗██║██╔══██║██╔═══╝ ██║   ██║   ██║ ╚═══██╗
 ╚███╔███╔╝██║  ██║██║     ██║   ██║   ██║██████╔╝
  ╚══╝╚══╝ ╚═╝  ╚═╝╚═╝     ╚═╝   ╚═╝   ╚═╝╚═════╝  
Wapiti-3.0.0 (wapiti.sourceforge.net)
usage: wapiti [-h] [-u URL] [--scope {page,folder,domain,url}]
              [-m MODULES_LIST] [--list-modules] [-l LEVEL] [-p PROXY_URL]
              [-a CREDENTIALS] [--auth-type {basic,digest,kerberos,ntlm}]
              [-c COOKIE_FILE] [--skip-crawl] [--resume-crawl]
              [--flush-attacks] [--flush-session] [-s URL] [-x URL]
              [-r PARAMETER] [--skip PARAMETER] [-d DEPTH]
              [--max-links-per-page MAX] [--max-files-per-dir MAX]
              [--max-scan-time MINUTES] [--max-parameters MAX] [-S FORCE]
              [-t SECONDS] [-H HEADER] [-A AGENT] [--verify-ssl {0,1}]
              [--color] [-v LEVEL] [-f FORMAT] [-o OUPUT_PATH]
              [--no-bugreport] [--version]
wapiti: error: one of the arguments -u/--url --list-modules is required


Shortest way (with default options) to launch a Wapiti scan :

wapiti -u http://target/


Every option is detailed in the wapiti(1) manpage.
Wapiti also comes with an utility to fetch cookies from websites called wapiti-getcookie. The corresponding manpage is here.


Download Wapiti 3.0.0
