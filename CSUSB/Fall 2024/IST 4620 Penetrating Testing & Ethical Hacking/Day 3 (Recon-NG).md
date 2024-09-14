
#### Recommended OSINT Book
Only $20: intenltechniques.com/books.html

#### Black hills infosec
They help cybersecurity studnets get in the field. They sponsor the Recon-ng tool
- https://www.blackhillsinfosec.com/

# Recon-ng
marketplace - Interfaces with the module marketplace
modules - Interfaces with installed modules

## Profiler
Profiler searches the internet for common and popular websites using a particular username

#### Class work
~ help
~ marketplace install profiler
	- This **installs** the **module** profiler
~ modules load profiler
	-   {Tool} {Workstation} {Module}
	- We **loaded** the profiler **module** here
~ options set SOURCE inteltechniques
	- **sets** our target, or source to be **inteltechniques**
~ input
	- This validates, or verify that everything is loaded
~ run
	- Runs the script
~ show profiles
	- Shows all instances of a username being used on common websites
~ Back
	- To change modules
	![[Pasted image 20240905134339.png]]

----

##### Errors in the script

This helps you identify if your target has a profile on these websites
- If there's an error, it's because we don't have an API.
- That API is supposed to pull information
x for example, will give you an API if you apply for one.

#### Searching humanhacker username
~ modules load profile
~ options set SOURCE humanhacker
~ input 
~ run
~ Show results

#### Downloading different domains
~ marketplace install bing_domain_web
~ marketplace install google_site_web
~ marketplace install brute_suffix
~ marketplace install pgp_search
	- Used for encrypted email
~ marketplace install html

#### Testing a website against a search engine
~ Modules load bing_domain_web
~ options set SOURCE cnn.com
~ run

We're going to see everything that CNN.com is related too
- It failed

~ modules load google_site_web
~ options set SOURCE cnn.com
~ run

Same thing on Googles
- It worked

These methods are interesting to use when we have a smaller target with certain websites
- **Some URLs should not be public**
- Admin, or robots.tec?
This tool will uncover them.

#### Search PGP (Encrypted emails)
~ Modules load pgp_search
~ options unset SOURC
~ options set SOURCE cnn.com
~ run

#### HTML
~ modules load html
~ options set CUSTOMER CSUSB
~ options set CREATOR Z.Taylor
~ run 
*Report gets generated*

If you open the report, it gives a summary of everything you did, the host, and your profile. 

**This report is what we will submit for our HW**
# HW
Run recon-ng, install APIs....and see if we can get more or less results with those APIs.
- Not looking for 100% completion, he wants to see if we can do it. 

There will be a pre-assement quiz on tuesday.
