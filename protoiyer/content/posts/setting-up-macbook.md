---
title: 'Setting up my Macbook development environment'
date: Tue, 30 October 2018 22:35:20 +0000
draft: false
tags: ['Programming']
---

### Introduction

A blog post after 6 long years. Yay!

Recently I had to setup my personal Macbook and migrate some stuff from the previous machine.

In the past, I had written [more in-depth posts](https://protoiyer.github.io/posts/setting-up-linux-12.04-ror/) about setting up my laptop for programming. What follows is the quick 2018 version for my future reference.

Let us get the ball rolling!


### Basic Machine Setup

**A. IR Black theme**

Get [IR Black theme](https://osxdaily.com/2012/02/24/ir_black-theme-add-colors-easily-to-the-terminal-in-mac-os-x/) for the Terminal. The link in that article to download the theme file doesn't work anymore, and so we can [Google](https://www.google.com/search?q=mac+ir_black+theme+for+terminal) to locate it.

- Set IR Black theme as the default (use the Default button at the bottom of the Terminal Preferences window).
- Adjust the font (Menlo Regular 14pt),
- Remove 'Use bold fonts'
- Cursor underline and blink
- Adjust Window size and rows (120 * 55 for 14", 120 * 58 for 15", 120 * 65 for MBP 16")
- Keyboard check Use Option as Meta Key



**B.Apple Command Line Tools**

Install the Apple Command Line Tools

```
xcode-select --install
```


**C. Homebrew**

Install homebrew

```
/usr/bin/ruby -e "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/master/install)"
```

Verify the brew installation worked by running

```
brew doctor
```

If it suggests anything, it might be worthwhile to check and act on it.

The apps installed with homebrew should take precedence over those that came by default:

```
echo 'export PATH="/usr/local/bin:$PATH"' >> ~/.bash_profile
```

Install homebrew [cask](https://github.com/Homebrew/homebrew-cask)

```
brew tap homebrew/cask
```

Verify whether the cask is working fine by installing and uninstalling Atom.

```
brew cask install atom
brew cask uninstall atom
```

See whether homebrew needs updates

```
brew update
brew upgrade (if needed)
```



**D. Rectangle**

Install Rectangle for easy split-window management

```
brew install --cask rectangle
```

I especially like to have Command+Shift+M as the keyboard shortcut to fill the screen with the menu bar visible (not the system full screen that hides the menu bar).



**E. Karabiner**

Install Karabiner Elements to easily remap keyboard keys

```
brew cask install karabiner-elements
```

Two essential key remaps I use are (as a vim and tmux user):

```
Caps lock as [left] Ctrl
Right Cmd key as [left] Ctrl
```

On an Apple International English keyboard, I would remap/swap the §/± key (that would be under the Esc key) with the ~/` key.

At this point I would be comfortable using the new laptop - I can resize windows as I please and can press the Ctrl key easily in vim.



**F. Homebrew Packages**

Next up would be the [list of brew packages](https://apple.stackexchange.com/a/101092) or casks to install

Before we get there, we may have to first manually install

```
brew install java
brew cask install adoptopenjdk
brew tap heroku/brew && brew install heroku
```

Verify at this point that java is indeed installed and working properly.

```
java --version
```

---
NOTE: eval "$(/opt/homebrew/bin/brew shellenv)"

==> Caveats
Temurin is the official successor to this software:

```
  brew install --cask temurin
```

adoptopenjdk has been officially discontinued upstream. It may stop working correctly (or at all) in recent versions of macOS.

---

And then use `brew bundle dump` in the source machine, copy the `~/Brewfile` over to the new machine and after ensuring `~/Brewfile` is available in the new machine, execute `brew bundle`.

Oh, I also had to adjust the version number of ghc to 8.4 in the list

And, earlier, we used to use these commands (probably we may still need to):

```
brew install $(< brew_list )
brew cask install $(< brew_cask )
```

At this point, verify whether the basic stuff that should have been installed like tmux, vim, node, irb etc are working fine.

---
NOTE: In case we are setting up for the first time (without any Brewfile to port over), we would have to go through the painfull process of figuring out everything we want installed on the new machine. For instance, your favorite programming languages, their version managers (if any), any other favorite Mac apps you have etc.

---



**G. Ruby and a version manager**

If you use ruby, install ruby and a ruby version manager

To install ruby, I had to first install

```
brew install gnupg gnupg2
```

And also had to do the following:

```
command curl -sSL https://rvm.io/mpapis.asc | gpg --import -
```



**H. SSH keys**

Deal with the [SSH keys](https://confluence.atlassian.com/bitbucket/set-up-an-ssh-key-728138079.html) or [copy](http://osxdaily.com/2012/07/13/move-ssh-keys-from-one-computer-to-another) them over.



**I. Dot files**

Next up would be the turn of [the dot files](https://developer.atlassian.com/blog/2016/02/best-way-to-store-dotfiles-git-bare-repo/). Pull them into the new machine following the instructions.



**J. Hidden files in Finder**

Ensure the finder can display hidden files

```
defaults write com.apple.Finder AppleShowAllFiles true
killall Finder
```

Now open finder again and the hidden files should be visible.



**K. Vim plugin manager**

Now that the dot files are available, install your favorite plugin manager for vim and install the plugins. Or copy the vim stuff over from the old machine to avoid downloading and installing plugins. I also like to copy over viminfo dot file so that my recent vim commands are still available in the new machine. Oh, and also my favorite vim color schemes.



**L. Tmuxinator**

Install tmuxinator

```
gem install tmuxinator
```

Install the plugin tmuxinator needs

```
brew install reattach-to-user-namespace
```



**M. Atom editor**

Install the Atom editor

```
brew cask install atom
```

Hopefully you would have backed-up the settings from the old machine. I used the [Sync Settings for Atom](https://atom.io/packages/sync-settings) package and that worked quite well.



**N. Other apps**

Install the other must-have apps (your list would be different)

```
Adobe Reader
Adobe Digital Editions
Android File Transfer
Balsamiq
Handbrake
HP Easy Scan
Itsycal
mclock
MPlayerX
...
```


**O. Terminal vim app**

One of the things that I didn't like when I started using Mac for the first time in 2014 was the inability to open text-ey files from the Finder in Terminal Vim. So, I am thankful to this [superuser.com thread](https://superuser.com/a/139949/44785). This is what works for me in the new box:

```
on run {input}
	set the_path to POSIX path of input
	-- set cmd to "vim " & quoted form of the_path\
        -- we can do a change directory to make NerdTree happy
	set cmd to "clear;cd `dirname " & the_path & "`;vim " & quoted form of the_path & "; exit"
	tell application "System Events" to set terminalIsRunning to exists application process "Terminal"
	tell application "Terminal"
		activate
		if terminalIsRunning is true then
			do script with command cmd
		else
			do script with command cmd in window 1
		end if
	end tell
end run
```


**P. System preferences**

This is where I would go through the System Preferences and other app preferences, making a bunch of changes to suit my style.

This would include a bunch of system configuration including the following:

System Preferences->Keyboard->Shortcuts, look under the Accessibility section, you need to turn on Invert Colors by checking the box.

I wish there was a way to easily backup these user config settings and recreate in a new box.



**Q. Charger chime sound**

Disable the chime sound when the charger is connected

```
defaults write com.apple.PowerChime ChimeOnAllHardware -bool false;killall PowerChime
```



**R. Seagate NTFS for Mac**

Install NTFS for Mac - [Download](https://www.seagate.com/in/en/support/downloads/item/ntfs-driver-for-mac-os-master-dl/) from the Seagate website



**S. Trackpad settings**

I am very finicky about the Trackpad settings (as you can make out from this section). This is more so since I want minimum interference with keyboard shortcuts and keyboard driven workflow that I generally tend to employ.

a. Go to System Preferences |  Accessibility | Trackpad Options to enable three finger drag.

b. Go to System Preferences | Trackpad to set the following:

```
POINT & CLICK tab
Lookup & data detectors - OFF
Tap to click - ON
Secondary click - Click or tap with two fingers
Click slider on medium
Tracking speed on one below Fast
Force Click and haptic feedback - OFF

SCROLL & ZOOM
Scroll direction: Natural
Zoom in or out: Pinch with two fingers
Smart zoom: Double-tap with fingers
Rotate - Rotate with two fingers

MORE GESTURES
Swipe between pages - OFF
Swipe between full-screen apps - ON
Notification center - ON
Mission Control - OFF
App Expose - OFF
Launchpad - OFF
Show Desktop - ON
```



**T. Install node and npm**

For this just download the installer from the [nodejs website](https://nodejs.org/en/)

Verify that the installation worked:

```
node --version
npm --version
```



**U. Chrome Web Search Navigator**

Install the [Chrome extension Web Search Navigator](https://chrome.google.com/webstore/detail/web-search-navigator/cohamjploocgoejdfanacfgkhjkhdkek) (if it is not already installed)

If Google has [again] pulled down this extension, install it from the [source code](https://github.com/infokiller/google-search-navigator).



**V. Wallpaper, Dock**

Setup the wallpaper to something not too bright (love the default dark mode wallpapers in Mojave or Cataline), and Install Google Featured Photos as Screen Saver
The dock should be small, hidden away to the left. I keep a very small number of items in it, the top three being the Finder, Chrome and Terminal.



**Z. Touchbar config**

I can't generally stand the Touchbar (perhaps shows my age) and so I keep it to a minimum number of fixed controls.

```
Only 'Adjust keyboard brightness in low light' selected
Touch Bar shows 'Expanded Control Strip'
Modifier Keys - Caps lock should be Control
Customize Control strip >
  -- Keyboard brightness down and up
  -- Media play keys (3)
  -- screen brightness down and up
  -- Volume keys (3)
  -- screen lock
```



### Closing Thoughts

I think I will get used to the new laptop pretty quickly (I already am on my way) but I wanted to capture my initial impressions as they are fresh in my mind.

**What I don't like**

1. The trackpad is so big that I keep accidentally brushing my palm and fingers against it very frequently. And so I had to turn off most of the gestures from Trackpad settings' 'More Gestures' tab that opens things like Launchpad, App Expose, Mission Control and so on.


2. Not being able to make the Touchbar display the Function keys always by default (to mimic the old style) is bad. I know that it can be setup to do this one app at a time, but ..
- the app that I use the most during the day - Terminal (and Terminal Vim) cannot be configured for this!
- one has to keep pressing the Fn key or the function keys in the touch bar would disappear to be replaced with the more useful screen brightness and other shiny buttons. #sarcasm #fail

  Maybe there is a way out, but I haven't found it yet.

3. I find that I accidentally even touch the Touchbar when I am trying to use my hands to point to something on the screen (usually when analyzing something on the screen :). The solution was to remove the touchbar keys for adjusting keyboard brightness, mission control, launchpad and so on.

4. The noise coming from the keyboard especially if you type fast (and so carefully typing to avoid/reduce the noise is not an option for you). I need to see whether the noise comes down with usage (as some threads in the interwebs claim) or whether my technique improves (type fast in the new keyboard without making noise :).

5. I have no idea how to use Ctrl+F2 to access the Apple menu on the top left to quickly access the restart or shutdown menus available there using just the keyboard. One way would be to press Cmd+? and then use the right arrow to wrap around to the left and reach the Apple menu

6. The screen brightness (the 50% level, at least to my eyes) seems to have come down and I don't know whether this is a good thing (hence adding it to this list)


**What I do like**

1. Using the Touch ID to quickly unlock the laptop without having to type the password

2. Better speakers in the latest version compared to the previous 2013 model?

3. Lighter laptop than the older model (to be expected, I suppose)


Finally, I concur with the two incisive posts by [Marco Arment](https://twitter.com/marcoarment): [The best laptop ever made](https://marco.org/2017/11/14/best-laptop-ever), and [Fixing the [new] MacBook Pro](https://marco.org/2017/11/24/fixing-the-macbook-pro). Being a user who spends quite a lot of time on the Terminal, I would like to see the physical function keys back with the Touch ID sensor. Oh, and a better keyboard (or at least one that makes less noise).


**Reference**

1. [macOS Dev Setup](https://github.com/nicolashery/mac-dev-setup#mac-os-x-dev-setup) by Nicolas Hery


2. [How to Set up an Apple Mac for Software Development](http://www.stuartellis.name/articles/mac-setup/) by Stuart Ellis


3. [Dotfiles: Best way to store in a bare git repository](https://developer.atlassian.com/blog/2016/02/best-way-to-store-dotfiles-git-bare-repo/) by Nicola Paolucci on Atlassian Git Tutorial site


---

**Revision History**

Update# 1 - Sun, 20-Sep-20: Expanded or added sections on IR Black theme, Homebrew cask, Ruby, Keyboard shortcuts, Trackpad settings

Update# 2 - Fri, 28-Jul-23: Added the section about Temurin
