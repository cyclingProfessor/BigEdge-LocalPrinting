# BigEdge-LocalPrinting
The problem with the Big Edge Linux command line tool "f5fpc" is that it will not permit access to local resources when the vpn tunnel is running.
This means that you can't find your streaming device, your network drives or your printer.
It is easy to overcome this with just one line that adds the local network to your routing table.  This must be done AFTER the tunnel is set up.

The script "vpn" here does just that.  It is a bash script that must be run as root - with sudo - since it alters the routing table.

=================================================================================================================
TO make it work for your system you will need to edit the defaults in the script.  
The IP of your local network,
The name of your Big Edge vpn server host.
The name of the device that your computer uses to talk to other machines: netdev

These are configured by changing hte appropriate lines at the top of the vpn script.
======================================================================================================

You can run the script in three modes, corresponding to the three modes of f5fpc.
sudo vpn -s : to connect
vpn -o : to disconnect
vpn -i : to query the status of the tunnel

You can also use "sudo vpn" which defaults to "sudo vpn -s" 
sudo vpn -s -t hostname : connects to the server "hostname"

Of course, the script prints help if you use it wrong.
