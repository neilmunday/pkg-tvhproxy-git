# pkg-tvhproxy-git

An Arch Linux package for the fork of [tvhproxy](https://github.com/chkuendig/tvhProxy) by @chkuendig

The package is based upon based upon https://aur.archlinux.org/tvhproxy-git.git but modified to work with the fork.

Usage:

```
makepkg -si
```

Once installed, edit `/etc/conf.d/tvhproxy` to match your configuration.

You can then start the service like so:

```
systemctl start tvhproxy
```
