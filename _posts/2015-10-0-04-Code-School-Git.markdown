---
layout: post
title:  "Code School Git"
date:   2014-10-04
categories: Git
---
Code School offers free and paid courses in various developer-centric languages. languages such as Ruby, iOS . It offers one-off courses and groups of courses (Paths) 
If you haven't already heard, ShellShock is the name of a recent vulnerability [CVE-2014-6271][CVE] discovered in [GNU Bash][GNU Bash]. Apple ships Bash v3 in the latest version of their operating system, [OS X Mavericks][OS X].

There are a number of ways to determine if your copy of Bash is vulnerable. The best one I've seen is [bashcheck][bashcheck]. It only checks Bash for the original ShellShock vulnerability but also ones discovered after the initial "fix" was released. Excecuting the `bashcheck` script tests the default Bash installation on the machine. Here's some sample output:

{% highlight bash %}
Testing /opt/local/bin/bash ...
GNU bash, version 4.3.28(1)-release (x86_64-apple-darwin13.4.0)

Variable function parser pre/suffixed [%%, upstream], bugs not explitable
Not vulnerable to CVE-2014-6271 (original shellshock)
Not vulnerable to CVE-2014-7169 (taviso bug)
Not vulnerable to CVE-2014-7186 (redir_stack bug)
Test for CVE-2014-7187 not reliable without address sanitizer
Found non-exploitable CVE-2014-6277 (lcamtuf bug #1)
Found non-exploitable CVE-2014-6278 (lcamtuf bug #2)
{% endhighlight %}

Keen observers may have noticed that the script also outputs the location of the Bash executable. In the case above, it's `/opt/local/bin/bash` as opposed to `/bin/bash`. I use the [MacPorts][MacPorts] version of Bash instead of Apple's include Bash since Apple has a history of included outdated or modified versions of Unix utitlies in their operating system. While Apple has released a [patch][Apple Bash update], it's still a major version way from the latest available version.

Whichever way you go, make sure you apply the patch!

[bashcheck]:          https://github.com/hannob/bashcheck
[CVE]:                http://web.nvd.nist.gov/view/vuln/detail?vulnId=CVE-2014-6271
[GNU Bash]:           https://www.gnu.org/software/bash/
[OS X]:               http://www.apple.com/osx/
[MacPorts]:           http://www.macports.org
[Apple Bash update]:  http://support.apple.com/kb/DL1769
