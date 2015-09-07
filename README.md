# rethinkdb-vagrant

This is a Vagrant configuration for running the latest version of RethinkDB on a virtual 64bit 14.04 Ubuntu machine. You can use this for whatever you want, but this is particularly useful for running RethinkDB on a Windows machine.

# Installing on Windows

I'm going to describe the entire process. If you are already familiar with something, just skip it :)

Throughout this process, we're gonna need to install some applications. Just so it's easier, let's use Chocolatey.

Installing Chocolatey
--

Open Powershell as an administrator and run this command:

    @powershell -NoProfile -ExecutionPolicy Bypass -Command "iex ((new-object net.webclient).DownloadString('https://chocolatey.org/install.ps1'))" && SET PATH=%PATH%;%ALLUSERSPROFILE%\chocolatey\bin
