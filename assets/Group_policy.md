# Creating Group Policies in Windows Active Directory

## Overview
Group Policy is a feature of Windows Active Directory (AD) that allows IT administrators to manage and configure operating systems, applications, and user settings in a centralized manner. By creating and applying Group Policy Objects (GPOs), administrators can enforce security settings, deploy software, configure user environments, and much more across the networked computers within a domain.

## Key Concepts
- **Group Policy Object (GPO)**: A collection of settings that define the configuration and behavior of users and computers.
- **Active Directory (AD)**: A directory service that provides centralized authentication and authorization.
- **Group Policy Management Console (GPMC)**: A Microsoft Management Console (MMC) snap-in used to create, modify, and manage GPOs.
- **Organizational Unit (OU)**: A container within AD that can hold users, groups, and computers, and to which GPOs can be applied.

## Steps to Create and Apply a Group Policy

### Step 1: Open the Group Policy Management Console
1. Press `Win + R`, type `gpmc.msc`, and press `Enter` to open the Group Policy Management Console (GPMC).
2. Alternatively, you can access GPMC via the **Start Menu** by navigating to **Administrative Tools** and selecting **Group Policy Management**.

<img align="center" src="/assets/images_GP/Image1.jpg" /><br>

### Step 2: Create a New Group Policy Object (GPO)
1. In the GPMC, expand your domain's node and right-click on the **Group Policy Objects** folder.
2. Select **New** to create a new GPO.
3. Enter a name for the GPO that reflects its purpose (e.g., "Password Policy" or "Software Deployment Policy") and click **OK**.

### Step 3: Edit the GPO
1. Right-click on the newly created GPO and select **Edit** to open the Group Policy Management Editor.
2. The editor is divided into two main sections:
   - **Computer Configuration**: Policies and settings that apply to computers, regardless of who logs on.
   - **User Configuration**: Policies and settings that apply to users, regardless of which computer they log on to.

### Step 4: Configure Policy Settings
1. **Computer Configuration** or **User Configuration**: Navigate to the specific setting you want to configure.
2. **Example 1**: Enforcing a Password Policy
   - Navigate to `Computer Configuration` > `Policies` > `Windows Settings` > `Security Settings` > `Account Policies` > `Password Policy`.
   - Double-click on **Minimum password length** and set the desired minimum length (e.g., 8 characters).
   - Configure other password policies such as **Password must meet complexity requirements** and **Maximum password age**.
3. **Example 2**: Mapping a Network Drive for Users
   - Navigate to `User Configuration` > `Preferences` > `Windows Settings` > `Drive Maps`.
   - Right-click and select **New** > **Mapped Drive**.
   - Set the **Location** (e.g., `\\Server\SharedFolder`), choose a **Drive Letter**, and configure options like reconnect at logon.
   - Apply the settings and close the editor.

### Step 5: Link the GPO to an Organizational Unit (OU)
1. In the GPMC, right-click the OU where you want to apply the GPO (or the domain if you want it to apply to all objects within the domain).
2. Select **Link an Existing GPO**.
3. Choose the GPO you created from the list and click **OK**.

### Step 6: Verify and Apply the GPO
1. After linking the GPO, it may take some time for the policy to propagate to all computers and users.
2. You can force an immediate update by running the `gpupdate /force` command on a target computer.
3. Check the applied policies using the `gpresult /r` command or the **Resultant Set of Policy (RSoP)** tool.

## Practical Example: Setting a Screen Lock Policy
### Step 1: Create and Edit the GPO
1. Create a new GPO named "Screen Lock Policy" and open it for editing.
2. Navigate to `User Configuration` > `Policies` > `Administrative Templates` > `Control Panel` > `Personalization`.

### Step 2: Configure the Policy
1. Double-click on **Enable screen saver** and set it to **Enabled**.
2. Double-click on **Password protect the screen saver** and set it to **Enabled**.
3. Double-click on **Screen saver timeout** and set the desired timeout duration (e.g., 600 seconds for 10 minutes).

### Step 3: Link and Apply the GPO
1. Link the "Screen Lock Policy" GPO to the appropriate OU or domain.
2. Use `gpupdate /force` to apply the policy immediately on target computers.

## Tips for Effective Group Policy Management
- **Document Policies**: Keep detailed records of all GPOs, including their settings and the OUs to which they are linked.
- **Test Policies**: Before applying new GPOs domain-wide, test them in a controlled environment or on a small set of users/computers.
- **Use Descriptive Names**: Name GPOs descriptively to make their purpose clear.
- **Regularly Review and Audit GPOs**: Periodically review GPOs to ensure they are still relevant and effective.

## Conclusion
Creating and managing Group Policies in Active Directory allows for centralized and efficient control over user and computer settings. By following the steps outlined above, administrators can effectively implement security measures, standardize user environments, and automate various administrative tasks.

![Group Policy Management](https://via.placeholder.com/800x400.png?text=Group+Policy+Management+Console)
