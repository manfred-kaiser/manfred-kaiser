
# [SSH-MITM Server](https://github.com/ssh-mitm/ssh-mitm) <img src="https://github-readme-stats.vercel.app/api?username=manfred-kaiser&show_icons=true&hide=stars&count_private=true" align="right">


**SSH-MITM is a man in the middle (mitm) server for security audits supporting public key authentication, session hijacking and file manipulation.**

## Installation SSH-MITM

The first step to using any software package is getting it properly installed.

To install SSH-MITM, simply run this simple command in your terminal of choice:

    $ pip install ssh-mitm

## Connect to the network

To start an intercepting mitm-ssh server on Port 10022, all you have to do is run a single command.

```bash
# start the mitm server
$ ssh-mitm server --remote-host 192.168.0.x

# connect to the mitm server
$ ssh -p 10022 user@proxyserver
```
## Spoofing FIDO Tokens

SSH-MITM is able to spoof FIDO Tokens which can be used for 2 factor authentication.

The attack is called [trivial authentication](https://docs.ssh-mitm.at/trivialauth.html) ([CVE-2021-36367](https://docs.ssh-mitm.at/CVE-2021-36367.html), [CVE-2021-36368](https://docs.ssh-mitm.at/CVE-2021-36368.html)) and can be enabled with the command line argument `--enable-trivial-auth`.

  ssh-mitm server --enable-trivial-auth

Using the trivial authentication attack does not break password authentication, because the attack is only performed when a publickey login is possible.

<p align="center">
  <b>Video explaining the spoofing attack:</b><br/>
  <i>Click to view video on vimeo.com</i><br/>
  <a href="https://vimeo.com/showcase/9059922/video/651517195">
  <img src="https://github.com/ssh-mitm/ssh-mitm/raw/master/doc/images/ds2021-video.png" alt="Click to view video on vimeo.com">
  </a>
</p>

<p align="center">
  <b><a href="https://github.com/ssh-mitm/ssh-mitm/files/7568291/deepsec.pdf">Downlaod presentation slides</a></b>
</p>
