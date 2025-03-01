# gnome-cedilla-fix

[Versão em português](README_ptbr.md)

Configure your Gnome "US-International" keyboard layout to generate a cedilla c
(ç) instead of an accented c (ć). This project should be particularly useful to
Brazilian Portuguese users with a US-International layout, but could also be
used by anyone else who needs to constantly type a cedilla c.

## Why do I need this?

The traditional Microsoft "US International" keyboard generates accented
characters by sequences of accent+letter, making text typing easy and familiar
for latin language users. This behavior was translated into X, and then into the
earlier versions of Gnome.

Eventually, most countries defined their own keyboard layouts and Gnome added
full support for those. Unfortunately, at some point during this time, the Gnome
project decided that '+c (accent+c) should generate an accented c instead of a
cedilla c, breaking the widely used US-Intl layout in Gnome for many users.

This move generated substantial frustration, and
[many](https://bugs.launchpad.net/ubuntu/+source/ibus/+bug/518056)
[bugs](http://askubuntu.com/questions/363115/how-to-type-latin-small-letter-c-with-cedilla)
[have](https://ask.fedoraproject.org/en/question/28468/problems-with-letter-c-in-us-international-keyboard-fedora-19/)
[been](http://ubuntuforums.org/showthread.php?t=1851918)
[reported](http://blog.klauskiwi.com/cedilla-c-symbol-using-american-keyboards-in-linux/)
on this topic, without a clear and concise solution. This behavior also causes
confusion when migrating users from other operating systems, and makes Linux
adoption more difficult for those who need to use cedilla-c regularly.

## How do I use this?

At the shell prompt, type:

```bash
wget -q https://raw.githubusercontent.com/lima195/gnome-cedilla-fix/refs/heads/master/fix-cedilla -O fix-cedilla
chmod 755 fix-cedilla
./fix-cedilla
```

To activate the changes, log out and re-login. This is usually enough. If you
still see the wrong results after the logout/login procedure, reboot your
computer.

## Uninstallation

To uninstall, just run:

```
rm ${HOME}/.XCompose
```

Again, you will need to log out and re-login for changes to take effect.

## How does it work?

The script copies your system "Compose" file into `~/.XCompose` (your personal
compose file), translating every occurrence of an accented-c (ć) into a cedilla
c (ç). This should satisfy non-Gnome programs.

## Compatibility

I've tested this with a few versions of Debian, Ubuntu, Mint Linux, and Fedora
with success. Please let me know about success and failure stories in other
versions of Linux.

Pull Requests (PRs) with fixes and updates are always welcome.

# You may also like

You may also like these other (unrelated) repos from the same author:

* [coolsites](https://github.com/marcopaganini/coolsites): A collection of cool, useful, and interesting sites around the Internet. There's something for everyone here.
* [termschool-vim-theme](https://github.com/marcopaganini/termschool-vim-theme): A pleasant green/gray dark theme for vim and gvim (requires 256 color terminals or gvim).
* [mojave-vim-theme](https://github.com/marcopaganini/mojave-vim-theme): A warm dark theme for Vim and Gvim.
* [netbackup](https://github.com/marcopaganini/netbackup): A backup frontend for many common backup tools (rsync, rdiff-backup, etc). Simplify your backups using similar configuration files, generate log files on common locations, etc.
* [mkvtool](https://github.com/marcopaganini/mkvtool): A "swiss-army knife" tool to manipulate, clean, rename MKV movie files and subtitles.
* [bitrot](https://github.com/marcopaganini/bitrot): A simple tool to detect bitrot (silent media corruption) in your media. Particularly useful for flash drives.
* [quotes exporter](https://github.com/marcopaganini/quotes-exporter): A prometheus financial quotes exporter.
