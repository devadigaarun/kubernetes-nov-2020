## Stage 1 as "build"
FROM gcc:latest as build
# SET WORKDIR (Create directory, if does't exists!)
WORKDIR /app
# Copy file into WORKDIR
COPY app.c  .
# Building a binary 'app.o'
RUN ["gcc","-static","-o","app.o","app.c"]

## Stage 2  / Scratch is a FLAG 
FROM scratch
COPY --from=build /app/app.o /app.o
CMD ["/app.o"]