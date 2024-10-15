# Hack.lu 2024 Workshop

Lookyloo, Pandora, and all the bells and whistles to go with them.

The goal of the tool suite is to make it easier to handle suspicious contents reported by
your users, friends or constituents. It empowers them to check URLs, emails, or files
they receive and take educated decisions without relying on you all the time.

This workshop will go in depth on how you can configure Lookyloo and Pandora, and
all the other tools that make it a complete tool suite usable in your organization
with minimal manual work. We will also look at the correlation features to pivot across
captures to find phishing campaigns in the 4+ millions captures gathered across
the years on the CIRCL Lookyloo instance.


# Target Audience

The target audience for this workshop is relatively technical, but as long as you're using
the demo interfaces, you do not need deep sysadmin skills and some python should do.

If you'e setting up your own instances of the tools, you will need to be pretty fluent using linux.

# Attendance at Hack.lu 2024

Please make sure before attending this workshop that you can install python 3
software on your device, and your device should preferably be running Ubuntu 24.04
or more recent. As the workshop is relatively short and depending on how many people
will attend, we may not have time to do a lot of sysadmin work during the workshop.

The tools we will use are the following:

* Lookyloo (to analyze URLs)
* Pandora (to analyze files)
* Lacus (optionally, to capture the URLs when you have a lot of them)
* An URL monitoring interface (to compare a specific URL over time)
* Phishtank Lookup (to check if a URL is known or not)

We will also see how to integrate Lookyloo and Pandora to handle the cases
where the URL points to a file, and where the file is a web document, or it contains URLs.

Integration with 3rd party services:

* MISP (to share the indicators)
* Ticketing system (to manage interactions with other entities, typically take down requests)
* Validate if URL is known with VirusTotal, PhishtankLookup, URLScan, URLHaus
* Validate if a file is known with Virustotal, ManwareBazaar, HybridAnalysis, MwDB, JoeSandbox
* Add contextual information with SaneJS, uWhoisd, Hashlookup

# Setup guide

## Work environment

We assume you have the following environment at your disposal:

* Ubuntu 24.04. It can be an other similar general purpose operating system (Debian 10, Fedora),
  but specialized distros such as Kali Linux are strongly discouraged and won't be supported if you have issues.

  **NOTE**: It is assumed that you're *not* running as root, but the account you're using is administrator (tl;dr: `sudo` works)

* Python 3.10, 3.11, or 3.12

  **NOTE**: Check it by running `python -V` in a terminal.

* Basic command line tools: `curl`, `wget`, `grep`, `git`
* [Poetry](https://github.com/python-poetry/poetry) 1.8.0 (or more recent), preferably installed this way:
  ```
  curl -sSL https://install.python-poetry.org | python3 -
  ```

  Make sure Poetry is working by running `poetry self -V` in a terminal.

## Install

1. Clone the repository (requires `git`)
  ```bash
  git clone https://github.com/Yoyodyne-IT/2024_Hack.lu.git
  cd 2024_Hack.lu
  ```

2. Install the dependencies
  ```bash
  poetry install
  ```

3. Run the lab
  ```bash
  jupyter-lab
  ```

4. Move to your browser. Running `jupyter-lab` should have opened a tab in your favorite browser.
If it didn't, look in the terminal for hints.
