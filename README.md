# ACTIVE DIRECTORY SETUP ON WINDOWS SERVER 2022


- Create a Windows Server 2022 VM in VirtualBox.
- Configure VM with minimum requirements due to limited resources.
- Set up two NICs:
  - One with NAT for external access.
 
<img align="center" src="assets/images/Picture8.png" /><br>

- Another with Host-only adapter for host-only access.

<img align="center" src="assets/images/Picture9.png" /><br>

  
- VM traffic is routed through a pfSense firewall.
- Start the VM and follow standard Windows installation instructions.

<img align="center" src="assets/images/Picture10.png" /><br>

<img align="center" src="assets/images/Picture11.png" /><br>

- Choose "Windows Server 2022 Datacenter Evaluation (Desktop Experience)" for lab.

<img align="center" src="assets/images/Picture12.png" /><br>

<img align="center" src="assets/images/Picture13.png" /><br>

<img align="center" src="assets/images/Picture14.png" /><br>

- Complete installation, set password for built-in admin when prompted.

<img align="center" src="assets/images/Picture15.png" /><br>

- Press ` CTRL + ALT + DEL ` to login to the server.

<img align="center" src="assets/images/Picture16.png" /><br>

- Login using username `Administrator` and the provided password.

<img align="center" src="assets/images/Picture17.png" /><br>

- Server Manager starts automatically on startup.

<img align="center" src="assets/images/Picture20.png" /><br>

- In Server Manager the default services are visible.

<img align="center" src="assets/images/Picture21.png" /><br>

- Rename the PC to a sensible name (e.g., `DASHERSLAB AD`).

<img align="center" src="assets/images/Picture22.png" /><br>

- Restart the PC after renaming.
- Begin installing Active Directory services:

<img align="center" src="assets/images/Picture23.png" /><br>

  - Click on "Roles and Features".
  - Select installation type as "Roles and Features".

<img align="center" src="assets/images/Picture23.png" /><br>

  - Select the server displayed (if only one).

<img align="center" src="assets/images/Picture73.png" /><br>

  - Choose "Active Directory Domain Services" as the server role.
  - Click "Add Features" and then "Next".

<img align="center" src="assets/images/Picture26.png" /><br>

<img align="center" src="assets/images/Picture27.png" /><br>

<img align="center" src="assets/images/Picture28.png" /><br>

  - Check "Restart if required" on the confirmation screen.

<img align="center" src="assets/images/Picture29.png" /><br>

<img align="center" src="assets/images/Picture30.png" /><br>

  - Click "Install" to install the role.

<img align="center" src="assets/images/Picture31.png" /><br>

<img align="center" src="assets/images/Picture32.png" /><br>

- After installation, a notification prompts for post-deployment configuration to promote this server to a Domain Controller.

<img align="center" src="assets/images/Picture34.png" /><br>

- Start the deployment configuration wizard:
  - Choose "Add a new Forest".
  - Provide a domain name.

<img align="center" src="assets/images/Picture36.png" /><br>

  - Configure optional restore password.

<img align="center" src="assets/images/Picture37.png" /><br>

  - Leave DNS options at default. It will be installed.
 
<img align="center" src="assets/images/Picture38.png" /><br>

  - NetBIOS domain name is auto-populated from forest name.

<img align="center" src="assets/images/Picture39.png" /><br>
<img align="center" src="assets/images/Picture40.png" /><br>

  - Directory paths can be left as default.
    
<img align="center" src="assets/images/Picture41.png" /><br>
<img align="center" src="assets/images/Picture42.png" /><br>

  - Review changes; opt for manual installation (not PowerShell script).

<img align="center" src="assets/images/Picture44.png" /><br>

  - Click "Next" and proceed with prerequisite checks (ignore if needed).
  
<img align="center" src="assets/images/Picture45.png" /><br>

  - Click "Install" to begin installation.
- Restart the PC once installation is complete.
- The login screen now displays domain name followed by Administrator as `DASHERSWINLAB\Administrator`.

<img align="center" src="assets/images/Picture46.png" /><br>

- Enter the Domain Administrator password and not the local Administrator password
- This will then Log you in to the newly created domain, not the local PC.
- If you want to log int to the local Pc then you can choose the other user.
- For now lets log in to the Domain.
- Server Manager shows AD DS server group running.

- you can see the Server manager displays the newly added ` AD DS ` and ` DNS services `.

<img align="center" src="assets/images/Picture47.png" /><br>

- Now that we have the Active Directory setup, the DNS `DOMAIN NAME SYSTEM ` service is automatically configured.
- AD DS relies heavily on DNS for name resolution within the domain.
- DNS facilitates locating other domain controllers, domain-joined computers, and other domain resources.
- Of course it can be tweaked according to requirements, but the integration of these services ensures the seamless functioning.
-Now its a good practice to create a  `local Admin ` other than the built in Administrator.
- You can create this Admin and contain user in a ` Organizational unit `.
- You can view the process in detail this link [Create An Organizational Unit]( https://github.com/rajeevlraman/ActiveDirectory/blob/main/ad_ou.md)
- After creating the user you can login with the new Administrator credentials.
