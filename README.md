# CCExtractor-Distrobox

A quick guide to setup and use CCExtractor (&amp; GUI) through Distrobox

---

This guide is intended to give people an alternative way to install CCExtractor GUI for computers that doesn't use system level programs (es.: Fedora Atomic, Universal Blue, etc.) and integrating it with the host system for a beautiful user experience

# Contents

1. [Requirements](#requirements)
  
2. [Organize your Host](#organize-your-host)
  
3. [Distrobox Setup](#distrobox-setup)
  
4. [Downloading CCExtractor](#downloading-ccextractor)
  
5. [Downloading the GUI](#downloading-the-gui)
  
6. [The Script](#the-script)
  
7. [The Menu Icon](#the-menu-icon)
  
8. [Here you go!](#here-you-go)
  

# Requirements

- Distrobox [installed](https://distrobox.it/#distrobox)
  
- Internet connection (for downloading the container image and CCExtractor)
  

# Organize your host

The first thing we have to do is to setup our machine to accept our configurations:

Create a folder for the home directory of the ubuntu container (Mine is situated in /Distrobox/ubuntu-ccextractor).

# Distrobox Setup

Now we can create an ubuntu container (I just used ubuntu, you can use whatever you like, but it must have ccextractor in it's repository)

Open the Terminal and paste this command:

```bash
distrobox create -i docker.io/library/ubuntu:22.04 -n ubuntu-ccextractor -H /home/USERNAME/Distrobox/ubuntu-ccextractor/ --hostname uccex --unshare-all
```

Change USERNAME with your username and the path to the folder we have created previously.

> If you are not confortable with the Terminal you can use Boxbuddy as Distrobox UI, but if you use the flatpak version you have to do [this](https://www.dvlv.co.uk/BoxBuddyRS/tips) to change the home folder through the GUI.

# Downloading CCExtractor

It's time to open the container we have created, it will take several minutes, it's the first time we open it and it has to install the system and setup (automatically) few things.

Now that we have the terminal ready we can install CCExtractor:

```bash
sudo apt install ccextractor
```

> At this point we already can use ccextractor via the Terminal, but if you want the nice GUI continue reading ;)

# Downloading the GUI

We can now proceed downloading the files to use the CCExtractor GUI -> [Link](https://github.com/CCExtractor/ccextractorfluttergui/releases)

We have to extract the archive we downloaded and put the extracted folder inside the home folder of our container.

> Now we can open the container -> start ccxgui(automatically will start ccextractor) and we can use the GUI to extract the subtitles of our files

# The Script

I have crated a script to automate all the process of opening the terminal, container, and execute the program, just download the [zip]() and put the CCExtractor.sh file inside the GUI folder.

# The Menu Icon

To make all more beautiful i created the CCExtractor.desktop file

> This type of files are the menu icons you see on your Application menu

1. Download the [file]()
  
2. Download the [image](https://ccextractor.org/images/ccx.svg) (from the official website)
  
3. [Convert](https://cloudconvert.com/svg-to-png) the image in PNG
  

And put the image in `/home/USERNAME/CONTAINER-HOME/GUI-FOLDER/CCExtractor/`

Now with the Script we

1. Open the .sh file with a text editor
  
2. Modify the lines with your values
  

```
Exec=/home/USERNAME/CONTAINER-HOME/GUI-FOLDER/CCExtractor.sh
Icon=/home/USERNAME/CONTAINER-HOME/GUI-FOLDER/CCExtractor/ccx.png
```

And put the .desktop in `/home/USERNAME/.local/share/applications/`

# Here you go!

Now we have a desktop icon that will

1. open distrobox
  
2. open our linux container
  
3. start CCExtractor GUI
  

And when we have finished if we close the GUI everything will close!
