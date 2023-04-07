# TryHackMe-ice-Walkthrough
Deploy &amp; hack into a Windows machine, exploiting a very poorly secured media server.

![ice bg](https://user-images.githubusercontent.com/120317751/230588239-c2b3596b-8fb5-460c-8556-2e9f9d72a5ae.png)


![ice](https://user-images.githubusercontent.com/120317751/230573629-a0156837-a602-42ed-ac27-d7dccee48dcc.jpg)


<br>

<h2>Download VPN File from Release Section :</h2>

Link: https://github.com/Sumit-CyberSecurity/TryHackMe-ice-Walkthrough/releases/download/ice/sumit5011.ovpn
 
 
 🔴 Important :  Please rename this VPN file as per your TryHackMe account username

<b>Task 1: Connect</b>
<br>
<br>

Click on Access Machine --> Click on OpenVPN (How to connect & config VPN)



![ice (1)-min](https://user-images.githubusercontent.com/120317751/230582828-2ae90b78-e403-45c7-a745-8c99c66e4f57.gif)

<br>

<b><H2>Recon</b></H2>




![image](https://user-images.githubusercontent.com/120317751/230583696-bf067667-dbad-44cc-a79a-ea0aa36ee73b.png)

<B>Scan and enumerate our victim!</B>

Answer the questions below ----------------------------------------------------------------------------------------------------------------------------------------


Deploy the machine! This may take up to three minutes to start.

         No answer needed
         
Launch a scan against our target machine, I recommend using a SYN scan set to scan all ports on the machine. The scan command will be provided as a hint, however, it's recommended to complete the room 'Nmap' prior to this room.  

         No answer needed
         

Once the scan completes, we'll see a number of interesting ports open on this machine. As you might have guessed, the firewall has been disabled (with the service completely shutdown), leaving very little to protect this machine. One of the more interesting ports that is open is Microsoft Remote Desktop (MSRDP). What port is this open on?

           3389











