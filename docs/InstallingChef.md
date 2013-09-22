# Installing Chef

I worked from [**this blogpost**] [chef-server-tutorial].

I essentially followed these steps:

## Installing the Server

On the Server machine (obviously):

1.  I went [**here**] [chef-install] to find the appropriate version of the chef server (Use the **Chef Server** tab).
    -   **Hint**: **Ubuntu 13.xx** doesnt seem to have explicit support so its a good reason for choosing the **LTS** version of **Ubuntu** for the Server).
2.  Installed it with the command:

        sudo dpkg -i chef-server_11.0.8-1.ubuntu.12.04_amd64.deb

3.  It then instructed me to run:

        sudo chef-server-ctl reconfigure

4.  I wasn't happy that the **http** and **https** ports were set to the typical default values (443 and 80) respectfully so I created the `/etc/chef-server/chef-server.rb` file and added the following lines:

        nginx['non_ssl_port'] = 8001
        nginx['ssl_port'] = 4443

5.  I ran `sudo chef-server-ctl reconfigure` to stop all the services, and get them to reconfigure and relaunch.

5.  I then ran `sudo chef-server-ctl test` to test the installation.

## Installing the Client

Its pretty similar (except that its all now on the client machine):

1.  Go [**here**] [chef-install] again and this time use the **Chef Client** tab.
2.  In this case it told me to run:

        curl -L https://www.opscode.com/chef/install.sh | sudo bash

## Setting up an Admin User

1.  Copy both of the files `/etc/chef-server/admin.pem` and `/etc/chef-server/chef-validator.pem`
from the **Server** to the `~/.chef` directory on the **Client** machine

2.  Ran `knife configure -i` to create an initial `~/.chef/knife.rb` file.

--------------

And **Chef Server/Client** is installed!

# Booststrapping A Chef Node!

So the **Server** is setup and the **Client** setup on the machine we wish to use as a node.  Hence we next have to setup this machine to actually run as a node...

I followed the instructions [**here**] [bootstrap-a-node].  In case that site goes down or there were some system specific subtleties I came across  I'll put the steps I used down here:

1.  Identify the **FQDN** or static **IP** for the node.

2.  Run this command (with user details that have sudo rights):
    -   It should still work if you drop the `-P` parameter, you will be queried for the user password

            knife bootstrap <FQDN/IP> -x <username> -P <password> --sudo


3.    Verify the node by running `knife client show <nodename>` or `knife client list`

[chef-server-tutorial]: http://www.opscode.com/blog/2013/03/11/chef-11-server-up-and-running/ "Getting Chef 11 Server up and running"
[chef-install]: http://www.opscode.com/chef/install/ "Install Chef | OpsCode"
[bootstrap-a-node]: http://docs.opscode.com/install_bootstrap.html "Bootstrap a Node | OpsCode"
