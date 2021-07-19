# Checking OS version in Unix systems

Referring to Linux, you are usually referring to what is called a _distribution_. Linux itself is a kernel, the core component of the operating system. 

A **Linux distribution** is the operating system made on top of a **Linux kernel**, GNU tools and libraries, other than software collections.

Some of the most popular Linux distributions are 
- Debian
- Red Hat
- Ubuntu
- Arch Linux
- Fedora
- CentOS

Knowing what version of Linux is running on a specific machine is always a good idea and could be of great help to figure out, for example, which package manager you should use to install new software.

Below are sone simple commands to check Operating System name and kernel version in use in the machine you will operate.

## Checking OS name and  version

One of the following should do the trick

- `cat /etc/os-release`
- `lsb_release -a`
- `hostnamectl`

## Checking kernel version

- `uname -r`
- `cat /proc/version`


