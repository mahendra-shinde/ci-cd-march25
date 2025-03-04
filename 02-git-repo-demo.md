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
2. Generate a new Maven project using the following command:

    ```sh
    mvn archetype:generate -DgroupId=com.example -DartifactId=myapp -DarchetypeArtifactId=maven-archetype-quickstart -DinteractiveMode=false
    ```

Your local repository `demo-1` now contains a basic Maven project structure.