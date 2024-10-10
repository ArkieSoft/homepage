+++
title = 'Cosmic Alpha 2 Review'
date = 2024-10-09T12:41:29-07:00
draft = false
author = "Arkannon"
tags = ['Unix', 'Linux', 'Cosmic' ]
+++
![cosmic](/blog/2024/images/cosmic-desktop.png)
Cosmic Alpha 2 is out and it is downright an improvement beyond my expectations. Having tried Alpha 1, I had an idea of what to expect, but out of the problems I have noticed, most have been fixed. I will lay out the issues I found with Alpha 1, and what has changed.

I have it installed on NixOS under the 24.05 branch. I am using [Lily Foster's](https://github.com/lilyinstarlight/nixos-cosmic) module to install it. If you install on different distros or in a different way, your mileage may vary.

# ++First Experience++
{style="color: green"}

I already daily drive the cosmic greeter, and the only things I have to say is that it just works with a few quirks. First of all, if you have a multi-display setup, there is no setting to fix the monitor layout. Fortunately, it is mirrored among all monitors so no matter what, you can get your business done. You can select your DE/WM with the cog button, and it uses the Comic DE wallpaper settings automatically. 

Upon entering the newly update environment, the appearance settings largely stayed the same with one exception. You will notice a lot of icons on the desktop. This is because Cosmic 2 allows, by default, desktop icons now and Steam automatically creates desktop icons. You can simply delete them, or turn this fucntionality off (Like someone using a computer in the Year of our Lord, 2024) in the settings app under Desktop>Appearance. Otherwise it all looks business as usual.


# ++Issues From Alpha 1 and How Have They Changed in Alpha 2++
{style="color: green"}

## Janky Settings App

The settings app is good, but needs optimization. The biggest offender is under "Desktop", the Appearance tab is slow to load and attempts to update settings live with varying results depending on the individual setting. Fonts, secondary colors, and the grouping settings are not live, and will partially freeze the app when selected. Not a big deal as you can quit the app and reopen with the settings applied. Because settings opens back to the section it was at previously, it will take some time to open again. Besides that hiccup, it is overall reliable and I hope this problem gets fixed. 

In Alpha 2, this hasn't changed all that much, but it is nonetheless useable.

![Settings app messing up](/blog/2024/images/cosmic-settings.gif)

## Games on Cosmic are Unstable at Best.

Gaming on an experimental environment is not recommended but I know we all will do it. On Alpha 1, games had a lot of trouble sizing correctly in the WM side of things, tiled or not. When attempting to resize, the game will freeze, crash, or blink a lot as I think it defaulted to native resolution and the game had to change resolution accordinglly (I could be wrong here, please don't skewer me for it). 

In Alpha 2, I am sure this is largely fixed as the option to scale apps works wonders for games. Now, no one is going to tile a game in a weird aspect ratio, but for the space aliens that do, here are some things. When tiled, the game kind of compresses or stretches to fit the WM. This leads to the game looking squished, and the mouse tracking matches the game at it's initial state. Games generally start off maximized (like most gamers prefer) so the mouse tracking works best in that state. I even took the time to torture The Binding of Isaac and Civilization VI with the tiling and they were handled effortlessly by the WM and the only things weird were mentioned above. Overall, a very useable experience.


# ++New and Cool Things in Alpha 2++
{style="color: green"}

## Files

The Cosmic Files app was good in Alpha 1. In Alpha 2, they have only made it better. By default, it automatically accesses mountable hardware (flash drives). It now has a built in archive tool that compresses and extracts quickly and with no fuss. Has good sorting features that come standard in most file managers. There is a keyboard shortcut to add a folder to the sidebar (Ctrl+D), but you can't drag and drop for some reason. It is limited on viewing in terms of resources and I don't know why. To stress test it, I navigated to /nix/store, which has thousands of directories and basically contains my entire OS. This froze the app and it climbed up to 3Gb of memory useage and was probably climbing further. I had to ```pkill Files``` in order to close it out. To be fair, Thunar is also not the fastest when trying out the same directory. Another thing to note is the network drive section looks very intuitive and even contains a reference guide to help you use the varying technologies you might want to connect with. 

![Cosmic Files App](/blog/2024/images/cosmic-files.png)

## UI Grouping Changes

This isn't a problem, per se, but the Cosmic App UI had an old Adwaita feel with how spread out pieces of the app are. This made it feel old. Thankfully, there is now an option to change it to make it all look more compact. You can find it in the Setting app in Desktop>Appearance.


# ++What System76 Doesn't Tell You++
{style="color: green"}
So it was mentioned in the changelog that cursor follows focus and vice versa. For those who are unfamiliar, if you move your cursor to hover over another app, the focus will now automatically shift. There is a thing that is not told, though. If you simply try it out, you will notice the focus seems a little.... slow. Well there is a setting to change that. Apparently, system76 hired a sloth to make this because there is a timed delay before focus is actually shifted. The default is 250 ms. It is definitly noticeable. My recommendation is to bring it down to 100 ms. 

![Cosmic Settings Focus Delay](/blog/2024/images/cosmic-focus-delay.png)

Note: This setting also affects the focus of panel option widgets. This means if it gets too low, it can lose focus of widgets due to the small gap.

![Cosmic ms Testing](/blog/2024/images/ms-tester.gif)


# ++My Wishlist++
{style="color: green"}

I am not making any demands to System76 at this time (that comes later when I get majority ownership /j). I do, however have things I would like to see that aren't exactly missing, but simply might not be a design decision of theirs. I like to make this disctinction as not having what I like doesn't mean it is bad. It just means that it is designed differently for different people. 

## Workspace Options

The current options are workspaces per monitor, or systemwide workspaces. I would like bind a certain workspace to a single monitor and address the monitor via workspace like I can do with i3/Sway and Hyprland. I feel like this is something that can be done with a plugin in the future, and may just not be on the design table for System76. 

## Effects/GIFs For Wallpapers

The wallpaper system is awesome. It just works and is implimented in the Settings app. However, apart from forming a slideshow, there isn't much in the way with transition effects or GIF compatibility. I would like to see this, and can see this being implimented in a later version of Cosmic. As of now, it is going to be, understandibly, low priority.

## Remove Panel For Fullscreening apps

The Cosmic Panel is always visible. It would be nice to have the option to have fullscreen apps like games autohide the panel without making the panel autohide globally.


# ++Do I Recommend it For Everyday Use?++
{style="color: green"}

Short answer, no. Long answer, maybe. If you are the tinkering type in the settings, then it is definitely not for you, but it is definitely very stable which is something that System76 definitly spent a lot of time on before releasing. The DE is still a little quirky and needs some getting used to if you are used to KDE and will feel somewhat similar if you're a GNOME user. I spent an hour tweaking keyboard shortcuts to match my Hyprland config/muscle memory and changing some basic settings like disabling the dock (No hate, just not a fan of docks). 

The Files app, however, I plan on using as a possibly replacement for Thunar. Thunar needs other external applications to impliment certain functions that Files does effortlessly. As for the performance issues when accessing /nix/store/, I feel like that is something that I would use ``` ls | grep``` to navigate through anyways.


