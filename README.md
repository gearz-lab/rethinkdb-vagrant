# rethinkdb-vagrant

This is a Vagrant configuration for running the latest version of RethinkDB on a virtual 64bit 14.04 Ubuntu machine. You can use this for whatever you want, but this is particularly useful for running RethinkDB on a Windows machine.

# Installing on Windows

I'm going to describe the entire process. If you are already familiar with something, just skip it :)

Throughout this process, we're gonna need to install some applications. Just so it's easier, let's use Chocolatey.

Installing Chocolatey
--

Open Powershell as an administrator and run this command:

    iex ((new-object net.webclient).DownloadString('https://chocolatey.org/install.ps1'))
    
... now you should have Chocolatey installed. We're gonna use to install the others.

Installing Vagrant
---

Run this as an administrator:

    choco install vagrant -y
    
Installing VirtualBox
---

Vagrant relies on a virtualization application that it calls a "provider". The default one is VirtualBox so let's install it. Run `cmd` as administrator and run this:

    choco install virtualbox -y

Now you should be able to run the `vboxmanage` command. If it doesn't work, make sure `C:\Program Files\Oracle\VirtualBox` is in your PATH.

Installing Cygwin
---

We're gonna log on a virtual machine using SSH, so we need a SSH enabled terminal. For that, let's use Cygwin.

    choco install cyg-get -y


Installing Cygwin packages
---

There'are two Cygwin packages we need to install, `openssh`, because Cygwin doesn't have SSH support by default, and `rsync` so Vagrant can use it to synchronize files between the host and the guest machines.

On PowerShell, running as an administrator, let's run these commands:

    cyg-get openssh
    cyg-get rsync
    
Cloning rethinkdb-vagrant
---

Open the `Cygwin64 Terminal`. You should now be in your Cygwin home folder, which should look like `C:\tools\cygwin\home\[YOUR_USER]`.

Make sure you have git installed. If you don't just `choco install git -y`. Now, clone `rethyinkdb-vagrant`:

    git clone https://github.com/gearz-lab/rethinkdb-vagrant.git
    
Now you should have a directory like this: `C:\tools\cygwin\home\[YOUR_USER]\rethinkdb-vagrant`.

Starting Vagrant and useful commands
---

From inside the `Cygwin64 Terminal` home directory (described in the last step), type `cd rethinkdb-vagrant`, now, any Vagrant commands will target `cd rethinkdb-vagrant`.

 - To setup and boot the machine: `vagrant up` (After this, RethinkDB is available, see next step).
 - To access the machine's terminal: `vagrant ssh`.
 - To destroy the machine (every RethinkDB data will be lost): `vagrant destroy`.
 - To suspend the machine: `vagrant suspend`.
 - To resume a suspended machine: `vagrant resume`.

Accessing RethinkDB.
---

Make sure you have `vagrant up` from the last step. Now:

 - For accessing the web administration tool: [http://localhost:8080](http://localhost:8080).
 - For accessing RethinkDB from a client app, the port is 28015.



