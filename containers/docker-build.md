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