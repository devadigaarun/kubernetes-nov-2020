# Docker Build


* `docker build` command can prepare a new custom container image.
* Collects all the contents from PROJECT-DIRECTORY (skip files and directories mentioned in .dockerignore) and upload it to Docker engine.
* Docker engine CANNOT access any files or directories OUTSIDE the project-directory (AKA Build context)
* Command syntax is

    `docker build -t IMAGENAME PROJECT-DIRECTORY`

* Examples

    `docker build -t myapp:1 .`

    Imagename: myapp:1
    Project Directory: . (Present working directory!)

* Docker Build Project directory

    ```
    Project-Directory\
        Dockerfile
        .dockerignorefile
        Otherfiles
        Otherdirectory\
    ```

* Dockerfile Syntax

    ```
    # Base image for current one
    FROM <BaseImageName>

    # Copy files and directories
    COPY <sourcefile> <inside-container-path>

    # Copy and extract contents of TAR
    ADD <sourcefile> <inside-container-path>

    # Run a command in BUILD process
    RUN <Cmd> <Arg>

    # Define the ROOT process for container
    # When missing, CMD from BASE-IMAGE would be used!
    CMD <Cmd> <Arg>
    ```