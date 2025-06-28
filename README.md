# ClipShare - Package Repository

ClipShare is a lightweight and cross-platform tool for clipboard sharing. ClipShare enables copying text, files, and images on one device and pasting on another. ClipShare is simple and easy to use while being highly configurable.

This repository contains `deb` packages of ClipShare for Ubuntu-based Linux distributions.

## Installation

> **Note:** It's advised to remove any previous installations of ClipShare (installed by other means) to avoid conflicting with this installation.
If you have installed ClipShare with the installation scripts in the [releases](https://github.com/thevindu-w/clip_share_server/releases), you can remove them by deleting the following paths.
> - ~/.local/bin/clip_share
> - ~/.config/systemd/user/clipshare.service

1. **Identify the distribution**

    The remaining steps require using the correct version codename for the OS distribution. The version names for the recent Ubuntu LTS versions are,

<table align="center">
<tr>
<th style="text-align:center">Version</th>
<th style="text-align:center">Name</th>
</tr>
<tr>
<td align="center">24.04</td>
<td align="center">noble</td>
</tr>
<tr>
<td align="center">22.04</td>
<td align="center">jammy</td>
</tr>
<tr>
<td align="center">20.04</td>
<td align="center">focal</td>
</tr>
<tr>
<td align="center">18.04</td>
<td align="center">bionic</td>
</tr>
</table>

* For other non-LTS versions, use the last LTS version released before your Ubuntu version.
* For other Ubuntu flavors (ex: Kubuntu, Xubuntu, Lubuntu, Ubuntu MATE) and other Ubuntu-based distributions (ex: Mint, Pop!_OS, Elementry OS, Zorin OS, etc), use the Ubuntu version name, which your distro is based on.
For example, Linux Mint 22.1 _Xia_ is based on Ubuntu _noble_.

2. **Add the repository as a package source.**

    Run the following commands to add the ClipShare repository to `apt`.
    ```bash
    CODENAME='noble'  # Replace 'noble' with your Ubuntu version name
    echo "deb [arch=amd64 signed-by=/etc/apt/trusted.gpg.d/clipshare-package.gpg] https://thevindu-w.github.io/clipshare-packages/ubuntu ${CODENAME} main" | sudo tee /etc/apt/sources.list.d/clipshare.list >/dev/null
    ```

3. **Add the GPG key**

    Run the following command to add the ClipShare repository to `apt`.
    ```bash
    wget -qO - https://thevindu-w.github.io/clipshare-packages/clipshare-package.gpg | sudo tee /etc/apt/trusted.gpg.d/clipshare-package.gpg >/dev/null
    ```
    Alternative command if the above fails
    ```bash
    sudo curl -L -o /etc/apt/trusted.gpg.d/clipshare-package.gpg https://thevindu-w.github.io/clipshare-packages/clipshare-package.gpg
    ```

4. **Install/Update ClipShare**

    Run the following commands to install or update ClipShare.
    ```bash
    sudo apt-get update
    sudo apt-get install -y clipshare-server
    ```

5. **Setup auto-start on login and Create configuration file** (Optional)

    Run the following command without `sudo` or root privileges.
    ```bash
    setup-clipshare
    ```

## Updating

You need to run only the 4<sup>th</sup> step above to update ClipShare.