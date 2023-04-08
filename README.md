# TryHackMe-ice-Walkthrough
Deploy &amp; hack into a Windows machine, exploiting a very poorly secured media server.

![ice bg](https://user-images.githubusercontent.com/120317751/230588239-c2b3596b-8fb5-460c-8556-2e9f9d72a5ae.png)


![ice](https://user-images.githubusercontent.com/120317751/230573629-a0156837-a602-42ed-ac27-d7dccee48dcc.jpg)


<br>

<h2>Download VPN File from Release Section :</h2>

Link: https://github.com/Sumit-CyberSecurity/TryHackMe-ice-Walkthrough/releases/download/ice/sumit5011.ovpn
 
 
 🔴 Important :  Please rename this VPN file as per your TryHackMe account username

<b><H2>Task 1 Connect</b></H2>
<br>
<br>

Click on Access Machine --> Click on OpenVPN (How to connect & config VPN)



![ice (1)-min](https://user-images.githubusercontent.com/120317751/230582828-2ae90b78-e403-45c7-a745-8c99c66e4f57.gif)

<br>

<b><H2>Task 2 Recon</b></H2>




![image](https://user-images.githubusercontent.com/120317751/230583696-bf067667-dbad-44cc-a79a-ea0aa36ee73b.png)

<B>Scan and enumerate our victim!</B>

Answer the questions below ----------------------------------------------------------------------------------------------------------------------------------------


Deploy the machine! This may take up to three minutes to start.

     No answer needed
         
Launch a scan against our target machine, I recommend using a SYN scan set to scan all ports on the machine. The scan command will be provided as a hint, however, it's recommended to complete the room 'Nmap' prior to this room.  

     No answer needed
         

Once the scan completes, we'll see a number of interesting ports open on this machine. As you might have guessed, the firewall has been disabled (with the service completely shutdown), leaving very little to protect this machine. One of the more interesting ports that is open is Microsoft Remote Desktop (MSRDP). What port is this open on?

     3389
           
Command: (Your Start Machine IP)

    sudo nmap -sT -sV -O -Pn 10.10.254.30 
           
           

![Screenshot from 2023-04-07 15-30-12](https://user-images.githubusercontent.com/120317751/230589653-59731a6c-d70d-4845-ba58-e52761203d58.png)


What service did nmap identify as running on port 8000? (First word of this service)

     Icecast
     

What does Nmap identify as the hostname of the machine? (All caps for the answer)

     DARK-PC
     
     
<b><H2>Task 3 Gain Access</b></H2>   

![Screenshot from 2023-04-08 00-02-27](https://user-images.githubusercontent.com/120317751/230659913-1bd61fde-2956-4235-bccd-54edef6b37ac.png)


Exploit the target vulnerable service to gain a foothold!

Answer the questions below ----------------------------------------------------------------------------------------------------------------------------------------


Now that we've identified some interesting services running on our target machine, let's do a little bit of research into one of the weirder services identified: Icecast. Icecast, or well at least this version running on our target, is heavily flawed and has a high level vulnerability with a score of 7.5 (7.4 depending on where you view it). What type of vulnerability is it? Use https://www.cvedetails.com for this question and the next.

     execute code overflow
     

What is the CVE number for this vulnerability? This will be in the format: CVE-0000-0000

      CVE-2004-1561
      
Now that we've found our vulnerability, let's find our exploit. For this section of the room, we'll use the Metasploit module associated with this exploit. Let's go ahead and start Metasploit using the command `msfconsole`      

       No answer needed


After Metasploit has started, let's search for our target exploit using the command 'search icecast'. What is the full path (starting with exploit) for the exploitation module? This module is also referenced in 'RP: Metasploit' which is recommended to be completed prior to this room, although not entirely necessary. 

      exploit/windows/http/icecast_header
      

Let's go ahead and select this module for use. Type either the command `use icecast` or `use 0` to select our search result.

        No answer needed
        
Following selecting our module, we now have to check what options we have to set. Run the command `show options`. What is the only required setting which currently is blank?

         rhosts
         

First let's check that the LHOST option is set to our tun0 IP (which can be found on the access page). With that done, let's set that last option to our target IP. Now that we have everything ready to go, let's run our exploit using the command `exploit`

         No answer needed






