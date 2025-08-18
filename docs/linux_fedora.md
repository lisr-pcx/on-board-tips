# Fedora Linux

I usually work on virtual machines. They give me isolation and security from my primary OS, and they offers a versatile environment for testing and development. Steps below have been written according to that idea.

## Installation

Download the last release of [Fedora Workstation](https://fedoraproject.org/workstation/download).

Create a new virtual machine (use VMware or VirtualBox software) by adding the ISO file just downloaded.

Follow step-by-step instructions. It's quite straightforward but if you feel insecure there are tons of tutorial on the web... at the end you'll get a running version.

Check current version:

```sh
test@fedora:~$ uname -a
Linux fedora 6.8.5-301.fc40.x86_64 #1 SMP PREEMPT_DYNAMIC Thu Apr 11 20:00:10 UTC 2024 x86_64 GNU/Linux
```

## Update

Keep your system and packages updated by running command below:

```sh
test@fedora:~$ sudo dnf update
test@fedora:~$ uname -a
```

Then reboot the system (both commands are equivalent):

```sh
test@fedora:~$ sudo reboot
test@fedora:~$ sudo shutdown -r now
```

I suggest to rarely use `dnf upgrade` due to its harsh behavior during the upgrade process like removing/replacing existing packages or dependencies.

## DNF: the package manager

Basic operations on a package:

```sh
test@fedora:~$ sudo dnf install PACKAGENAME
test@fedora:~$ sudo dnf update PACKAGENAME
test@fedora:~$ sudo dnf remove PACKAGENAME
```

List installed and available packages (or only the installed):

```sh
test@fedora:~$ sudo dnf list
test@fedora:~$ sudo dnf list installed
```

Check latest update for your packages:

```sh
test@fedora:~$ sudo dnf check-update
```

Search a package by name, and get specific info:

```sh
test@fedora:~$ sudo dnf search NAME
test@fedora:~$ sudo dnf info PACKAGENAME
```

Show repository:

```sh
test@fedora:~$ sudo dnf repolist all
```

## Customization

Few additional operations I usually do after a fresh installation.

### Mount local shared folder (VMware)
Note: add the desired folder in the VMware configuration panel, then run the virtual machine and run the command

```sh
test@fedora:~$ sudo mkdir /media/shared
test@fedora:~$ sudo /usr/bin/vmhgfs-fuse .host:/ /media/shared -o subtype=vmhgfs-fuse,allow_other
```

### Install Git

Git is already pre-installed on Fedora. Just configure your account:

```sh
test@fedora:~$ git config --global user.name "YOUR NAME"
test@fedora:~$ git config --global user.email "YOUR EMAIL ADDRESS"
```

### Install C/C++ toolchain

```sh
test@fedora:~$ sudo dnf install gcc
```

### Install RUST toolchain

Make sure you have gcc toolchain, then follow instruction [here](https://www.rust-lang.org/learn/get-started).

### Install Python toolchain

Python is already pre-installed on Fedora. Just check the version and eventually updated it...  
Check also PIP (Python package manager).

```sh
test@fedora:~$ python --version
Python 3.12.7
test@fedora:~$ pip --version
pip 23.3.2 from /usr/lib/python3.12/site-packages/pip (python 3.12)
test@fedora:~$ pip install mkdocs
pip 23.3.2 from /usr/lib/python3.12/site-packages/pip (python 3.12)
```

I highly recommend to install specific packages into specific virtual environment of each project.

### Install VSCode

Upgrade packages:

```sh
test@fedora:~$ sudo dnf upgrade --refresh
```

Import VSCode GPG key to verify the authenticity of the installed packages:

```sh
test@fedora:~$ sudo rpm --import https://packages.microsoft.com/keys/microsoft.asc
```

Import VSCode RPM Repository using the command below (it creates a new repository file with the necessary configuration to access the Visual Studio Code packages):

```sh
test@fedora:~$ printf "[vscode]\nname=packages.microsoft.com\nbaseurl=https://packages.microsoft.com/yumrepos/vscode/\nenabled=1\ngpgcheck=1\nrepo_gpgcheck=1\ngpgkey=https://packages.microsoft.com/keys/microsoft.asc\nmetadata_expire=1h" | sudo tee -a /etc/yum.repos.d/vscode.repo
```

Finalize Installation (for stable version):

```sh
test@fedora:~$ sudo dnf install code
```

Run VSCode and install desired extensions:

+ Git Graph (mhutchie)
+ Markdown Preview Github Stylng (Matt Bierner)
+ Python (Microsoft)
+ rust-analyzer (The Rust Programming Language)
