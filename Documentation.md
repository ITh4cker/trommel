# TROMMEL Documentation

* Download TROMMEL
* Download vFeed database from vFeed tool from https://vfeed.io/pricing/. 
	* This database needs to be placed in the root of the working directory of TROMMEL.

# Handling Dependencies
* The vFeed database is addressed above.
* Python-magic
	* For Linux:
		* pip install python-magic
	* For Mac:
		* brew install libmagic
		* pip install python-magic

# Usage

```
$ trommel.py --help
```

Output TROMMEL results to a file based on a given directory
```
$ trommel.py -p /directory -o output_file
```

* TROMMEL sifts through directories of files to identify indicators that may contain vulnerabilities. Specifically, TROMMEL identifies the following indicators: 
	* Secure Shell (SSH) key files
	* Secure Socket Layer (SSL) key files
	* Internet Protocol (IP) addresses
	* Uniform Resource Locators (URLs)
	* email addresses
	* shell scripts
	* web server binaries
	* configuration files
	* database files
	* specific binaries files (for example, Dropbear, BusyBox, and others) 
	* shared object library files
	* web application scripting variables
	* Android application package (APK) file permissions
* TROMMEL integrates vFeed, which is a database wrapper that pulls in content from Common Vulnerabilities and Exposures (CVE) database, Exploit-DB, and Metasploit. 
* vFeed offers a free, downloadable Community Database for non-commercial users. 
* This integration allows for further in-depth vulnerability analysis of identified indicators. 
* TROMMEL significantly lessens the manual analysis time of the researcher by automating much of the vulnerability discovery and analysis process. 
* Upon execution, TROMMEL provides the following feedback to the researcher in the terminal:
	* TROMMEL is working to sift through the files.
	* Results will be saved to "[Researcher Supplied File Name]_Trommel_YYYYMMDD_HHMMSS"
* The identified indicators are then saved to a text file in the current working directory of TROMMEL. 
* The text file is named according to the above naming convention and will contain the following information preceding the identified indicators:
	* Trommel Results File Name: [Researcher Supplied File Name]
	* Directory: [Researcher Supplied Directory]
	* There are [Count of Files] total files within the directory.
	* Results could be vulnerabilities. These results should be verified as false positives may exist.
* The indicators should be reviewed to identify and remove false positives and to identify indicators that need further analysis for potential vulnerabilities. 