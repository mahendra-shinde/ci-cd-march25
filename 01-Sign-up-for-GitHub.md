# Creating a New Personal GitHub Account Using a New Outlook Account

## Step 1: Create a New Outlook Account
1. Go to [Outlook](https://outlook.live.com/).
2. Click on **Create free account**.
3. Choose a new email address and click **Next**.
4. Create a password and click **Next**.
5. Enter your first and last name, then click **Next**.
6. Enter your country/region and birthdate, then click **Next**.
7. Complete the CAPTCHA verification and click **Next**.
8. Your new Outlook account is now created.

## Step 2: Create a New GitHub Account
1. Go to [GitHub](https://github.com/).
2. Click on **Sign up**.
3. Enter your new Outlook email address, create a password, and choose a username.
4. Complete the CAPTCHA verification and click **Create account**.
5. GitHub will send a verification code to your Outlook email. Check your email and enter the code on GitHub.
6. Follow the on-screen instructions to complete the setup of your new GitHub account.

## Step 3: Configure Local Git CLI
1. Download and install Git from [git-scm.com](https://git-scm.com/).
2. Open a terminal or command prompt.

### Set Your Git Username and Email
```sh
git config --global user.name "Your Name"
git config --global user.email "your-email@outlook.com"
```

### Configure Git Credentials Manager
1. Enable the Git credentials manager by running the following command:
```sh
git config --global credential.helper manager-core
```
2. Verify the configuration:
```sh
git config --global credential.helper
```

### Verify Your Configuration
```sh
git config --global --list
```

