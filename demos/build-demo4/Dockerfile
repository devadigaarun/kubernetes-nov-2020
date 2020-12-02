FROM mcr.microsoft.com/dotnet/sdk:3.1 as build
WORKDIR /app-src
COPY sample-app1/ .
RUN ["dotnet","restore"]
RUN ["dotnet","publish","-o","app"]

FROM mcr.microsoft.com/dotnet/aspnet:3.1
WORKDIR /app
COPY --from=build /app-src/app .
CMD ["dotnet","/app/sample-app1.dll"]
