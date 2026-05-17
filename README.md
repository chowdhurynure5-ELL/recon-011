Recon47

Automated Reconnaissance & Vulnerability Scanner

Author: SHOVON Language: Python Architecture: Modular CLI-based Security Automation Framework


---

1. Vision

Recon47 is a modern automated reconnaissance and vulnerability assessment framework designed for ethical security testing, bug bounty reconnaissance, internal attack surface mapping, and educational cybersecurity automation.

The tool combines:

Fast reconnaissance

Smart attack surface discovery

Automated crawling

Parameter extraction

JavaScript analysis

Technology fingerprinting

Vulnerability scanning

Modern reporting

Hacker-style HTML dashboard reporting


Recon47 is intentionally designed to be:

Lightweight

Fast

Easy to use

Modular

Extendable

Real-world practical


The framework should feel like a professional offensive security utility while remaining beginner-friendly.


---

2. Core Objectives

Recon47 must:

Accept domain, URL, subdomain, or IP as input

Perform automated reconnaissance

Discover attack surface assets

Crawl websites recursively

Extract endpoints and parameters

Collect JavaScript files

Fingerprint technologies

Detect vulnerabilities

Integrate Nikto and Nuclei

Produce structured findings

Generate professional HTML reports

Provide clean and elegant terminal output

Use modular architecture for scalability



---

3. Target Users

Penetration Testers

Bug Bounty Hunters

SOC Analysts

Red Teamers

Cybersecurity Students

Internal Security Teams



---

4. Key Design Philosophy

4.1 Easy to Use

Minimal commands.

Example:

recon47 -t example.com

Advanced mode:

recon47 -t example.com --full --threads 50 --report html


---

4.2 Elegant UX

The console output should:

Use Rich library

Display progress bars

Use colored sections

Show real-time scan status

Display severity levels

Use tables and panels

Look modern and premium


Example style:

Neon green

Red severity indicators

Cyberpunk aesthetics

Animated progress

Structured logs



---

4.3 Modular Architecture

Each functionality remains isolated.

Benefits:

Easier maintenance

Independent testing

Better scalability

Cleaner codebase

Easier future upgrades



---

5. High-Level Features

Reconnaissance

Subdomain enumeration

DNS enumeration

WHOIS lookup

Port scanning

Service detection

HTTP header analysis

SSL/TLS analysis

Technology fingerprinting

JavaScript extraction

Robots.txt parsing

Sitemap parsing

Directory discovery

Endpoint collection

Parameter extraction

Form extraction

Wayback URL collection


Crawling

Recursive crawling

Internal link extraction

JS endpoint extraction

API endpoint discovery

Smart deduplication

Scope validation


Vulnerability Scanning

Nikto integration

Nuclei integration

Custom vulnerability checks

Header misconfiguration detection

Sensitive file detection

Open redirect checks

Basic XSS reflection detection

Basic SQLi pattern detection

Exposed admin panel detection


Reporting

JSON export

TXT export

HTML report generation

Hacker-themed UI report

Severity grouping

Executive summary

Scan metadata

Timeline

Statistics dashboard


Bonus Features

Async scanning

Multi-threading

Rate limiting

Docker support

AI-assisted summaries

Resume scan capability

Screenshot capture

Attack surface graph

Dark mode HTML UI

Live scan dashboard



---

6. Full Architecture

Recon47/
│
├── recon47.py
├── setup.py
├── requirements.txt
├── README.md
├── Dockerfile
├── LICENSE
├── config/
│   ├── settings.py
│   └── banners.py
│
├── core/
│   ├── engine.py
│   ├── runner.py
│   ├── logger.py
│   ├── scope.py
│   ├── rate_limiter.py
│   ├── output.py
│   └── utils.py
│
├── recon/
│   ├── subdomains.py
│   ├── dns_enum.py
│   ├── portscan.py
│   ├── tech_detect.py
│   ├── headers.py
│   ├── crawler.py
│   ├── js_analyzer.py
│   ├── wayback.py
│   ├── robots.py
│   └── screenshot.py
│
├── scanners/
│   ├── nuclei_scan.py
│   ├── nikto_scan.py
│   ├── custom_checks.py
│   ├── xss.py
│   ├── sqli.py
│   ├── open_redirect.py
│   └── sensitive_files.py
│
├── parsers/
│   ├── nuclei_parser.py
│   ├── nikto_parser.py
│   ├── html_parser.py
│   └── js_parser.py
│
├── reports/
│   ├── html_report.py
│   ├── json_report.py
│   ├── txt_report.py
│   ├── templates/
│   │   ├── report.html
│   │   ├── assets/
│   │   ├── css/
│   │   └── js/
│
├── data/
│   ├── wordlists/
│   ├── payloads/
│   └── fingerprints/
│
├── outputs/
│   ├── scans/
│   └── reports/
│
└── tests/
    ├── test_crawler.py
    ├── test_scanner.py
    └── test_parser.py


---

7. Technology Stack

Component	Technology

Language	Python 3.11+
CLI UX	Rich
HTTP	httpx
Async Engine	asyncio
HTML Parsing	BeautifulSoup4
JS Parsing	regex + BeautifulSoup
Port Scanning	python-nmap
DNS	dnspython
Tech Detection	Wappalyzer / custom fingerprints
Reporting	Jinja2
HTML Theme	Cyberpunk Dark Theme
Screenshotting	Playwright
Data Storage	JSON
Vulnerability Scanning	Nuclei + Nikto



---

8. Functional Workflow

Step 1: Input Validation

Accept:

Domain

URL

IP

Subdomain


Validate:

Proper formatting

Reachability

Scope safety



---

Step 2: Reconnaissance Phase

Modules executed:

Subdomain Enumeration

Methods:

crt.sh scraping

SecurityTrails API (optional)

DNS brute-force

Assetfinder integration

Subfinder integration


Output:

[
  "api.example.com",
  "dev.example.com"
]


---

DNS Enumeration

Collect:

A records

AAAA

MX

TXT

NS

CNAME



---

Port Scanning

Use:

Nmap

python-nmap


Detect:

Open ports

Running services

Versions



---

Technology Detection

Identify:

Frameworks

CMS

CDN

Backend stacks

JS frameworks


Examples:

React

Next.js

WordPress

Nginx

Apache



---

HTTP Header Analysis

Detect:

Missing CSP

Missing HSTS

Insecure headers

Server leaks



---

Crawl Engine

Features:

Recursive crawling

JS crawling

Sitemap parsing

Robots.txt parsing

URL normalization

Deduplication

Query parameter extraction



---

JavaScript Analysis

Extract:

API endpoints

Secrets

Tokens

Hidden routes

Sensitive keywords


Regex examples:

api/

token

secret

key

graphql



---

9. Vulnerability Scanning Phase

9.1 Nuclei Integration

Run:

nuclei -u target -severity low,medium,high,critical

Parse:

Severity

CVE

Template ID

Description

Matched URL



---

9.2 Nikto Integration

Run:

nikto -h target

Collect:

Dangerous files

Misconfigurations

Outdated software

Server weaknesses



---

9.3 Custom Security Checks

Security Headers

Check:

CSP

X-Frame-Options

HSTS

Referrer Policy



---

Sensitive Files

Try:

/.env

/backup.zip

/.git/

/admin

/phpinfo.php



---

Open Redirect

Payloads:

?next=https://evil.com


---

Reflection Detection

Simple reflected XSS identification.


---

SQL Error Detection

Check for:

SQL syntax errors

Database leakage



---

10. Smart Features

10.1 Deduplication Engine

Avoid:

Duplicate URLs

Duplicate endpoints

Repeated scans


Use:

Hashing

Canonicalization



---

10.2 Rate Limiting

Prevent overwhelming targets.

Features:

Delay control

Concurrency limit

Retry mechanism



---

10.3 Scope Enforcement

Prevent accidental out-of-scope scanning.


---

10.4 Async Engine

Use asyncio for:

Fast crawling

HTTP requests

Endpoint collection



---

11. CLI Design

Basic Usage

recon47 -t example.com

Full Scan

recon47 -t example.com --full

Fast Mode

recon47 -t example.com --fast

HTML Report

recon47 -t example.com --report html

Custom Threads

recon47 -t example.com --threads 100

Disable Nuclei

recon47 -t example.com --no-nuclei


---

12. Console UX

Features

Animated progress bars

Live status updates

Severity colors

Panels

Tables

Spinner indicators


Example:

[+] Subdomains Found: 14
[+] Open Ports: 5
[!] High Severity Vulnerabilities: 2


---

13. HTML Report Design

Theme

Cyberpunk hacker aesthetic.

Visual style:

Dark background

Neon green accents

Red critical alerts

Terminal-inspired panels

Matrix-style visuals



---

Report Sections

Header

Tool name

Author

Timestamp

Target

Scan duration



---

Executive Summary

Total vulnerabilities

Severity breakdown

Risk score

Attack surface summary



---

Recon Findings

Subdomains

Open ports

Technologies

Headers

JS files

Endpoints



---

Vulnerabilities

Each vulnerability includes:

Title

Severity

Description

Affected asset

Evidence

Recommendation

References



---

Statistics Dashboard

Charts:

Severity pie chart

Endpoint distribution

Open port chart



---

Footer

Generated by Recon47 | Author: SHOVON


---

14. AI-Assisted Summary (Bonus)

Optional module:

Summarize findings

Prioritize risks

Explain vulnerabilities

Recommend remediation


Local summarization supported.


---

15. Docker Support

Dockerfile

Features:

Pre-installed dependencies

Nuclei

Nikto

Python environment


Usage:

docker build -t recon47 .

docker run recon47 -t example.com


---

16. Error Handling Strategy

Handle:

Connection timeouts

Invalid domains

DNS failures

API failures

Interrupted scans

External tool crashes


Never allow full tool crash.


---

17. Logging System

Log Types

INFO

WARNING

ERROR

DEBUG

SUCCESS


Logs saved:

outputs/logs/scan.log


---

18. Setup Requirements

setup.py

Must include:

Metadata

Entry points

Dependencies

Versioning


Example:

from setuptools import setup, find_packages

setup(
    name="recon47",
    version="1.0.0",
    author="SHOVON",
    description="Automated Reconnaissance and Vulnerability Scanner",
    packages=find_packages(),
    install_requires=[
        "rich",
        "httpx",
        "beautifulsoup4",
        "jinja2",
        "python-nmap",
        "dnspython",
        "tldextract",
        "playwright",
        "aiofiles"
    ],
    entry_points={
        'console_scripts': [
            'recon47=recon47:main'
        ]
    }
)


---

19. requirements.txt

rich
httpx
beautifulsoup4
jinja2
python-nmap
dnspython
aiohttp
requests
tldextract
playwright
lxml
colorama
pyfiglet
validators
fake-useragent


---

20. README Requirements

README should contain:

Tool overview

Installation

Usage examples

Screenshots

Report examples

Architecture overview

Legal disclaimer

Docker usage

Feature list



---

21. Real-World Enhancements

Planned Advanced Features

Future Enhancements

Passive recon APIs

ASN enumeration

Cloud bucket discovery

GitHub secret hunting

JWT analysis

GraphQL introspection

SSRF checks

WebSocket analysis

API fuzzing

CVE enrichment



---

22. Security & Ethics

Recon47 must display:

WARNING: Use only on authorized targets.
Unauthorized scanning may violate laws and regulations.

Scope validation is mandatory.


---

23. Performance Targets

Component	Goal

Crawl Speed	100+ URLs/min
Async Requests	500+ concurrent
Report Generation	<5 sec
Startup Time	<2 sec
Memory Usage	Optimized



---

24. Suggested Development Roadmap

Phase 1

Core CLI

Logger

HTTP engine

Input validation


Phase 2

Recon modules

Crawler

JS extraction


Phase 3

Nuclei integration

Nikto integration

Custom checks


Phase 4

Reporting engine

HTML templates

Dashboard visuals


Phase 5

Docker support

AI summaries

Screenshots



---

25. Sample Scan Workflow

User Input
   ↓
Validation
   ↓
Recon Phase
   ↓
Crawler
   ↓
Attack Surface Mapping
   ↓
Vulnerability Scanning
   ↓
Data Aggregation
   ↓
Risk Classification
   ↓
HTML Report Generation


---

26. Risk Severity System

Severity	Color

Critical	Bright Red
High	Orange
Medium	Yellow
Low	Blue
Informational	Green



---

27. Final Deliverables

Mandatory Deliverables

Full Python source code

Modular architecture

setup.py

requirements.txt

README.md

HTML report system

Sample scan outputs

Docker support

Clean CLI UX



---

28. Final Product Positioning

Recon47 should resemble:

A lightweight commercial recon framework

A real bug bounty automation tool

A professional cybersecurity utility

A portfolio-quality offensive security project


The final implementation must prioritize:

Stability

Clean UX

Real-world practicality

Professional reporting

Maintainable architecture

Fast scanning

Ethical usage



---

29. Recommended Libraries

Purpose	Library

CLI UI	Rich
Crawling	httpx + BeautifulSoup
Async	asyncio
DNS	dnspython
HTML Templates	Jinja2
Screenshots	Playwright
Validation	validators
Parsing	lxml
Port Scanning	python-nmap
Charts	Chart.js



---

30. Final Notes

Recon47 should not be just another university assignment.

The goal is to create:

A polished standalone security tool

A usable real-world reconnaissance framework

A modern cybersecurity automation platform

A project suitable for GitHub portfolio showcase

A foundation for future offensive security tooling


The implementation must feel professional, modern, reliable, and production-inspired.# recon-011
