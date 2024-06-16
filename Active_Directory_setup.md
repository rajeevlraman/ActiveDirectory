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

<img align="center" src="assets/images/Picture31.png" /><br>

  - Check "Restart if required" on the confirmation screen.
  - Click "Install" to install the role.
- After installation, a notification prompts for post-deployment configuration to promote this server to a Domain Controller.
- Start the deployment configuration wizard:
  - Choose "Add a new Forest".
  - Provide a domain name.
  - Configure optional restore password.
  - Leave DNS options at default.
  - NetBIOS domain name is auto-populated from forest name.
  - Directory paths can be left as default.
  - Review changes; opt for manual installation (not PowerShell script).
  - Click "Next" and proceed with prerequisite checks (ignore if needed).
  - Click "Install" to begin installation.
- Restart the PC once installation is complete; login screen displays domain name.
- Login to the newly created domain, not the local PC.
- Server Manager shows AD DS server group running.
- Now its a good practice to create a local Admin other than the built in Administrator.
- You can create this Admin and contain user in a Organizational unit.
- You can view the process in detail here https://github.com/rajeevlraman/ActiveDirectory/blob/main/README.md
- After creating the user you can login with the new Admin.
- Now that we have the Active Directory setup, the DNS `DOMAIN NAME SYSTEM ` service is automatically configured.
- AD DS relies heavily on DNS for name resolution within the domain.
- DNS facilitates locating other domain controllers, domain-joined computers, and other domain resources.
- Of course it can be tweaked according to requirements, but the integration of these services ensures the seamless functioning.
