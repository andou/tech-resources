# How to check OS version in Unix systems

## Checking OS name and  version

One of the following should do the trick

- `cat /etc/os-release`
- `lsb_release -a`
- `hostnamectl`

## Checking kernel version

- `uname -r`
- `cat /proc/version`


