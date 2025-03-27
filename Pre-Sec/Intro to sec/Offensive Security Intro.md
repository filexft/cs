>"To outsmart a hacker, you need to think like one."

This is the core of "Offensive Security." It involves **breaking into computer systems, exploiting software bugs, and finding loopholes in applications to gain unauthorized access.** The goal is to understand hacker tactics and enhance our system defences.



##  [Gobuster](https://github.com/OJ/gobuster)

brute-force a website to find hidden directories and pages. Gobuster will take a list of potential page or directory names and try accessing a website with each of them; if the page exists, it tells you.

Most companies have an admin portal page, giving their staff access to basic admin controls for day-to-day operations.

Due to human error or negligence, there may be instances when these pages are not made private, allowing attackers to find hidden pages that show or give access to admin controls or sensitive data.

to begin, type the following command into the terminal to find potentially hidden pages on FakeBank's website using Gobuster (a command-line security application).

```bash
gobuster -u http://fakebank.thm -w wordlist.txt dir
```

In the command above, `-u` is used to state the website we're scanning, `-w` takes a list of words to iterate through to find hidden pages.


