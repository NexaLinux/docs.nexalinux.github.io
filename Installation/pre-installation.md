---
label: Pre-installation
icon: package-dependencies
order: -2
---

!!!warning Under Construction
This section is still being developed.
!!!

We appreciate you choosing Nexa Linux!

## Obtain the Installation Image

Head over to the [Download](https://nexalinux.xyz/download) page and grab the latest ISO file.

### Validate the Hash

Verifying the image hash is strongly recommended before use, particularly when downloading from a HTTP mirror, as downloads can be intercepted and [tampered with](https://www2.cs.arizona.edu/stork/packagemanagersecurity/attacks-on-package-managers.html).

==- Retrieve the SHA-256 checksum for your image
Filename | SHA-256
--- | ---
nexalinux_dev_2025.3_amd64_2025-03-16_0818.iso | 7b210266ea8e765f10a63be518fe911a4d3e8687d1d3d3baa25dd5f2cb44a2e1

===
To verify the SHA-256 checksum, execute the following command, replacing `<filename>` with the ISO's actual name and `<sha256>` with the corresponding hash.

+++ Windows
Open Windows PowerShell and run:

```cmd
certutil -hashfile <filename>.iso SHA256
```

Compare the output with the hash you got from here.

+++ Linux/macOS
Open Terminal and enter:

```bash
echo "<sha256> <filename>.iso" | sha256sum -c
```

+++

## Create an Installation Medium

To install Nexa Linux, you’ll need a USB flash drive. The ISO can be written to the USB using [Balena Etcher](https://etcher.balena.io/#download-etcher).

!!!info
Use a USB drive with at least 8GB of storage.
!!!

### Get Balena Etcher

Download Balena Etcher from the [official site](https://etcher.balena.io/#download-etcher).

### Flash the ISO

Launch Etcher, select the ISO file, and choose your USB drive. Click Flash! and wait for the process to complete. <br>
**Once done, your Nexa Linux installation medium is ready!**

-![](https://github.com/user-attachments/assets/655d8208-0354-4447-91be-f086d8fc42f0)
