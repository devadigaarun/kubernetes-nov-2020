## Docker build demo1

1.  Create a directory 'build-demo1' and following files inside:

    Dockerfile, .dockeringore, index.html & contactus.html

2.  Add following lines inside 'Dockerfile'

    ```
    ## Base Image
    FROM nginx:alpine

    COPY *.html /usr/share/nginx/html/
    ```

3.  Update HTML files with some HTML code.

4.  To build and test, open CMD in 'build-demo1' directory

    ```
    $ docker build -t demo1 . 
    $ docker run --rm -d --name w1 -p 8080:80 demo1
    $ curl http://localhost:8080/
    ```