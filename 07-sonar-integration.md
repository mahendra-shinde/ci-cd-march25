### Steps to Integrate Jenkins with SonarCloud for Java Project Scanning

### Step 0 : Sign up for FREE SonarQube Cloud Account

1. Navigate to SonarCloud sign up page at https://www.sonarsource.com/products/sonarcloud/signup/

2. Click on `GitHub` (Signup using Github Account).
3. Enter your github credentials and then click on Login. 
4. Click on `Authorize SonarQube Cloud` to Access GitHub.
5. After Successful signup, create a new `organization` manually. 
    In right top corner, there is `+` button which would open context menu with two options: `create project` and `create organization`
6. Click on `Create Manually` and then provide unique name and choose `Free` plan
7. click `Create` button.
8. Click on `Analyze new project` -> provide a display name for project, visibility should be `Public`. click `Next`
9. Choose `Number of days` for code compare. click `Create Project` button.
10. Click on `Other CI` and then choose `Maven`
11. Keep this page open for configuration in jenkins.

    > You need sonar_token and maven properties config


#### Step 1: Install SonarQube Scanner for Jenkins Plugin
1. Navigate to **Manage Jenkins** → **Plugin Manager** → **Available Plugins**.
2. Search for **SonarQube Scanner for Jenkins** and install it.
3. Restart Jenkins if required.

#### Step 2: Configure SonarQube in Jenkins
1. Go to **Manage Jenkins** → **Configure System**.
2. Scroll down to **SonarQube Servers** and click **Add SonarQube**.
3. Provide the following details:
   - **Name**: `sonar1` (Logical name to identify this SonarQube instance)
   - **Server URL**: `https://sonarcloud.io`
4. Configure **Server Authentication Token**:
   - Click **Add** → **Jenkins** Credential Manager → **Secret Text**.
   - Use the **SONAR_TOKEN** generated in SonarCloud. This token was generated when new "manual project" was setup on SonarCloud.
   - Enter this token in Jenkins and assign it a descriptive ID (e.g., `sonar-token`).
   - Select this credential from the dropdown in Jenkins.

5. Click **Save** to apply changes.

### New Jenkins Job (Freestyle job)

1. From jenkins dashboard click `New Item` and then choose type `Freestyle Job`
2. Use following configuration:

```yaml
SCM:
  git: https://github.com/mahendra-shinde/ci-servlet-demo
  branch: */master

Build Environment:
  Use secret text or file:
    Variable: SONAR_TOKEN   # MUST EXACTLT MATCH
    Credentials: choose "SONAR_TOKEN" # from credential created earlier

Build Steps:
  Top Level Maven Target:
    Name: M3
    Goal: verify org.sonarsource.scanner.maven:sonar-maven-plugin:sonar -Dsonar.projectKey=mahendra123_demo101 
    ## Replace the projectKey value ####
```

3. Click **Save** button and then click **Build Now**.


### **Notes and Best Practices**
- Ensure the `SONAR_TOKEN` has appropriate permissions for the organization and project in SonarCloud.
- Make sure Maven (`M3`) is correctly configured in Jenkins under **Global Tool 