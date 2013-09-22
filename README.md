# Giter8 Chef Repo Template

Based on [**opscode/chef-repo**] [opscode-chefrepo]

## New to Chef?

So am I!

Here are some of the notes I took while setting it up on my system:

-   [**Installing Chef On the Server and Client**] [installing-chef]
-   [**Getting started for Development**] [getting-started-for-development].  How to setup/install `vagrant`, `vbguest` and `librarian-chef`

# Giter8

This template uses [**Giter8**] [giter8] to fill out default values in the cabal project file.

## Installing Giter8

Detailed instructions for installing **Giter8** can be found [**here**] [giter8-install].

But for **UNIX**y systems the following will suffice:

    curl https://raw.github.com/n8han/conscript/master/setup.sh | sh
    ~/bin/cs n8han/giter8
    ~/bin/g8

This will install `cs` and `g8` in `~/bin`.  It would be a good idea to add `~/bin` to your `path`.

## Using Giter8

This template can be downloaded with the command (assuming `~/bin` is added to your path):

    g8 domdere/chef-repo

[giter8]: https://github.com/n8han/giter8 "n8han/giter8 on github.com" 
[giter8-install]: https://github.com/n8han/giter8/blob/master/README.markdown#installation "Installation instructions for Giter8"
[opscode-chefrepo]: https://github.com/opscode/chef-repo.git "opscode/chef-repo on GitHub.com"
[installing-chef]: ./docs/InstallingChef.md "Installing Chef"
[getting-started-for-development]: ./docs/GettingStartedForDevelopment.md "Getting Started For Development"
