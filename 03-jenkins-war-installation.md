# Installing and Running Jenkins from a WAR File

This guide will help you install and run Jenkins from a WAR file on your system.

## Prerequisites
- **Java Development Kit (JDK)**: Jenkins requires Java to run. Ensure you have JDK 11 or later installed.
- **Jenkins WAR File**: Download the Jenkins WAR file from the [Jenkins website](https://www.jenkins.io/download/).

## Steps

### Step 1: Verify Java Installation

Make sure you have Java installed on your system. You can check the Java version by running the following command:

```sh
java -version
```

> The output should show the installed Java version, which should be 11 or later.

### Step 2: Download Jenkins WAR File

Download the Jenkins WAR file from the official Jenkins download page.

### Step 3: Run Jenkins WAR File

Open a terminal or command prompt, navigate to the directory where you downloaded the Jenkins WAR file, and run the following command:

```sh
java -jar jenkins.war
```

> In case, you get an error with "java" command, you can try a full path of java.exe instead:   `"Program Files\Java\jdk-17\bin\java.exe" -jar jenkins.war`

### Step 4: Access Jenkins

Once Jenkins is running, you can access it by opening a web browser and navigating to:

```
http://localhost:8080
```

### Step 5: Unlock Jenkins

The first time you access Jenkins, you will be prompted to unlock it. Follow these steps:

1. Retrieve Administrator Password:

The initial administrator password is stored in a file on your system. The file path will be displayed on the Jenkins unlock screen.

Or, you could check the Command prompt / terminal window for Initial password, select generated password using mouse and "right click" to copy it

> DO NOT USE `CTRL-C` shortcut key to copy, It would actually kill jenkins from terminal !!!

1. Click "Continue" to proceed.

### Step 6: Install Suggested Plugins
Jenkins will prompt you to install plugins. It is recommended to install the suggested plugins:

Click on "Install suggested plugins".

Jenkins will automatically download and install the selected plugins. This process may take a few minutes.

### Step 7: Create First Admin User

After the plugins are installed, Jenkins will prompt you to create the first admin user:

Enter the required details (username, password, full name, and email address).

Click "Save and Finish".

### Step 8: Start Using Jenkins

Jenkins is now ready to use. Click on "Start using Jenkins" to access the Jenkins dashboard.