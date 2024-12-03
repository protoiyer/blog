---
title: 'Setting up my Linux box and Ruby on Rails development environment'
date: Mon, 16 May 2011 09:57:43 +0000
draft: false
tags: ['Programming']
---

### Introduction

As many of you might be aware, I have been a fan of the Ruby language for a few years now, and though I had read a bit about Rails, I started learning and using it on a daily basis only during the past 8 to 10 weeks. Coming to the world of Linux from Windows has been liberating, especially for a keyboard junkie like me. Plus I just love the fact that I can invert the color of any/all window by pressing WindowsKey+N or WindowsKey+M. That is just super awesome!

Of course, coming from the dumbed down Microsoft/Windows world, things haven't been exactly only rosy. There were a few thorns, nothing more irritating than trying to set up the development environment in the same machine again and again. Let me explain.

I started learning Rails on my laptop running Windows Vista. Rails is meant to be run on a Unix based machine (Linux or Mac OS), and it is a real pain in the proverbial to get everything working on Windows, and in fact some of the things just don't work well (spork and autotest, off the top of my head). But still I got things working and used Rails on Vista for a few weeks.

I was sort of sticking to my desktop running Windows XP for all my serious work since Vista was (and is) pretty slow -- it had almost become my wife's movie watching machine!

When I wanted to install Ubuntu 10.10 the first time, I tried my level best to opt for dual booting on my laptop. In spite of my valiant effort to defragment the disk to make space for Ubuntu, the system refused to allocate anything more than 150 MB for another partition. I decided enough is enough, and installed Ubuntu 10.10 aka "Maverick Meerkat" wiping the disk clean and getting rid of Vista.

This was the first time I was ever working on Ubuntu, and so had to spend a lot of time grokking around to get everything setup as I wanted it to be (or as I was used to all these years).

When Ubuntu 11.04 (Natty Narwhal) came out, and I read about the new sleek (and I must add, really helpful for someone like me) Unity interface, I decided to upgrade. Upgrade itself was a breeze, and everything was working and looking great, on the second morning I started noticing the only problem I have had with it -- system freeze.

Due to some reason (that I am not good enough at the moment to identify by myself or rectify) the system would freeze on every boot, and I will have to kill it once, run in recovery mode, kill again, and then start again to get the system to boot! The same was happening even if I tried to work around it by using Hibernate.

Of course, not everyone who has upgraded to Ubuntu 11.04 is facing this issue, but some definitely are, and the freeze happens at different moments for different people. I tried raising it in various forums, but didn't get any solution.

Having spent the last 15 days doing this killing ritual many times a day, I decided once again that enough is enough, and decided to install 10.10 back, which I did. Of course, it had to wipe the system clean and reinstall since it is a downgrade.

So, here I had a blank machine one more time, and this time I decided to jot down the things I had to do to get the machine to a state that I would be happy about. I am a bit finicky about things like colors and fonts. For instance, in my book, the default fonts like Courier New or Monospace or Ubuntu-font are not as great as Google's Droid font or the awesome Consolas/Inconsolata, and I prefer light color text on dark background for coding as well as reading web pages.

So here are the steps I took to reclaim my machine. I will use it as a reference the next time I have to install Linux on any box, and I hope some of the things mentioned here will be useful for you -- for instance, how to maximise the screen estate without upgrading to Unity!



### Basic Machine Setup

**A. Configure gEdit**

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


**B. Configure Nautilus**

```
  View
    Default view Compact
    Arrange Items by Modification Date
    Zoom 50%
    ...
```


**C. Configure Terminal**

  select "Inconsolata 11" as font
  Color: Green on black  


**D. Install Firefox 4**

```
  sudo add-apt-repository ppa:mozillateam/firefox-stable
  sudo apt-get update
  sudo apt-get upgrade
```


**E. Install Chrome Dev Channel**

  <http://www.chromium.org/getting-involved/dev-channel>

  Install Chrome apps

  <http://googlesystem.blogspot.com/2010/07/install-google-web-apps-in-google.html>
  <http://www.readwriteweb.com/archives/weekend_project_install_google_web_apps_in_chrome_or_chromium.php>
  <http://downloadsquad.switched.com/2010/07/06/more-google-chrome-web-apps/>

  Also reinstall "Mail Checker Plus for Google Mail" from <https://chrome.google.com/webstore/detail/gffjhibehnempbkeheiccaincokdjbfe#>



**F. Maximize screen real estate**

  Don't install "window applets" using the first link (though it is fine) below, but do use it to install "Window Picker" and Maximus.
  <http://www.omgubuntu.co.uk/2011/01/maximising-screen-space-in-ubuntu/>

  <http://www.webupd8.org/2010/12/window-applets-0210-released.html>

  To install Window Applets 0.2.10 in Ubuntu, you can use the WebUpd8 PPA:

```
  sudo add-apt-repository ppa:nilarimogard/webupd8
  sudo apt-get update
  sudo apt-get install gnome-window-applets
```

  You might have to run `killall gnome-panel` before you can see "Window Buttons" and "Window Title" in the "Add to Panel" list, as mentioned in the FAQ in this page: <http://gnome-look.org/content/show.php?content=103732>

  Btw, I removed "Window Title" since "Window Picker" since "Window Picker" already shows the window title. I ended up hiding that caption as well since it is sorta redundant.



**G. Install banshee music player (stable)**

  <http://banshee.fm/download/>
```
  sudo add-apt-repository ppa:banshee-team/ppa
  sudo apt-get update
  sudo apt-get install banshee
```



**H. Installing favorite fonts**

  Inconsolata font <http://kevin.vanzonneveld.net/techblog/article/install_the_best_coding_font/>
```
    sudo apt-get install ttf-inconsolata
```

  Droid fonts
```
    sudo apt-get install ttf-droid
```

  I actually had backed up the font folders [.fonts, .fontconfig, both under root (~/)], but forgot about it, and so had to install the above two again.



**I. Apply the favorite fonts everywhere**

Configure gEdit, Terminal, browsers and the system as such to use Droid and Inconsolata fonts. Yeah, I am a bit mad when it comes to fonts and colors used in the IDE.



**J. Install Picasa 3**

  Grab it from <http://picasa.google.com/linux/>



**K. Install aptitude**

  This would come in handy to install stuff that needs aptitude rather than the default apt-get package manager.
```
  sudo apt-get install aptitude
```



**L. Install Wine and Kindle for PC**

  If you are like me, and is a bookworm, you naturally love Kindle [device or app]. Though Amazon and Kindle itself runs on Linux, they don't support Linux when it comes to the Kindle apps. But, fear not. Using Wine, we can install Kindle for PC on our Linux box. Here are a couple of sites explaining how it is done.

Install the Kindle for PC application on your Linux computer: <http://www.fewt.com/2009/11/install-kindle-for-pc-application-on.html>
Installing Kindle for PC on Debian Squeeze: <http://okomestudio.net/biboroku/?p=931>

Though I had installed the latest version of Kindle for PC about 3 months back (as explained in the the first link above), as of today, I am unable to make it work (may be Amazon released a new version that doesn't work with the Wine I have?) and so had to use an old beta version of the Kindle for PC app (as mentioned in the second link). But as they say, something is better than nothing!



**M. Install Pinta (equivalent of `Paint.net`)**

  I am someone who takes a number of screenshots in a month for various things, and so not having the equivalent of Paint is not acceptable. I usually crop the screenshots and so I need a decent editor. Enter Pinta: <http://www.ubuntugeek.com/pinta-paint-net-clone-for-linux.html#more-4476>

```
  sudo add-apt-repository ppa:moonlight-team/pinta
  sudo apt-get update
  sudo aptitude install pinta
```



**N. Configure Reliance NetConnect**

  Unfortunately, my Reliance Netconnect just doesn't work with the out-of-the-box method (of adding a new mobile network connection), and what works is the steps outlined by Harbhag at his blog: [Reliance Netconnect Broadband+ on Ubuntu](https://harbhag.wordpress.com/2010/09/14/reliance-netconnect-broadband-on-ubuntu/)

  May be there are other ways to achieve the same thing, but this works for me, and so that is what I will use in future as well.


**O. Further tips and tricks to customize Ubuntu**
  Refer <http://www.techsupportalert.com/content/ubuntu-tips-and-tricks.htm>



### Developer Tools Setup

**A. Install LAMP**

  <http://tuxtweaks.com/2010/04/installing-lamp-on-ubuntu-10-04-lucid-lynx/> -- I stopped short of installing phpAdmin which is mentioned at the end

  <http://surferzworld.com/2010/10/installing-lamp-linux-apache-mysql-php-server-ubuntu/> -- looks promising, but I didn't follow this



**B. Install gvim**

```
  sudo apt-get install vim vim-gnome
```

  Since I had backed up the vim settings yesterday before reinstalling Ubuntu 10.10, I just had to copy paste the settings back into the root (~/) and gvim was ready to go with all the plugins, themes and fonts that I was using, which was great. The folders/files that I had backed up were:

```
  taglist, .vim-fuf-data, fuzzy_file_finder-1.0.4, .vim, src, VimSettings, .vimfuzzyfinder, .viminfo, .gvimrc, .vimrc
```

  The only thing that I had to install was "exuberant ctags" using `sudo apt-get install exuberant-ctags`.

  I tested to ensure my favorite plugins were working fine: rails-vim, nerd-tree, Bufexplorer etc were working fine. And yes, my favorite themes were also around -- railscasts, obsidian2, and others.

  I will try to post about my vim experiences some day.


++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++


  Note: From here on, the installation process was done based on a bunch of resources:

  Blog post by my good friend and colleague, Apple:

  Installing RoR in Ubuntu: <http://arunsark.wordpress.com/2011/02/25/installing-ror-in-ubuntu/>

  The excellent Ruby on Rails Tutorial book (available online for free):
    <http://ruby.railstutorial.org/ruby-on-rails-tutorial-book#sec:up_and_running>

  The Ruby on Rails Tutorial video on installing Rails in Linux/MacOS/Windows (this bit is free):
    <http://ruby.railstutorial.org/> -- check the section Table of Contents for links to free videos  

  A couple of blogs that I stumbled upon:

  [Ruby On Rails Development On Ubuntu 10.10 With git, vim, and RVM](https://web.archive.org/web/20101203044304/http://appogee.posterous.com/ubuntu-1010-ruby-on-rails-setup)

  [How to install Rails 3.0 and Ruby 1.9.2 on Ubuntu](http://toranbillups.com/blog/archive/2010/09/01/How-to-install-Rails-3.0-and-Ruby-1.9.2-on-Ubuntu)


++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++



**C. Install git**

```
  sudo apt-get install git-core
```


**D. Set up tab completion for git**

  Trying to set up tab completion for git branches turned out to be a bit of a pain since the version of git installed by the above command apparently doesn't have the file "contrib/completion/git-completion.bash" that is the source for tab completion. I had to download the latest git source (tar ball) from <http://git-scm.com/download>, extract it, and use the file that was available inside the contrib/completion folder (your version number might be different based on when you are downloading):

This section follows what is mentioned in the Ruby on Rails Tutorial free video on installing Rails in Linux/MacOS.
Refer <http://ruby.railstutorial.org/bashrc> for the exact contents that goes into the ~/.bashrc file

```
  # navigate to the Downloads folder where the tar file was downloaded
  $ cd Downloads/

  # unzip it
  $ tar jxf git-1.7.5.1.tar.bz2

  # navigate into the git source and copy the git-completion.bash to the root folder
  $ cd git-1.7.5.1/
  $ cp contrib/completion/git-completion.bash ~

  # Open the .bashrc file for editing
  $ gvim ~/.bashrc

  # NOW, Paste the contents from http://ruby.railstutorial.org/bashrc into the file.

  # NEXT, run the following to source the bashrc file.
  $ . ~/.bashrc
```



**E. Install curl**

```
  sudo apt-get install curl
```


**F. Install Ruby Version Manager (RVM)**

  Refer <https://rvm.beginrescueend.com/rvm/install/> and follow along.

  This was a nightmare for me and I had to keep running `source .bash-profile` to ensure rvm was always recognized as a command/function. Of course, I think if you follow one of the sources (instead of trying to follow "the best from all sites") you might not run into this problem.

  In fact, I still need to run `source .bash_profile` every time I start a terminal for the system to recognize rvm and rails as commands/functions.

  Note: Since this is the third or fourth time I am setting this up, I think you are better off refering to one source while installing rvm. This is the first time I tried to act smart (by referring to multiple sources, trying to pull in the best bits about the installation or setup), and promptly, paid the price!

Update: I found out the issue. .bash_profile might be used by some other Linux distributions, but not Ubuntu. For Ubuntu, the proper file is ~/.bashrc [i.e. ".bashrc" under root (~/)]. So, there was nothing much that I had to do except for using .bashrc wherever .bash_profile was being mentioned!

Anyways, I also learnt how to uninstall rvm in the process:

```
gem uninstall rails  # not mandatory, I think; when you remove rvm (next step) this too should vanish

rvm implode
```


**G. Install Ruby**

```
  rvm install 1.9.2
```

  You might have to jump through a few hoops here (to create the gemset, the default gemset and so on. Please refer the Ruby on Rails Tutorial or the blog posts mentioned above).    

  At the end of it, your system should be using 1.9.2 against a gemset you created. At end of it all, I ran the command:

```
  rvm --default use 1.9.2@rails3
```

  which means I am on ruby 1.9.2 and I have created a gemset rails3 for me to play with.



**H. Install Rails 3.0.7 (the latest as of now).**

```
  gem install rails --version 3.0.7
```


**I. Install the databases**

  If you had followed along from the top (referring to the different sources, you would have already installed both mysql and sqlite3). If you haven't, please refer the "Databases" step of [Ruby on Rails Development on Ubuntu 10.10 with Git, Vim, and RVM](https://web.archive.org/web/20101203044304/http://appogee.posterous.com/ubuntu-1010-ruby-on-rails-setup).

  For me, what is left to do is to install postgresql

```
  # Install postgresql and deps
  sudo apt-get install postgresql libpq-dev
  gem install pg
```


**J. Install "Open Terminal [Command-Prompt] Here"**

  This allows you to open a terminal from any path in the file manager Nautilus. From: [How to open a menu with 'Open Terminal Here' in Ubuntu 10.04 by left clicking desktop, or inside folder?](https://superuser.com/q/166407/44785)

```
  sudo apt-get install nautilus-open-terminal
```


To complete the set up of Rails development environment along with the required test setup and deployment (using heroku) environment, refer to the excellent Ruby on Rails Tutorial, in particular chapters 1 and 3. Chapter 2 is about using scaffold to create a sample app, and doesn't add any value towards our current goal: setting up the environments.

Of course, my ideas about what constitutes my preferred configuration is bound to change over time, and so would the tools required to do the job. If I come across something great, I will try to update this post with that info.

Thanks for reading and I hope at least some of it would have been useful for you.


---
Update: Thu, 19-May-11: Updated the section "F. Install Ruby Version Manager (RVM)" under "Developer Tools Setup" based on later findings, and also added sections to install Pinta, Open Terminal Here, Picasa 3, Kindle for PC, and a link to 'how to customize Ubuntu further'.

Update: Thu, 26-May-11: Inserted a new section "N. Configure Reliance NetConnect" under "Basic Machine Set Up"
