# Docker Compose

1. docker-compose is a utility that allows deploying MUTLI-CONTAINER applications.
2. docker-compose.exe is the command and docker-compose.yml is the declaration files.
3. docker-compose.yml must be inside a folder, folder-name becomes your project-name.
4. Use following command to validate compose file

    `docker-compose config`

5.  Deploy compose file, command is

    `docker-compose up -d`
    
## Docker COmpose YAML Syntax

```
version: '3.5'

## Mandatory
services:

    servicename:

        image: IMAGENAME
        environment:
            KEY: VALUE
        networks:
        - netname
        volumes:
        - VOLNAME:GuestPath

# Optional
networks:


# Optional
volumes:
```