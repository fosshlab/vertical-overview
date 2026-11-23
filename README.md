# Vertical Overview
> **This is the maintained fork of [RensAlthuis/vertical-overview](https://github.com/RensAlthuis/vertical-overview)**, kept by the [FOSSH Lab](https://github.com/fosshlab) (Free Software and Hardware Lab). In [#128](https://github.com/RensAlthuis/vertical-overview/issues/128) the original author announced that the extension is no longer maintained and offered to hand it over; we have offered to take it on there. All credit for the extension goes to Rens Althuis and its contributors.
>
> Supported GNOME Shell versions: **42 and 43**. Porting to GNOME 45+ is planned.
>
> Issues and pull requests are welcome here: https://github.com/fosshlab/vertical-overview/issues

## Changes in this fork

### v11
- Workspace thumbnails come back after monitors are disconnected and reconnected (docking/undocking, monitors waking up). Previously they disappeared until the extension was reloaded. (upstream PR [#133](https://github.com/RensAlthuis/vertical-overview/pull/133))
- Guards against an empty workspace list while the overview is torn down.
- Includes the upstream fix for `connectObject()`/`disconnectObject()` ([#116](https://github.com/RensAlthuis/vertical-overview/pull/116)), which was never released on extensions.gnome.org.
- Debug logging turned off by default.

## Description
Gnome has had vertically stacked workspaces for a long time. The Gnome 40 update unfortunately made the switch to a horizontal layout. A choice that many Gnome users disagree with. This extension Aims to replace the new Gnome overview with something that resembles the old style. 


## Preview image
![vertical-overview](https://user-images.githubusercontent.com/12956267/116825963-f0977f00-ab91-11eb-953a-ea891389ddf9.gif)

## Installation:
The version on [Gnome Extensions](https://extensions.gnome.org/extension/4144/vertical-overview/) is the original v10, without the fixes above.

To install this fork, download the zip from the [latest release](https://github.com/fosshlab/vertical-overview/releases/latest) and run:
```
gnome-extensions install --force vertical-overview@RensAlthuis.github.com.zip
```

Or build it from source:
```
git clone https://github.com/fosshlab/vertical-overview.git
cd vertical-overview
make
make install
```

If you use X11, reload the server (press `Alt-F2` and type `r`).
If you use Wayland, log out and log in.
You can detect your Windowing System in Settings → About.

Then enable the extension in "Extensions" application or via command:

```
gnome-extensions enable vertical-overview@RensAlthuis.github.com
```

## FAQ
#### **How do I get back `Super + Page Up/Down` to switch workspaces?**

@romgrk and @m2-farzan have got you covered Until I get around to adding this:
https://github.com/RensAlthuis/vertical-overview/issues/7#issuecomment-816054137



## Donations
> **Note (FOSSH Lab fork):** the donation button below goes to Rens Althuis, the original author, as a thanks for creating this extension. It does not fund the maintenance of this fork. The text below is the original author's.

I never expected this to be something I have to consider. I really don't expect anyone to donate, nor do I want anyone to feel obligated to do so. I do this because I enjoy it and will for sure keeping working on it as long as I can. However multiple people have asked me to make a donation button, so here it is. If you are considering donating, Thank you so much! I really appreciate it.

[![Donate](https://www.paypalobjects.com/en_US/i/btn/btn_donate_LG.gif)](https://www.paypal.com/donate?hosted_button_id=8JSADCLQR58KJ)
