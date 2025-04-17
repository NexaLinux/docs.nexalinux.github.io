---
label: Nexa Linux Conversion Script
icon: arrow-switch
---

# Nexa Linux Conversion Script

!!!contrast DO NOT USE!
At this time, Nexa Linux is being rebased to Ubuntu, and the script most likely doesn't work!
!!!

The [Nexa Linux Conversion Script (NLCS)](https://github.com/NexaLinux/scripts) is used by developers, for better coding experience and easier ISO packaging. It is completely open-source, which means you can help us by making a [Pull Request](https://github.com/NexaLinux/scripts/pulls)!

!!!danger Development only
This script is made to be used for development purposes only. It is not recommended to run it on your System.
!!!

## Usage

**If you will use this script, we recommend doing it in a [Virtual Machine](https://en.wikipedia.org/wiki/Virtual_machine).** <br>

### Enter a TTY

For the script to work, you need to be running it in a [TTY](<https://en.wikipedia.org/wiki/Tty_(Unix)>). To do that, press `CTRL + ALT + F5` and log in.

### Download and run

To use NLCS, first you need to install `wget` and `python3`:

```bash
sudo apt install -y wget python3
```

After that, you need to download the script:

```bash
wget https://scripts.nexalinux.xyz/nlcs.py
```

!!!warning
The creators of this script are not responsible for any damages caused to your PC!
!!!

And now, execute it:

```bash
python3 nlcs.py
```
