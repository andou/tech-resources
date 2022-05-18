# Checking real time server access with GoAccess

## Rationale

This short guide is intended to give a brief guidance to make [GoAccess](https://github.com/allinurl/goaccess) work on your local machine showing remote server accesses.

## Prerequisites

### Access

You'll need **ssh public key access** to your remote server to have live reporting. Otherwise you'll have to settle with a non-live check.

### Software

You'll need to have installed locally only these pieces of software
- [http-server](https://github.com/http-party/http-server) -> _[Installation](https://github.com/http-party/http-server#installation)_
- [GoAccess](https://github.com/allinurl/goaccess) -> _[Installation](https://github.com/allinurl/goaccess#installation)_

## Prepare your environment

First things first, choose a directory where to work or create it

```
mkdir -p ~/projects/goaccess
cd ~/projects/goaccess
```

## Tailing from the remote

Then you'll want to tail a porting of the right remote log file inside a reduced local log file.

```
ssh -n -i ~/path/to/your/key <user>@<remote_server_address> 'tail -n5000 -f /var/log/httpd/remote-access-log' > local.log
```

Make sure to tune the `-n` parameter to achieve the right history to track. It does depends on your site accesses.


## Bringing up GoAccess

From another window, from the very same folder, issue this command

```
LANG="en_US.UTF-8" bash -c 'goaccess local.log -o index.html --log-format=COMMON --real-time-html'
```

The right command should be `goaccess local.log -o index.html --log-format=COMMON --real-time-html`, the above wrapping up is to avoid some [language/date issues](https://github.com/allinurl/goaccess/issues/1571#issuecomment-543186858)

## Bringing up http-server

Now, from another window, from the very same folder, issue this command

```
http-server .
```

And magic :mage: appears! Go to [http://localhost:8080/](http://localhost:8080/) and enjoy!
















