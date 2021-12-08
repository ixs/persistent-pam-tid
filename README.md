# persistent-pam-tid (not so persistent)

macOS automatically resets `/etc/pam.d/sudo` to its default state after each system upgrade. This launchd configuration adds pam_tid.so to `/etc/pam.d/sudo` at startup if not present.

Blog post: [Persistent sudo Touch ID Authentication on macOS](https://birkhoff.me/Persistent-sudo-Touch-ID-Authentication-on-macOS/)

## Installation

```console
sudo curl -o /usr/local/bin/pam-tid-installer https://raw.githubusercontent.com/BirkhoffLee/persistent-pam-tid/main/pam-tid-installer
sudo curl -o /Library/LaunchDaemons/me.birkhoff.persistent_pam_tid.plist https://raw.githubusercontent.com/BirkhoffLee/persistent-pam-tid/main/me.birkhoff.persistent_pam_tid.plist
sudo chmod +x /usr/local/bin/pam-tid-installer
sudo chown root:wheel /Library/LaunchDaemons/me.birkhoff.persistent_pam_tid.plist
sudo launchctl load -w /Library/LaunchDaemons/me.birkhoff.persistent_pam_tid.plist
```

## Uninstalling

```console
sudo rm /usr/local/bin/pam-tid-installer
sudo rm /Library/LaunchDaemons/me.birkhoff.persistent_pam_tid.plist
```

## Disclaimer

Only use codes in this repository if you absolutely understand what it means and what it does. Everything in this project has been tested on my machine and clean macOS virtual machines. I take no responsibility and bear no culpability if anything breaks on your machine after using any piece of code in this repo.

## LICENSE

This project is released under [UNLICENSE](UNLICENSE).
