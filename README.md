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

We're gonna log on a virtual machine using SSH, so we need a SSH enabled terminal. For that, let's use Cygwin.

    choco install cyg-get


Installing Cygwin packages
---

There'are two Cygwin packages we need to install, `openssh`, because Cygwin doesn't have SSH support by default, and `rsync` so Vagrant can use it to synchronize files between the host and the guest machines.

On PowerShell, running as an administrator, let's run these commands:

    cyg-get openssh
    cyg-get rsync
    
Cloning rethinkdb-vagrant
---

Open your Cygwin home directory. It should be something like this: `C:\tools\cygwin\home\[YOUR_USER]`. Inside this folder, clone rethyinkdb-vagrant (make sure you have git installed):

    git clone https://github.com/gearz-lab/rethinkdb-vagrant.git
    
Now you should have a directory like this: `C:\tools\cygwin\home\[YOUR_USER]\rethinkdb-vagrant`.

Starting Vagrant
---

Open Cygwin as an administrator. You should be in the `~` directory (`C:\tools\cygwin\home\[YOUR_USER]`). Type `cd rethinkdb-vagrant`, an then `vagrant up`. For getting access to the machine, type `vagrant ssh`.

Accessing RethinkDB.

For accessing the web administration tool: http://localhost:8080. If you are accessing it from a client app, the port is 28015



