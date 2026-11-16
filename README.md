> [!NOTE]
> **This is an unofficial fork of AutoKey for Wayland that adds KDE Plasma
> support without root.** The AutoKey for Wayland developer doesn't support it,
> so please don't send them reports about it. The official project is
> [dlk3/autokey-wayland](https://github.com/dlk3/autokey-wayland).

# AutoKey for Wayland, with KDE Plasma support (unofficial)

The official AutoKey for Wayland reads and types keys through the kernel's
uinput device, which needs udev rules, the `input` group and a reboot. On
**KDE Plasma 6 (Wayland)** this fork can get the keys from KDE's window manager
(KWin) instead, so none of that is needed.

| Change | Works on |
|---|---|
| Hotkeys, abbreviations and typing through KWin, with no root, uinput or `input` group | KDE Plasma 6 (Wayland) |
| Abbreviations that contain characters typed with Shift or AltGr, such as `:`, now match | Any desktop that uses uinput, and KDE Plasma |

On other desktops, and on KDE when the KWin plugin isn't installed, AutoKey
uses uinput as before.

The KDE support needs two more small programs:

- [autokey-kwin-bridge](https://github.com/SamuelCGilbert/autokey-kwin-bridge), a
  KWin plugin that sends key events and hotkeys to AutoKey
- [kwin-input](https://github.com/SamuelCGilbert/kwin-input), which types for
  AutoKey

Tested on KDE Plasma 6.8 (Wayland) on Ubuntu. It was written with help from an
AI assistant (Claude). It's shared as-is, with no promise of support.

## Install

Follow the official
[install from GitHub](https://autokey-wayland.readthedocs.io/en/latest/github.html)
guide, with two changes:

1. In step 1, clone this fork instead:

   ```bash
   git clone -b wayland https://github.com/SamuelCGilbert/autokey-wayland
   ```

2. On KDE Plasma, skip step 3 (uinput, udev rules, `input` group and reboot).
   Install [autokey-kwin-bridge](https://github.com/SamuelCGilbert/autokey-kwin-bridge#build)
   and [kwin-input](https://github.com/SamuelCGilbert/kwin-input#build-and-install)
   instead, then log out and back in.

## Updates

This fork is updated with new AutoKey for Wayland releases from time to time.
The changes are on the `wayland` branch; `main` is an unchanged copy of the
official project.

*The original AutoKey for Wayland README follows.*

---

# AutoKey for Wayland (and X11, too)

The AutoKey for Wayland project is a fork of the
[AutoKey](https://github.com/autokey/autokey) project. It builds on work done in
the “develop” branch of that project to create the facilities that AutoKey needs
to operate in a Wayland environment. An “official” version of AutoKey based on
that work has not yet been released.

## Project Documentation

The [project documentation](https://autokey-wayland.readthedocs.io/en/latest/) 
web site includes information on:

* [What Works & What Does Not](https://autokey-wayland.readthedocs.io/en/latest/whatworks.html)
* [Installation Instructions](https://autokey-wayland.readthedocs.io/en/latest/installation.html)

Ubuntu/Debian and Fedora installation packages are available.  The AutoKey for 
Wayland code may also be cloned from GitHub, configured, and run manually on any
system.

## Support

Read the 
[Troubleshooting](https://autokey-wayland.readthedocs.io/en/latest/troubleshoot.html) 
section of the documentation website.

The [official AutoKey wiki](http://github.com/autokey/autokey/wiki) contains a 
lot of useful information about how to use AutoKey, including many example 
scripts and the like.  Make use of it.

You may post questions or bug reports to this project's 
[Issues](https://github.com/dlk3/autokey-wayland/issues) tracker, and I will do 
my best to address them.  Problem reports should always include a console log that
captures the debug output from AutoKey when the problem occurs.  See the 
[issue reporting](https://autokey-wayland.readthedocs.io/en/latest/troubleshoot/issues.html)
section of the documentation for guidance.

## Project Branches

* [main](https://github.com/dlk3/autokey-wayland/tree/main) - the current release.
* [develop](https://github.com/dlk3/autokey-wayland/tree/develop) - developing the next release.

See, also, [Releases](https://github.com/dlk3/autokey-wayland/releases).
