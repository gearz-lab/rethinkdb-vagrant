# rethinkdb-vagrant

This is a Vagrant configuration for running the latest version of RethinkDB on a virtual 64bit 14.04 Ubuntu machine. You can use this for whatever you want, but this is particularly useful for running RethinkDB on a Windows machine.

# Installing on Windows

I'm going to describe the entire process. If you are already familiar with something, just skip it :)

Throughout this process, we're gonna need to install some applications. Just so it's easier, let's use Chocolatey.

Installing Chocolatey
--

Open Powershell as an administrator and run this command:

    @powershell -NoProfile -ExecutionPolicy Bypass -Command "iex ((new-object net.webclient).DownloadString('https://chocolatey.org/install.ps1'))" && SET PATH=%PATH%;%ALLUSERSPROFILE%\chocolatey\bin
    
... now you should have Chocolatey installed. We're gonna use to install the others.

Installing VirtualBox
---

Vagrant relies on a virtualization application that it calls a "provider". The default one is VirtualBox so let's install it. Run `cmd` as administrator and run this:

    choco install virtualbox
    
Installing Vagrant
---

Let's not forget about Vagrant. Run this as an administrator:

    choco install vagrant
    

    
Installing Cygwin
---

We're gonna log on a virtual machine so we need a SSH enabled terminal. For that, let's use Cygwin.

    choco install Cygwin
    
We also need a package to install some Cygwin extra packages. Let's install cyg-get:

    choco install cyg-get
