## Prepare SDK image for BUILD and PUBLISH
FROM mcr.microsoft.com/dotnet/sdk:3.1 as build
WORKDIR /app-src
# Copy Project Source directory
COPY sample-app1/ .
# Install all dependencies
RUN ["dotnet","restore"]
# Build and Publish to Sub-directory 'app'
# The actual path would be /app-src/app/
RUN ["dotnet","publish","-o","app"]

# Start with RUNTIME image with ASP.NET Core 3.1 Libs
FROM mcr.microsoft.com/dotnet/aspnet:3.1
# Create Working Directory
WORKDIR /app
# Copy files from BUILD stage (at /app-src/app location)
COPY --from=build /app-src/app .
# Set the COMMAND to RUN on STARTUP
CMD ["dotnet","/app/sample-app1.dll"]
