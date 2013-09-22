# Getting Started for Development

Install `virtualbox`, `vagrant` and `vbguest` (a vagrant plugin to keep the virtualbox guest additions in sync), `librarian-chef`

## VirtualBox

I've tried **v4.2.10**

### Ubuntu

-   You can try your luck with the `aptitude` package `sudo apt-get install virtualbox`

### General

Try looking [**here**] [virtualbox-downloads].

## Vagrant

I've tested this with `vagrant` **v1.3.1**

For me the `vagrant` package on `aptitude` was too old so I just got the `.deb` 
from [**here**] [vagrant-downloads] (**Windows/Mac** users should go there too).

## VBGuest

I've tested **v0.9.0**

Install this with `gem`, `sudo gem install vagrant-vbguest`

Install the `ruby` environment if you dont have `gem` (see [**here**] [ruby-downloads]).

## Librarian-Chef

This is a dependency manager for Chef cookbooks.

I've tested **v0.0.1**

This is also a ruby gem, so install it with `sudo gem install librarian-chef`

# Downloading the Cookbooks

Instead of committing all the cookbooks to the repository in the `cookbooks` dir, `librarian-chef` parses the `Cheffile` and manages that directory,
the third-party cookbooks and their dependencies.

Run `librarian-chef install` in the root dir of the chef-repo to generate the `cookbooks` dir.

Any cookbooks you wish to add specifically for the project can go in `site-cookbooks`.

# Starting/Stopping the virtual machine


-   `vagrant up` from within the repo directory will spin up a new instance of a VM or startup a halted instance
-   `vagrant halt` will "turn off" your running VM instance without cleaning it up
-   `vagrant destory` will shutdown your running instance if it is running and then clean it up freeing up your space
-   `vagrant suspend` will suspend you running instance
-   `vagrant resume` will resume a suspended instance

[virtualbox-downloads]: https://www.virtualbox.org/wiki/Downloads "VirtualBox Downloads"
[vagrant-downloads]: http://downloads.vagrantup.com/ "Vagrant Downloads"
[ruby-downloads]: https://www.ruby-lang.org/en/downloads/ "Ruby Downloads"
