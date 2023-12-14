FROM mcr.microsoft.com/dotnet/aspnet:7.0 AS base
WORKDIR /app
EXPOSE 80
EXPOSE 443

FROM mcr.microsoft.com/dotnet/sdk:7.0 AS build
WORKDIR /src
COPY ["JenkinsApp/JenkinsApp.csproj", "JenkinsApp/"]
RUN dotnet restore "JenkinsApp/JenkinsApp.csproj"
COPY . .
WORKDIR "/src/JenkinsApp"
RUN dotnet build "JenkinsApp.csproj" -c Release -o /app/build

FROM build AS publish
RUN dotnet publish "JenkinsApp.csproj" -c Release -o /app/publish /p:UseAppHost=false

FROM base AS final
WORKDIR /app
COPY --from=publish /app/publish .
ENTRYPOINT ["dotnet", "JenkinsApp.dll"]