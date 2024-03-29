# SCRAMBLED_WEBS
Network web traffic generator and aggragator driven by YML based campaign files

# Releases
[Pre-Release 1.0.0 (winx64) Download](https://github.com/michaelrinderle/scrambled_webs/releases/download/V1.0.0W/scrambled_webs_1.0.0.zip)

* Demo 
![Screenshot](demo.gif)

# Privacy & Security Research Tool
	* Find data you didn't now existed
	* Locate developing data points
	* Generate web traffic for network stress testing
	* Obfuscate traffic from malicious eavesdropping
	* Protect privacy by tainting mined user data
	* Extend for machine learning inputs

# Easy To Use
	* Use simple YML files to map your campaigns
	* Keyword based seeding for specific targeting
	* Minimal requirements

# Features 
	* Run campaigns using browsers in headless mode
	* Logging support
	* Ability to run as startup service for privacy purposes
	* Proxy support
	* Run as a start up service 
	* Written in .NetCore, easy to exend

# Requirements 
	* .Net4  
	* Selenium
	* Firefox or Chrome 
	* More browsers to come

# Todo 
	* Bot campaign support for browserless campaigns
	* Multi-threading for multiple campaigns
	* Task based pipeline for easy custom user actions
	* Machine learning pipeline for mined data
	* Custom User Module Support 
	* More browser support
	* Refactoring to configurable fluent data analysis pipelines.
	* Interactive UI

# Usage

Supply ScrambledWebs with the `-p` flag and the path to the campaign Yml file. `--verbose` is optional an defaults to false if your campaign setting for logging is not set. If a flag and path is not specificed, ScrambledWebs will look in current directory for `campaign.yml` 

Usage:
`scrambledwebs.exe [path, -p, --p] [verbose, --verbose]`
`scrambledwebs.exe -p campaign.yml -verbose `
`scrambledwebs.exe` 

# Configuration 
* Campaign Yml File 
You can map out the campaign to your own liking by creating a Yml campaign file.
`campaign.yml` is in the project directory as a template to use for your custom campaign.

```
Campaign: # (string) 
Author: # (string)
Duration: # (int) 0 means forever
Logging: # (bool) 
LogPath: # (string) path to log file
Browser:  # (browser)
    Type: # (enum) firefox | chrome
    HtmlOnly: # (bool) does not download images
    Headless: # (bool) run without browser window
    Incognito: # (bool)
    Agent: # (bool) user agent string 
    WindowHeight: # (int)
    WindowWidth: # (int)
    MaxDepth: # (int) max number of pages to visit from a site
    MinDepth: # (int) min number of pages to visit from a site
    MaxWait: # (int) max number of seconds to wait before next site
    MinWait: # (int) min number of seconds to wait before next site
    MaxQueue: # (int) number of links to store for scrambling
    Proxy:
        Enabled: # (bool)
        Host: # (string)
        Port: # (int)

Urls:  # urls to seed scrambler with
    - # (string)
    - https://www.msnbc.com
    - https://www.foxnews.com
    - https://www.nbc.com
    - https://www.vox.com/


Blacklist:  # sites to block aggragating
    - https://www.facebook.com
    - https://www.twitter.com

BannedKeywords: # banned keywords for uri parsing
    - mp3
    - mp4
    - zip
```
