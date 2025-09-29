# Gobuster

**What it is:** a command-line tool that brute-forces paths, files, DNS names or virtual hosts on a web server.

**Why use it:** to discover hidden directories, files, or subdomains that aren’t linked from the site (useful in CTFs/labs).

## Common modes:

dir — directory / file brute-force (e.g. /admin, backup.zip).

dns — subdomain enumeration.

vhost — virtual host discovery.

fuzz — custom fuzzing of any target pattern.

## Example:

```shell
gobuster dir -u http://10.10.10.10 -w /path/to/wordlist.txt -t 50
# ( -u target URL, -w wordlist, -t threads )
```

## Useful flags:

`-x` to try file extensions (e.g. .php,.txt)

`-s` to show only certain HTTP status codes (e.g. 200,301)

`-o` to save output to a file

Tip: pick a good wordlist (SecLists is common) and be respectful — only run against lab/authorized targets.

## Tiny cheatsheet

```shell
# directory brute-force
gobuster dir -u http://target -w /usr/share/wordlists/dirb/common.txt

# directory brute-force with extensions and save output
gobuster dir -u http://target -w wordlist.txt -x php,txt -o results.txt

# subdomain enumeration
gobuster dns -d example.com -w subdomains.txt

# virtual host discovery
gobuster vhost -u http://target -w vhosts.txt
```
