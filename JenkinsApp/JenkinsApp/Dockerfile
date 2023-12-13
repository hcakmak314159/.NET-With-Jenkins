# See https://aka.ms/customizecontainer to learn how to customize your debug container and how Visual Studio uses this Dockerfile to build your images for faster debugging.

# Base Stage
FROM mcr.microsoft.com/dotnet/aspnet:7.0 AS base
WORKDIR /app
EXPOSE 80
EXPOSE 443

# Build Stage
FROM mcr.microsoft.com/dotnet/sdk:7.0 AS build
WORKDIR /src
COPY ["JenkinsApp/JenkinsApp.csproj", "JenkinsApp/"]
RUN dotnet restore "JenkinsApp/JenkinsApp.csproj"
COPY . .
WORKDIR "/src/JenkinsApp"
RUN dotnet build "JenkinsApp.csproj" -c Release -o /app/build

# Publish Stage
FROM build AS publish
RUN dotnet publish "JenkinsApp.csproj" -c Release -o /app/publish /p:UseAppHost=false

# Final Stage
FROM base AS final
WORKDIR /app
COPY --from=publish /app/publish .
ENTRYPOINT ["dotnet", "JenkinsApp.dll"]
