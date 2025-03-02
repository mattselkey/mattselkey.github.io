---
title: "Configuring 2FA for Github with Microsoft Visual Studio Code Integration."
date: "2018-12-16"
author: "mattselkey"
categories: ["Github"]
tags: ["2FA","github","PowerShell","VisualStudioCode"]
---

If not already, at a bare minimum, you should be using **2FA (Two-Factor Authentication)** with all services.

Setting up GitHub with 2FA using Google Authenticator is simple and well-documented online. However, setting up 2FA with **Microsoft Visual Studio Code** is not as straightforward.

This post details how I set up my environment to accomplish this.

## Prerequisites

- A **GitHub** account.
- A **Mobile Phone** with Google Authenticator installed. See the link [here](https://support.google.com/accounts/answer/1066447?co=GENIE.Platform%3DAndroid&hl=en) or search for it in the Android/iOS app store.

## Assumptions

- **Microsoft Visual Studio Code** is installed.
- **Git for Windows** is installed.
  - Visual Studio Code has been set as Git's default editor.
  - All other install options are set to the defaults.

---

# 1. Setting Up GitHub 2FA

### Step 1: Enable 2FA on GitHub
Log in to **GitHub** and go to **Settings**.

![GitHub Settings](2018-11-25-16_26_47-Releases-·-greenshot_greenshot.png)

Navigate to **Security** and click on **Enable two-factor authentication**.

![GitHub Security](2018-11-25-17_08_59-Security.png)

Select **Set up using an app**.

![GitHub 2FA Setup](2018-11-25-17_11_03-Enable-two-factor-authentication.png)

### Step 2: Save Recovery Codes
On the next screen, copy your **recovery codes** and save them securely. Password managers like [LastPass](https://www.lastpass.com/), [1Password](https://1password.com/), or [Keeper](https://keepersecurity.com/en_GB/) are good options.

![GitHub Recovery Codes](2018-11-25-17_13_02-Enable-two-factor-authentication2.png)

### Step 3: Link GitHub with Google Authenticator
- Open **Google Authenticator** on your phone.
- Scan the **QR code** provided.
- Enter the **6-digit verification code** from the app into GitHub and click **Enable**.

![GitHub 2FA Enabled](2018-11-25-17_14_52-Enable-two-factor-authentication.png)

2FA is now successfully enabled! You should see this confirmation:

![GitHub 2FA Success](2018-11-25-17_39_35-Manage-two-factor-authentication-1.png)

Next time you log in to GitHub, you will need to enter a **6-digit verification code** from Google Authenticator.

---

# 2. Create a Personal Access Token

To access your GitHub account from **Visual Studio Code**, you need to create a **Personal Access Token**.

### Step 1: Generate a Token
On **GitHub**, navigate to:

- **Developer settings** → **Personal access tokens** → **Generate new token**

![GitHub Personal Access Token](2018-11-25-17_55_53-Personal-Access-Tokens.png)

Enter a description for your new token and select the required scope. For repository work, the following permissions should suffice:

![GitHub Token Scopes](2018-11-25-17_58_43-New-personal-access-token.png)

Click **Generate token**.

![GitHub Token Generated](2018-11-25-18_10_48-New-personal-access-token.png)

Copy and save the token securely.

---

# 3. Configure Git for Windows with GitHub

Ensure **Git for Windows** is installed. Then, in the **Visual Studio Code terminal**, run:

```bash
git config --global credential.helper wincred
```

As shown in the example below:

![LoggingModule.psm1 - Untitled (Workspace) - Visual Studio Code](2018-12-16-11_23_40-LoggingModule.psm1-Untitled-Workspace-Visual-Studio-Code.png)

The next time a commit is pushed to GitHub from a local repo, you will be prompted to enter your GitHub login details, as shown below.  
**Use the personal access token as your password**:

![GitHub Login Prompt](2018-11-25-22_30_50-Window.png)

Git should now be configured with your GitHub account.

Should you need to confirm the credentials on your Windows workstation, open the Credential Manager using the following command:

```dos
control /name Microsoft.CredentialManager
```
![Windows Credential Manager](2018-11-25-22_56_46-Window.png)

Under **Generic Credentials** in the **Windows Credentials** tab, you can view and remove your access token if needed.

![GitHub Token in Windows](2018-11-25-23_00_03-Window.png)
![Windows Credential Details](2018-11-25-23_01_17-Window.png)
