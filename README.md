<p align="center">
<img src="https://i.imgur.com/LLk8I0Q.png" height="50%" width="50%" alt="Active Directory logo"/>
</p>

# Applying Security Policies (Active Directory)

This guide outlines the process of applying security policies in an Active Directory environment to ensure compliance and security standards are met. Follow these steps to configure and enforce security policies effectively.

---

## Tools and Technologies Used

- **Platform**: Active Directory Group Policy Management Console (GPMC)
- **Dependencies**: Group Policy Objects (GPOs)

---

## Operating Systems Used

- **Operating System**: Windows Server 2019/2022

---

## Overview of Steps

1. **Access the Group Policy Management Console (GPMC)**  
   - Open the GPMC tool on your server or management computer.

2. **Create a New Group Policy Object (GPO)**  
   - Define a GPO to manage security settings.

3. **Configure Security Settings**  
   - Apply password, account lockout, and audit policies.

4. **Link the GPO to an Organizational Unit (OU)**  
   - Associate the GPO with the relevant OU.

5. **Validate Policy Application**  
   - Use tools like `gpresult` and Event Viewer to confirm policy enforcement.

---

## Configuration Steps

### Step 1: Access the Group Policy Management Console (GPMC)

- **Action**:  
  - Open the GPMC by navigating to **Start > Administrative Tools > Group Policy Management** or by running `gpmc.msc` in the Run dialog.

<p align="center">
<img src="" height="75%" width="100%" alt="Accessing GPMC console"/>
</p>

---

### Step 2: Create a New Group Policy Object (GPO)

- **Action**:  
  - In the GPMC, right-click **Group Policy Objects** and select **New**.  
  - Name the GPO descriptively (e.g., "Security Settings Policy").

<p align="center">
<img src="" height="75%" width="100%" alt="Creating a new GPO"/>
</p>

---

### Step 3: Configure Security Settings

- **Password Policies**:  
  - Navigate to **Computer Configuration > Policies > Windows Settings > Security Settings > Account Policies > Password Policy**.  
  - Configure settings such as password complexity and maximum password age.

- **Account Lockout Policies**:  
  - Go to **Account Lockout Policy** and set thresholds for account lockout duration and attempts.

- **Audit Policies**:  
  - Navigate to **Advanced Audit Policy Configuration** and enable auditing for logon events, object access, and policy changes.

<p align="center">
<img src="" height="75%" width="100%" alt="Configuring password policies"/>
<img src="" height="75%" width="100%" alt="Configuring audit policies"/>
</p>

---

### Step 4: Link the GPO to an Organizational Unit (OU)

- **Action**:  
  - In the GPMC, locate the OU where the policy should apply.  
  - Right-click the OU, select **Link an Existing GPO**, and choose the created GPO.

<p align="center">
<img src="" height="75%" width="100%" alt="Linking GPO to OU"/>
</p>

---

### Step 5: Validate Policy Application

- **Action**:  
  - Use `gpupdate /force` on a client machine to apply the policy immediately.  
  - Run `gpresult /h` to generate a report verifying policy application.  
  - Check the Event Viewer for logs related to policy enforcement.

<p align="center">
<img src="" height="75%" width="100%" alt="Validating policy application with gpresult"/>
<img src="" height="75%" width="100%" alt="Checking Event Viewer logs"/>
</p>

---

## Summary

This tutorial covered:  

- **GPO Creation**: Steps to define a new Group Policy Object.  
- **Security Configuration**: Applying password, account lockout, and audit policies.  
- **Policy Linking**: Associating the GPO with a specific Organizational Unit.  
- **Validation**: Confirming successful policy application using tools and logs.

By following these steps, you can enhance the security posture of your Active Directory environment, ensuring compliance and protecting organizational assets.
