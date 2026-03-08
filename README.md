Assignment 6 – APT
Part 1: Understanding APT & System Updates
APT version
Command:
apt --version
Updating the package list
Command:
sudo apt update
Why this is important:  
Updating refreshes the local package index so the system knows the newest available versions.

Upgrading installed packages
Command:
sudo apt upgrade -y
Difference between update and upgrade:
update refreshes the package list.
upgrade installs newer versions of installed packages.

Viewing pending updates
Command:
apt list --upgradable

Part 2: Installing & Managing Packages
Searching for an image editor
Command:
apt search image editor
Chosen package:  
xpaint

Viewing package details
Command:
apt show xpaint
Dependencies:  

Installing the package
Command:
sudo apt install xpaint -y
Result:  
Package installed successfully.

Checking installed version
Command:
apt list --installed | grep xpaint

Part 3: Removing & Cleaning Packages
Removing the package
Command:
sudo apt remove xpaint -y
Purging configuration files
Command:
sudo apt purge xpaint -y
Difference between remove and purge:
remove deletes the program but keeps configuration files.
purge deletes both the program and its configuration files.

Removing unused dependencies
Command:
sudo apt autoremove -y
Why this is important:  
It removes leftover packages that are no longer needed.

Cleaning the package cache
Command:
sudo apt clean
What this does:  
Deletes all downloaded .deb files from the cache.

Part 4: Managing Repositories & Troubleshooting
Listing APT repositories
Command:
cat /etc/apt/sources.list
Observation:  
Ubuntu 24.04 uses the new deb822 format stored in /etc/apt/sources.list.d/ubuntu.sources.

Adding the universe repository
Commands:
sudo add-apt-repository universe
sudo apt update
What is in the universe repository?  
Community-maintained open‑source software.

Simulating an installation failure
Command:
sudo apt install fakepackage
Error message:
E: Unable to locate package fakepackage
How to troubleshoot:
Check spelling of the package name.
Run sudo apt update.
Search for the package using apt search.
Ensure correct repositories (main, universe, multiverse) are enabled.
