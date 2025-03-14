# Creating a Local Repository and Generating a Maven Project

## Step 1: Create a Local Repository

1. Open a Git Bash.
2. Navigate to the directory where you want to create your new repository:

    ```sh
    cd /c/
    mkdir git-demos
    cd git-demos
    ```

3. Initialize a new Git repository:
    ```sh
    git init demo-1
    ```

## Step 2: Generate a Maven Project

1. Ensure you have Maven installed. You can check by running:
    ```sh
    mvn -version
    ```
1. Generate a new Maven project using the following command:

    ```sh
    mvn archetype:generate -DgroupId=com.example -DartifactId=myapp -DarchetypeArtifactId=maven-archetype-quickstart -DinteractiveMode=false
    ```

Your local repository `demo-1` now contains a basic Maven project structure.

1. Verify the project created using VSCode editor.

    ```bash
    code /c/git-demos/demo-1
    ```

1.  Add the newly created maven project to git "stage" (index)

    ```bash
    git status          # Check the status of GIT repository
    git add myapp/      # Add directory myapp with all its contents to "Staging Area"/"Index"
    git commit -m "New maven project created" # Commit the "stagged" changes
    ```