# CI/CD Demo with Jenkins

## Step 1: Fork the GitHub Repository

1. Go to the repository: [ci-servlet-demo](https://github.com/mahendra-shinde/ci-servlet-demo)
2. Click on the "Fork" button at the top right corner to create a copy of the repository under your GitHub account.

## Step 2: Create Jenkins Project "demo-ci" to Build WAR File

1. Open Jenkins and log in.
2. Click on "New Item" and enter the name `demo-ci`.
3. Select "Freestyle project" and click "OK".
4. In the "General" tab, provide a description if needed.
5. In the "Source Code Management" section, select "Git" and enter the URL of your forked repository.
6. In the "Build" section, click on "Add build step" and select "Invoke top-level Maven targets".
    - Enter `clean package` in the "Goals" field.
7. Click "Save" to create the job.

## Step 3: Create Jenkins Project to Deploy WAR File

1. Click on "New Item" and enter the name `deploy-to-tomcat`.
2. Select "Freestyle project" and click "OK".
3. In the "General" tab, provide a description if needed.
4. In the "Build" section, click on "Add build step" and select "Copy artifacts from another project".
    - Enter `demo-ci` in the "Project name" field.
    - Select "Last successful build" and enter `**/*.war` in the "Artifacts to copy" field.
5. Click on "Add post-build action" and select "Deploy war/ear to a container".
    - Enter `**/*.war` in the "WAR/EAR files" field.
    - Enter in context "/<yourname>"
    - Enter `http://4.224.9.8:8080` in the "Context path" field.
    - Use tomcat credentials (manager/manager)
6. Click "Save" to create the job.

## Step 4: Trigger the Deployment Job

1. Go to the `demo-ci` job.
2. Click on "Configure".
3. In the "Post-build Actions" section, click on "Add post-build action" and select "Build other projects".
    - Enter `deploy-to-tomcat` in the "Projects to build" field.
4. Click "Save".

Now, every time you build the `demo-ci` job, it will automatically trigger the `deploy-to-tomcat` job to deploy the WAR file to your Tomcat server.