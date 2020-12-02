FROM gcc:latest

# SET WORKDIR (Create directory, if does't exists!)
WORKDIR /app

# Copy file into WORKDIR
COPY app.c  .

# Building a binary 'app.o'
RUN ["gcc","app.c","-o","app.o"]

# Using newly built binary as CMD 
CMD ["/app/app.o"]