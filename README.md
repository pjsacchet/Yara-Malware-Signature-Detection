# Project - MalwareSig
Code Written by Javon Kitson :octocat: & Patrick Sacchet :man:

## Purpose
The purpose of this program is to demonstrate current capabilities of antivirus programs, implementing their means of generic malware signature identification. This will be done via the YARA module, using self defined rule files that will determine whether or not a file is malicious. In accomplishing a simple program that can use these rule files in a multitude of ways we hope to educate on one simple way antivirus programs work to continuously scan and keep the security of our own computers safe.  

## How to run
  For default test directories:
  ```
  python3 MalwareSig.py
  ```
  To add your own directories for rule files (-r) and malicious files (-m):
  ```
  python3 MalwareSig.py  -r *ruledirectory* -m *malwaredirectory*
  ```
  For help:
  ```
  python3 MalwareSig.py -h
  ```

## How to Install
The program doesn't work unless YARA is installed
```
pip3 install yara-python
```

If running in the linux lab then install with:
```
pip3 install yara-python --user
```

## File Structure
* logs - Directory where all log files will be kept. Each instance of MalwareSig will produce a log file with the current day and time as the name
* malware_files - Test directory with some homemade malicious files that may or may not be detected as malware!
* rules - Test directory with some homemade rule files that will help detect malware
* MalwareSig.py - Main functionality, print commands and parsing command line
* YaraScanner.py - Implements a YaraScanner object, with which we can use YARA rules to identify malware and write to a log file

## How it works
### Scanning Functionality:
The scanning is split into a few main pieces:
  1. make_dict - In order to compile yara rules, we need to create a dictionary with rule file names as keys and their file locations as the values.
  2. scan_files - Compiles the yara rule dictionary, grabs the file path and calls yara_sig_check
  3. yara_sig_check - Takes a file and the compiled rules and checks to see if any rules are triggered, if any are, results are written to the log file via write_log

### Usability and User interactions
*    Default output is to scan malware_files
* If the input is ```-h```:
  * The program prints a list of possible command line args
* If the input is ```-r```:
  * Pass rule files (requires malicious file(s) passed in addition)
* If the input is ```-m```:
  * Malicious file(s) to be scanned (requires rule files passed in addition)

## Tools used
YARA, Python, & Dr. Olsen's ultimate wisdom and guidance

## Honor Code Statement
We Javon Kitson & Patrick Sacchet understand and will uphold the ideals of academic honesty as stated in the Honor Code and course syllabus.

## TODO:
In continuing this project, I aim to make a CLI for the user, implement full system scanning, and eventually establish a connection to a server of my own that hosts signature files that can be downloaded and used in daily scans, simulating a real day Antivirus program. 
