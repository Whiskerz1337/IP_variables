# IP_variables
<br>
Assignable IP variables for Kali Linux

<h2>About</h2>
<br>
The main focus of these tools is to allow the assignment of specific IP address variables in a linux shell environment. Linux shells support this feature by default, however variables normally only persist for a specific shell instance, even if spawning a child shell from a parent that contains the assigned variable.
<br>
<br>
tIP in particular works by creating an environment variable, which is assigned a value from a text file in the project folder. This means that it's possible to assign a target IP address variable that not only persists through new shell instances, but even through reboots.
<br>
<br>
The second tool provided (myIP) is simply a clean way to print out your own IP address as a string, without the need for grep or awk. This tool <i>does</i> rely on hardcoded interface names (eth0, tun0) and will check for each accordingly, printing the active one. I will likely add a configuration file in the future, which will allow for any interface name to be used.

<h2>Installation:</h2>
<br>

1. Clone the files into your home folder

2. Run the install_script from the new IP_variables folder (./install_script)

<br>
This will add everything to PATH and assign the necessary variables.
<br>

<h2>tIP:</h2>
<br>

This tool is designed to have a way to save a target's IP to a variable that persists between shell instances (or even reboots). To Assign a target IP, simply run the tool and pass in an argument:
<br>
<h3>example:</h3> 

<br>

To save an IP address:
<br>

<i>tIP 1.1.1.1</i>

<br>

You can then run tIP with no arguments to print the IP.

<br>

To print the saved address:

<br>

<i>tIP</i>

<br>

To then pass this IP into other tools, you must use '$':

<br>

<i>ping $tIP</i>

<i>nmap $tIP</i>   

<br>

And so on.

<br>
<br>
<h2>myIP:</h2>

<br>

This tool simply prints out your current IP address. It will check between eth0 and tun0 (vpn) and print the one in use. The main point of this tool is that it assigns the IP address it finds to a variable, which allows you to pass it as an argument into other tools (you must use '$' when passing it).
This has the limitation of the hardcoded interface names, so feel free to amend these as necessary.

<h3>example:</h3> 
<br>
<i>nmap $myIP</i>

<br>
<br>

<h2>Planned Improvements:</h2>

<br>

Help/Manual pages

Support for saving multiple IP address in tIP

Remove hardcoded interfaces names for myIP

Support for all popular linux shells

Support for unrestricted install paths

<br>

Enjoy!

<br>

