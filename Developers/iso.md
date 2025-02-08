---
label: Creating an ISO
icon: file-zip
---

Heavy packaging of Nexa Linux can be difficult, which is why we made our own ISO packaging script.

!!!primary
We use Penguins' eggs for packaging Nexa Linux. Huge thanks to the developer, [Piero Proietti](https://github.com/pieroproietti), for developing this awesome project.
!!!

!!!danger Critical warning
The ISO creator script is used for development ONLY. Please, do NOT run this on your main PC and redistribute the ISO.
!!!

First, start off with a clean Arch Linux [VM](https://en.wikipedia.org/wiki/Virtual_machine). No desktop enviroment, no users. Use the root user. You can set any password for `root` you like, it will be removed later.

!!!info
You can also use a [TTY](https://en.wikipedia.org/wiki/Tty_(Unix)). Just press `CTRL + ALT + F5` and log in.

Once you're in, install `wget` and `nano`.

```bash
sudo pacman -S nano wget
```

!!!warning Warning
There is a very high chance Penguins' eggs uses nano for editing `/etc/sudoers`, and we will be doing that, so don't try replacing it with a different editor (e.g Neovim.)
!!!

After installing the packages, download the necessary scripts:

```bash
wget https://nexalinux.github.io/scripts/arch-to-nexa.sh -O /tmp/nexa-prod/arch-to-nexa.sh
wget https://nexalinux.github.io/scripts/iso.sh -O /tmp/nexa-prod/iso.sh
```

Remove `wget` HSTS rules:

```bash
rm ~/.wget-hsts
```

Make the scripts executable:

```bash
chmod +x /tmp/nexa-prod/*
```

And now, execute `arch-to-nexa.sh` ([NLCS](https://docs.nexalinux.xyz/developers/nlcs/)):

!!!danger Danger ahead!
Like mentioned before, please, do __NOT__ execute the script on your main PC. If you do, don't even try making an issue, as that's 100% your fault.
!!!

```bash
/tmp/nexa-prod/arch-to-nexa.sh
```

After that's done, immediately run the ISO creator:

```bash
/tmp/nexa-prod/iso.sh
```

!!!info Info
When Penguins' eggs tells you to edit `/etc/sudoers`, find the commented line that enables any user in the group `%wheel` to run sudo commands and uncomment it. Then press `CTRL + S` to save and `CTRL + X` to exit.
!!!

And now, grab the ISO in `/home/eggs` and you're done!

!!!info
If you want to redistribute our ISO, please, follow [the GNU GPL 3.0 license](https://nexalinux.xyz/license.txt)!
!!!
