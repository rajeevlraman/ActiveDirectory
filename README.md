# ActiveDirectory
### Creating an Organizational Unit (OU):

1. **Open Active Directory Users and Computers**:
   - Go to **Start Menu** → **Administrative Tools** → **Active Directory Users and Computers**.

2. **Navigate to the Domain**:
   - Expand the domain node where you want to create the OU (e.g., `AD.DASHERSWINLAB.local`).

3. **Create the OU**:
   - Right-click on the domain or an existing OU where you want to create the new OU.
   - Select **New** → **Organizational Unit**.
   - Name the new OU following a clear naming convention. For example, if creating an OU for Admin Users, you might name it `AdminUsers`. i have named it `LabAdmins`.

4. **Set Permissions (Optional)**:
   - Right-click on the new OU (`LabAdmins`) → **Properties**.
   - Go to the **Security** tab to set permissions for who can manage objects within this OU.
   - I'll leave it empty.

### Creating an Admin User in the OU:

1. **Create the User Account**:
   - Right-click on the newly created OU (`LabAdmins`) or any other suitable OU.
   - Select **New** → **User**.

2. **Fill Out User Details**:
   - Enter the user's details, including:
     - First name, last name, and username (e.g., `admin_user`).
     - Password (choose a secure password).
     - Ensure the **User must change password at next logon** is unchecked if setting initial password.

3. **Assign User to Groups** (Optional):
   - On the **Member Of** tab, add the user to appropriate groups like `Domain Admins`, `Administrators`, or other relevant groups based on administrative roles.

4. **Configure User Properties**:
   - Customize settings in other tabs as needed, such as **Account**, **Profile**, **Telephones**, etc.

5. **Finish**:
   - Click **OK** to create the user.

### Naming Conventions:

- **OU Naming Convention**: Choose a clear and descriptive name that reflects the purpose of the OU, such as `AdminUsers` for administrative users or `SalesUsers` for sales department users.
- **User Naming Convention**: Typically, usernames should follow a standard format for consistency and clarity. For example, `firstname.lastname` or `firstinitial.lastname` (`bruce.banner` or `bbanner`). I'll stick with my convention 'FirstnameLastname' (example the user: `Bruce Banner` email has `brucebanner@`.

### Example:

- **OU Name**: `LabAdmin`
- **First name: `Bruce`
- Last name: `Banner`
- **User Name**: `brucebanner`
