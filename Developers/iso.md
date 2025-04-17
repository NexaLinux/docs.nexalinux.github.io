---
label: Creating an ISO
icon: file-zip
order: -3
---

Heavy packaging of Nexa Linux can be difficult, which is why we made our own ISO packaging script.

!!!contrast DO NOT USE!
At this time, Nexa Linux is being rebased to Ubuntu, and the scripts most likely don't work!
!!!

!!!primary
We use Penguins' eggs for packaging Nexa Linux. Huge thanks to the developer, [Piero Proietti](https://github.com/pieroproietti), for developing this awesome project.
!!!

!!!danger Development only
The ISO creator script is used for development ONLY. Please, do **NOT** run this on your main PC.
!!!

First, start off with a clean Ubuntu [VM](https://en.wikipedia.org/wiki/Virtual_machine).

Set a password for the root password with `sudo passwd root` (it will be removed later).

!!!info
You have to use a [TTY](<https://en.wikipedia.org/wiki/Tty_(Unix)>). Just press `CTRL + ALT + F5` and log in as the root user.
!!!

Once you're in, clean up after the user that you had to make while installing:

```bash
userdel YOUR_USERNAME
rm -rf /home/YOUR_USERNAME
```

Then, install `wget`, `nano` and `python3`:

```bash
sudo apt install -y nano wget python3
```

!!!warning Warning
Penguins' eggs uses nano for editing `/etc/sudoers`, and we will be doing that, so don't try replacing it with a different editor (e.g Neovim.)
!!!

After installing the packages, download the necessary scripts:

```bash
mkdir /tmp/nexa-prod/
wget https://scripts.nexalinux.xyz/nlcs.py -O /tmp/nexa-prod/nlcs.py
wget https://scripts.nexalinux.xyz/iso.py -O /tmp/nexa-prod/iso.py
```

Remove `wget` HSTS rules:

```bash
rm ~/.wget-hsts
```

And now, execute `nlcs.sh` ([NLCS](https://docs.nexalinux.xyz/developers/nlcs/)):

!!!danger Danger ahead!
Like mentioned before, please, do **NOT** execute the script on your main PC. If you do, don't even try making an issue, as that's 100% your fault.
!!!

```bash
python3 /tmp/nexa-prod/nlcs.py
```

After that's done, immediately run the ISO creator:

```bash
python3 /tmp/nexa-prod/iso.py
```

!!!info Info
When Penguins' eggs tells you to edit `/etc/sudoers`, find the commented line that enables any user in the group `%wheel` to run sudo commands and uncomment it. Then press `CTRL + S` to save and `CTRL + X` to exit.
!!!

And now, grab the ISO in `/home/eggs` and you're done!

!!!info
If you want to redistribute our ISO, please, follow [the GNU GPL 3.0 license](https://nexalinux.xyz/license.txt)!
!!!
