---
layout: post
title: Installing Gromacs on Windows subsystem for Linux.
date: 2023-04-26 21:27:00
description:
tags: coding, chemistry
categories: coding, chemistry
---

To install Gromacs on Windows, we first need to install the Windows subsystem for Linux. It is as easy as writing the following in the Windows Powershell app: 
 


{% highlight python %} 
wsl --install
{% endhighlight %}

Restart your computer and then open Ubuntu. Make a username and a password.

Then you can write the following commands one at a time:

You can verify that the installation was successful using:
{% highlight python %} 
sudo apt-get update
sudo apt-get upgrade
sudo apt-get install cmake
cmake --version
sudo apt-get install gcc
sudo apt-get install build-essential
sudo apt-get install libfftw3-dev
mkdir gromacs/
cd gromacs/
wget ftp://ftp.gromacs.org/gromacs/gromacs-2023.1.tar.gz
tar xfz gromacs-2023.1.tar.gz
cd gromacs-2023.1
mkdir build
cd build
cmake .. -DGMX_BUILD_OWN_FFTW=ON -DREGRESSIONTEST_DOWNLOAD=ON
make
make check
sudo make install
source /usr/local/gromacs/bin/GMXRC
{% endhighlight %}

To verify if the installation worked as expected, you can write the following code:

{% highlight python %} 
gmx -version
{% endhighlight %}

That's it! You are now ready to use Gromacs on Windows! 
