---
layout: post
title: How to Fix "Linux Failure to Download extra data files for ttf-mscorefonts-installer" error
category: General
tags: [general]
---
<p>Hi <br>
Using Linux for a while , one of the errors I often come across with is downloading problem for certain add-ons.
</p>

<br>

<p> If you get the following error: <br>
Failure to download extra data files

The following packages requested additional data downloads after package installation, but the data could not be downloaded or could not be processed.

ttf-mscorefonts-installer

The download will be attempted again later, or you can try the download again now. Running this command requires an active Internet connection. <p>

<p>So this certain  packet  actually stands for Microsoft's font files freely avaible from the Microsoft for you to use and download
without sharing with any 3rd party or individual.Therefore, there is a probable connection problem that you must have had when you attempted to download it.</p>

<p>To fix it: <br>

sudo apt-get remove --purge ttf-mscorefonts-installer
sudo apt-get install ubuntu-restricted-extras

use these two lines of codes respectively and you are ready to go ! <p>

<p>Sincerely sas, 04.02.2017</p>


