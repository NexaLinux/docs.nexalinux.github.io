---
label: Package Repository
icon: package
---

For easier installation, we made our own package repository that contains tools like [nexa-cmd](https://github.com/NexaLinux/nexa-cmd).

!!!contrast
The package repository doesn't currently work. Do NOT use it!
!!!

## Usage

You can use the repository, using `pacman` or `nexa apt` (included in [nexa-cmd](https://github.com/NexaLinux/nexa-cmd)).

### Editing your pacman.conf

!!!info
If you use Nexa Linux, you do not need to do this.
!!!

First, open your terminal and run:

```bash
sudo nano /etc/pacman.conf
```

Then, scroll until you see the repositories (`core`,`extra` and etc.) and add this:

```
[nexa-pkg]
SigLevel = Optional TrustAll
Server = https://packages.nexalinux.xyz
```

You can now press `CTRL + X` then `Y` and enter.

After that's done, update your package repositories:

```bash
sudo pacman -Sy
```

### You can install packages using `sudo pacman -S [package]`.
