# IP_tools
Assignable IP variables for Kali Linux

<h2>About</h2>
<br>
This project consists of two main command line tools aimed at helping pentesters and ethical hackers using Kali.
Essentially these tools allow you to save IP addresses into variables for later use. The tools currently work only for zsh, which is the default shell for Kali.

<h2>Installation:</h2>

<br>

1. Download the folder into your home folder

2. Run the install_script from the IP_tools folder

<br>
This will add everything to PATH and assign the necessary variables.
<br>
<h2>myIP:</h2>
<br>

This tool simply prints out your current IP address. It will check between eth0 and tun0 (vpn) and print the one in use. The main point of this tool is that it assigns the IP address it finds to a variable, which allows you to pass it as an argument into other tools (you must use '$' when passing it).
This has the limitation of the hardcoded interface names, so feel free to amend these as necessary.

<h3>example:</h3> 
<br>
<i>nmap $myIP</i>

<h2>tIP:</h2>
<br>

This tool is designed to have a way to save a target's IP to a variable that persists between shell instances (or even reboots). To Assign a target IP, simply run the tool and pass in an argument:
<br>
<h3>example:</h3> 

<br>

<i>tIP 1.1.1.1</i>

<br>

You can then run tIP with no arguments to print the IP.

<br>

The same rules apply when passing this into other tools, you must use '$':

<br>

<i>tIP 8.8.8.8</i>

<i>ping $tIP</i>

<i>nmap $tIP</i>   

<br>

And so on.   

<br>

Enjoy!

<br>

