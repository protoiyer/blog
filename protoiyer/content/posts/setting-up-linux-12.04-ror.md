---
title: 'Setting up my Linux box and Ruby on Rails - Ubuntu 12.04 Edition'
date: Wed, 02 May 2012 14:35:16 +0000
draft: false
tags: ['Programming']
---

### Introduction

About a year ago, I had [posted in depth](https://protoiyer.github.io/posts/setting-up-linux-11.04-ror/) about my love for Ruby, and how I set up my Linux box on Ubuntu 10.10, including how to set up Ruby on Rails in that environment.

Well the time has come for an update for [Ubuntu](https://ubuntu.com/) [12.04 LTS](http://releases.ubuntu.com/precise/) that came out during the last week of April.

Since I had written that [previous post](https://protoiyer.github.io/posts/setting-up-linux-11.04-ror/) in such detail, I will just jot down the steps in this one. This is more for my reference, but may be it will be of use to someone as well. Also, that post came in quite handy during the current setup and so I hope I would refer back to this one as well in future.

I was on Ubuntu 10.10, [whose support came to an end](https://www.omgubuntu.co.uk/2012/04/so-long-maverick-meerkat) during April and I was looking forward to the final release version of 12.04 ever since.

Now, there were only two ways to upgrade – from 10.10 to 11.04, then to 11.10, and finally to 12.04. Or, take backups, take a deep breath, and wipe your disk clean and install 12.04. I chose the later path since the former sounded a terrible idea. Also, interestingly had I been on 10.10 (another LTS version), I could have directly upgraded to 12.04 (which is again an LTS version). So, a good lesson learned there – I will think twice before upgrading to non-LTS versions from here on.

So, here I had a blank machine one more time, and this time too I decided to jot down the things I had to do to get the machine to a state that I would be happy about. I am a bit finicky about things like colors and fonts.

Compared to the 10.10 days, there are some changes - some of the apps now come pre-installed (Firefox 12.0) or is no longer supported on Linux (Picasa)

So, once the OS is installed, here are the things I did:



### Basic Machine Set Up

**A. Installing my favorite fonts**

[Inconsolata](https://web.archive.org/web/20170105005034/http://kvz.io/blog/2009/05/25/install-the-best-coding-font)

```
  sudo apt-get install ttf-inconsolata
```

[Inconsolata-dz](https://nodnod.net/posts/inconsolata-dz/), an even better looking Inconsolata

[Inconsolata-g](https://leonardo-m.livejournal.com/77079.html), another derivative of Inconsolata though I prefer the dz version more.

Droid family of fonts, designed by Google for Android phones

```
  sudo apt-get install ttf-droid
```

[Meslo](http://mir.aculo.us/2010/10/12/the-long-search-for-a-terminal-font-is-over/)

Another brilliant monospace font that has caught my attention off late is [Meslo](http://mir.aculo.us/2010/10/12/the-long-search-for-a-terminal-font-is-over/) (based on the Menlo font that the latest versions of Mac use), created by Andre Berg. The beauty of these fonts (and of course of the original Mac Monaco) is that they are very legible at small font sizes. Also, it is more compact (width-wise) at the same point size compared to say, Inconsolata. I use Meslo Medium at 9 points these days. You can download it from the [Meslo github page](https://github.com/andreberg/Meslo-Font/downloads). I haven’t changed the references in this post from Inconsolata to Meslo, however.



**B. Configure gEdit**

```
enable
  View
    Display line numbers
  Editor
    Tab Stops
      Tab width: 2
      Insert spaces instead of tabs
    Automatic indentation
      Enable automatic indentation
  Font
    Remove "Use the system fixed width font"
    select "Inconsolata 11" as font
  Color Scheme
    Oblivion
  ... # and so on
```



**C. Configure Nautilus**

```
View
  Default view List
  Arrange Items by Modification Date
  Zoom 50%
  ...
```



**D. Configure Terminal**

```
General tab
"Inconsolata 11" as font
Color: White on black  
```



**E. Install [Chrome Dev Channel](https://www.chromium.org/getting-involved/dev-channel/)**

Thankfully Chrome remembers all my settings and plugins and so this was pretty hassle free. The only setting I remembered doing was to set the font to Droid.

Of course, Chrome doesn’t remember any userscripts that you installed, and so I had to reinsall the following userscripts:

[Google Reader - Even More Compact Design (Nov 2011)](https://web.archive.org/web/20131108043128/https://userscripts.org/scripts/show/116888)
[O’Reilly Safari Minimalist Tweaked](https://web.archive.org/web/20131111095519/http://userscripts.org/scripts/show/76653)
[Resurrect Google Cache & Related links](https://web.archive.org/web/20131110215037/https://userscripts.org/scripts/show/114455)
[Google Plus Right Side Bar Remover](https://web.archive.org/web/20121206185536/http://userscripts.org/scripts/show/106671)



**F. Install aptitude**

This would come in handy to install stuff that needs aptitude rather than the default apt-get package manager.

```
sudo apt-get install aptitude
```



**G. Install Pinta (equivalent of Paint.net)**
I am someone who takes a number of screenshots in a month for various things, and so not having the equivalent of Paint.net is not acceptable. I usually crop the screenshots and so I need a decent, basic editor. Enter [Pinta](https://www.ubuntugeek.com/pinta-paint-net-clone-for-linux.html).

```
sudo add-apt-repository ppa:pinta-maintainers/pinta-stable
sudo apt-get update
sudo aptitude install pinta
```



**H. Configure Reliance NetConnect**

Unfortunately, my Reliance Netconnect just doesn’t work with the out-of-the-box method (of adding a new mobile network connection), and what works is the steps outlined by Harbhag at his blog: [Reliance Netconnect Broadband+ on Ubuntu](https://harbhag.wordpress.com/2010/09/14/reliance-netconnect-broadband-on-ubuntu/)



**I. Further tips and tricks to customize Ubuntu**

Refer any of these [awesome](http://www.webupd8.org/2012/04/things-to-tweak-after-installing-ubuntu.html) [resources](https://web.archive.org/web/20160113133412/http://www.tuxgarage.com/2012/04/things-to-do-after-installing-precise.html) or google for more.



**J. Install “Open Terminal [Command-Prompt] Here”**

This allows you to open a terminal from any path in the file manager Nautilus, and for me it is an indispensable tool. From [this SuperUser thread](https://superuser.com/questions/166407/how-to-open-a-menu-with-open-terminal-here-in-ubuntu-10-04-by-left-clicking-de):

```
sudo apt-get install nautilus-open-terminal
```



**K. Install tmux**

[Tmux](https://github.com/tmux/tmux/wiki) is a terminal multiplexer and ensures that every time I open it I have all the windows I need (multiple terminals, rails server, rails console, rails db server and so on) are up and running.

Here are [some](https://www.hawkhost.com/blog/2010/06/28/tmux-the-terminal-multiplexer/) [references](https://thoughtbot.com/blog/tags/tmux) and [a book](https://pragprog.com/titles/bhtmux3/tmux-3/) that would be useful to get started.

```
sudo apt-get install tmux
```

Since the apt-get repository had an old version, I downloaded and compiled the source. But the above should get you started.

Of course, to make it even more easier, I use the [Tmuxinator gem](https://github.com/tmuxinator/tmuxinator) as well:

```
gem install tmuxinator
```



**L. Install the indicator-weather applet**

```
sudo apt-get install indicator-weather
```



**M. Install Ack, which is of course better than grep**

```
sudo apt-get install ack-grep
```



**N. Install Kazam for recoring videos for screencasts.**

```
sudo add-apt-repository ppa:kazam-team/stable-series
sudo apt-get install kazam
```



**O. Install xsane for the scanner**

```
sudo apt-get install xsane
```



**P. Install VLC player**

```
sudo apt-get install vlc vlc-plugin-pulse
```


**Q. Install lo-menubar to make LibreOffice play nicely with Unity**

```
sudo apt-get install lo-menubar
```



**R. Install Nautilus Image converter to have a quick option to resize images from Nautilus**

```
sudo apt-get install nautilus-image-converter
```


**S. Install xclip to use the clipboard from the commandline**

```
sudo apt-get install xclip
```



**T. Install ImageMagick**

```
sudo apt-get install libqt4-dev
sudo apt-get install imagemagick libmagickcore-dev
sudo apt-get install libmagickwand-dev
```



**U. Install Exuberant Ctags (for Vim)**

```
sudo apt-get install exuberant-ctags
```



**V. Install MyUnity to tweak Ubuntu.**

```
sudo apt-get install myunity
```

The best part for me is that I can easily tweak the unity launcher bar from this.



**W. Install Ubuntu Tweak to tweak Ubuntu.**

Can be downloaded from <http://ubuntu-tweak.com/>



**X. Install Compiz Config Settings Manager**

```
sudo apt-get install compizconfig-settings-manager
```

This allows me to continue to use the Super(Windows key)+N combination to invert the monitor colors - an indispensable tool for reading using the browser.



**Y. Install AmbianceOneiric theme**

I prefer the all dark provided by AmbianceOneiric theme compared to light+dark menus of the default theme.

Download from the [github repo](https://github.com/StanAngeloff/AmbianceOneiric).



**Z. Change the keyboard shortcut to open the HUD.**

I find the default mapping of the [left] Alt key to open the [HUD](https://www.youtube.com/watch?v=w_WW-DHqR3c) highly irritating, as whenever I press Alt+tab or Alt+LeftArrow (in the browser to go to the previous page), the system would promptly open the HUD. I have to press Escape to close it and get the focus back on whatever window I wanted to access.

Go to System settings | Keyboard | Shortcuts tab. The entry “Key to show the HUD” should have the shortcut listed as “Alt L”. Click that row and press the right Alt key to get the row to display the new keyboard shortcut as “Alt R”. Peace of mind guaranteed. Of course, I do use HUD a lot, including to shut down the device, but I prefer to pay the extra penalty of clicking the right Alt key to invoke it.



**AA. Remap Caps Lock to act as Control key**

I wasn’t aware till recently that the editors like emacs make heavy use of the hard to reach Control key for virutally every shortcut not because it was designed by people who didn’t care, but because before the advent of x86 hardware, all keyboards had the Caps and Control keys swapped. Which means their decision (taken before the x86 days) to use the Control key makes a lot of sense. Luckily it is [pretty easy to remap the Caps Lock](https://www.emacswiki.org/emacs/MovingTheCtrlKey) to act as the Control key. Though it will take a little while for the change to sink in, after a week or so it would be pretty difficult to live without it!



**AB. Replace gedit with vim as the default editor**

One of the things I missed after upgrading 12.04 was the default availability of vim as an option when you right click a file to choose an application to open it with. Luckily the fix is simple and consists of two steps - (a) create a vim.desktop file to ensure vim is listed as an application when you right click (you would have to use “Open with Other Application” the first time to select vim from the list of available applications, and vim will be listed there only if the vim.desktop file is around) and (b) replace gedit with vim throughout the system as the default editor.

Please refer [these](https://askubuntu.com/questions/97683/how-can-i-change-the-default-text-editor-from-gedit-to-vim/97696#97696) [two](https://askubuntu.com/questions/73203/how-do-i-stop-gedit-from-opening-anything/73210#73210) [AskUbuntu](https://askubuntu.com/) answers for more.



**AC. Disable F1 in terminal vim**

One of the problems I face using vim is that I keep hitting F1 instead of the Esc key, and that means closing the Help window that pops up every now and then. The fix is simple - disable the keyboard shortcut for Help. Refer [this post](https://web.archive.org/web/20150113082159/http://robertmassaioli.wordpress.com/2010/06/13/gnome-terminal-disable-f1-help/) for more.



**AD. Get rid of the envelop icon in the system tray**

For about a year I have been living with the never used envelop icon in the top menu corner. Follow the instructions from [this post](https://web.archive.org/web/20161119080704/http://jonnyholroyd.x10.mx/?p=62) to get rid of it and a bit of unnecessary apps from the system including Empathy and Thunderbird.



**AE. Configure Terminal to always open maximized**

Since I work in terminal vim, it is important that when I press Ctrl+Alt+T, the terminal opens in the maximized state. Follow the instruction [found here](https://askubuntu.com/questions/27826/how-to-configure-my-system-so-that-all-windows-start-maximized/135108) to use Compiz to open all the windows in maximized state.



**AF. Bring back Hibernate**

Hibernate has been disabled by default in 12.04 (since Hibernate was not working consistently across hardware) but we can bring it back easily. Follow the instructions found in [this Ubuntu help post](https://web.archive.org/web/20120722085356/https://help.ubuntu.com/12.04/ubuntu-help/power-hibernate.html).



**AG. Install Opera**

There are some quirky Indian sites that works only with IE. For instance the payment page of Fame Cinemas simply refuses to work in either Chrome or Firefox, but it works in Opera! So having Opera in the system can help you at times. Install Opera following the instructions in [this page](https://www.wikihow.com/Install-Opera-Browser-Through-Terminal-on-Ubuntu).



**AH. Install Skype**

Though I am a huge fan of the simple and elegant Gmail chat, from time to time, I find myself talking to people who prefer to be on Skype. So having Skype on the box is pretty useful. It is better not to install Skype from the official download page and instead use the repos. To install using the repo, follow the instructions [at this page](https://help.ubuntu.com/community/Skype).



### Developer tools Setup


**A. Install LAMP**

Install following instructions at [Installing LAMP on Ubuntu 12.04 Precise Pangolin](https://tuxtweaks.com/2012/04/installing-lamp-on-ubuntu-12-04-precise-pangolin/). Like last time, I stopped short of installing the phpAdmin software that is mentioned at the end of that post.



**B. Install vim**

I have become a big fan of terminal vim over the last year, and this time decided to compile and install vim with ruby support. I followed the [steps outlined in this post](https://kresimirbojcic.com/2011/05/14/installing-command-t-ubunutu-11.04-ruby-1.9.2.html), including installing mercurial to clone the vim source code. Of course I used Ruby 1.9.3 on Ubuntu 12.04, but other than that the steps outlined in that post works. Of course, I still can’t get Command-T to work on my box, and that is something I will have to check one of these days.

I ended up installing version 7.3.509, which was the latest version available while I was installing.

For Vim plugin management, this time I decided to do away with my manual style, and was almost going to use the highly rated [Pathogen](https://github.com/tpope/vim-pathogen) plugin. But googling revelaed an even simpler (dare I say better) way of doing that using [Vundle](https://github.com/VundleVim/Vundle.vim).

For more on Vundle, do read [these](https://www.reddit.com/r/vim/comments/h4jfe/sane_vim_plugin_management_philtex/) [two](https://web.archive.org/web/20160113202752/http://blog.jvc26.org/2012/01/12/vundle-vim-pathogen-improved/) posts. I assure you it is worth your time!

Of course, to install terminal vim using the package manager, use

```
sudo apt-get install vim
```

++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++

Note: From here on, the installation process was done based on a bunch of resources:

[Installing RoR in Ubuntu](http://arunsark.wordpress.com/2011/02/25/installing-ror-in-ubuntu/) by my good friend and colleague, Apple
The excellent and free [Ruby on Rails Tutorial book](http://ruby.railstutorial.org/ruby-on-rails-tutorial-book#sec:up_and_running)
Of course my [previous post](https://protoiyer.github.io/posts/setting-up-linux-11.04-ror/) :)

++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++



**C. Install git**

```
sudo apt-get install git-core
```



**D. Set up tab completion for git**

I had backed up the file “contrib/completion/git-completion.bash” and so this was pretty painless - I just had to copy the file into my home (~) folder.

```
$ cd folder/having/git-completion.bash
$ cp contrib/completion/git-completion.bash ~

# Open the .bashrc file for editing
$ gvim ~/.bashrc

# NOW, Paste the contents from [this Rails tutorial page](http://ruby.railstutorial.org/bashrc) into the file.

# NEXT, run the following to source the bashrc file.
$ . ~/.bashrc
```

If you don’t have that file, you might have to download the latest git source. Please refer my previous installation post for more on this.

Also, if you use bash aliases (for instance, type g instead of git and so on), then the default autocomplete won’t work unless you type “git” in full. This can be pretty irritating if you are like me who use git many times a day and expect “g co”, “g bd” and “g m” to have auto completion available to select the branch. By the way, in case you are wondering, those are the alias shortcuts for checking out an existing branch, deleting a branch and merging a branch respectively.

In order to get bash alias and bash autocomplete to work with each other follow the instructions [found here](https://askubuntu.com/questions/62095/how-to-alias-git-to-g-so-that-bash-completion-rules-are-preserved/62098#62098).



**E. Install curl**

```
sudo apt-get install curl
```



**F. Install Ruby Version Manager (RVM)**

Refer the [RVM installation page](https://rvm.io/rvm/install#ubuntu) and follow along.



**G. Install Ruby**

```
rvm install 1.9.3
```

Create the required [rvm gemsets](https://rvm.io/gemsets) as per your requirement.



**H. Install the latest version of Rails**

```
gem install rails
```

If you run into the strange bundle-install-fails-on-every-gem issue due to handshake problem (Gem::RemoteFetcher::FetchError), please refer either of these [two](https://stackoverflow.com/questions/10329892/bundle-install-causes-gemremotefetcherfetcherror-on-each-gem) [posts](https://web.archive.org/web/20160207090959/http://railsapps.github.io/openssl-certificate-verify-failed.html) for a solution.

To complete the set up of Rails development environment along with the required test setup and deployment (using heroku) environment, refer to the excellent [Ruby on Rails Tutorial](https://www.railstutorial.org/), chapters 1 and 3. Chapter 2 is about using scaffold to create a sample app, and doesn’t add any value towards our current goal: setting up the environments.


**I. Install the databases**

If you had followed along from the top (referring to the different sources, you would have already installed both mysql and sqlite3). If you haven’t, please refer the “Databases” step of [this post](https://web.archive.org/web/20101203044304/http://appogee.posterous.com/ubuntu-1010-ruby-on-rails-setup).

For me, what is left to do is to install postgresql

```
# Install postgresql and deps
sudo apt-get install postgresql libpq-dev
gem install pg
```

Of course, you would then have to then try to log into the postgresql db server, create the required users/roles etc. Refer [this post](https://web.archive.org/web/20161116142346/http://xtremekforever.blogspot.in/2011/05/setup-rails-project-with-postgresql-on.html) to install and set up postgresql.



**J. Install node**

Since the package repository is not kept upto date, it is always better to install node from the source on a Ubuntu box. Refer the excellent gist: [install node and npm without having to sudo](https://gist.github.com/isaacs/579814) for instructions. I prefer [cloning the git repo](https://gist.github.com/isaacs/579814) method, and one can safely ignore line numbers 15-18 that is for installing npm. This is so since npm is bundled along with node that we installed following line numbers 1-14 of that gist.



### Conclusion

My ideas about what constitutes preferred configuration is bound to change over time, and so would the tools required to do the job. If I come across something great, I will try to update this post with that info.

Thanks for reading and I hope at least some of it would have been useful for you.


---

**Revision History**

Update# 1 - Thu, 03-May-12: Cleaned up the code snippets’ layout.

Update# 2 - Mon, 21-May-12: Changed the pinta ppa to point to the correct one, changed reference to the package libmagick to imagemagick, moved items K-Z to the more appropriate top section, added info about AmbianceOneiric theme and changing the HUD keyboard shortcut, added reference to Meslo and mapping the Caps Lock to act as the Control key. Added a note about installing node.js.

Update# 3 - Fri, 25-May-12: Added items AB - AG to further tweak the Ubuntu experience.
