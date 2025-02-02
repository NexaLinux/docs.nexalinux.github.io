---
label: Convert Arch Linux to Nexa Linux
icon: star-fill
---

# Converting an Arch Linux installation to Nexa Linux

!!!warning Warning
The script was made to be used for development ONLY. Use at your own risk!
!!!

!!!danger Danger
The script is still in development. DO NOT USE IT ON YOUR MAIN MACHINE.
!!!

Want to switch from Arch Linux to Nexa Linux? This script makes it easy.

First, install `wget` if it isn't installed:

```bash
sudo pacman -S --noconfirm wget
```

After that's done, download the script:

```bash
wget nexalinux.github.io/scripts/arch-to-nexa.sh
```

Make the script executable:

```bash
chmod a+x arch-to-nexa.sh
```

And now, execute it:

```bash
./arch-to-nexa.sh
```
