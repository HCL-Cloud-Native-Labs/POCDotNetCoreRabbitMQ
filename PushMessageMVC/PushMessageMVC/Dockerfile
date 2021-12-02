#See https://aka.ms/containerfastmode to understand how Visual Studio uses this Dockerfile to build your images for faster debugging.

FROM mcr.microsoft.com/dotnet/aspnet:6.0 AS base
WORKDIR /app
EXPOSE 80
EXPOSE 443

FROM mcr.microsoft.com/dotnet/sdk:6.0 AS build
WORKDIR /src
COPY ["PushMessageMVC/PushMessageMVC.csproj", "PushMessageMVC/"]
RUN dotnet restore "PushMessageMVC/PushMessageMVC.csproj"
COPY . .
WORKDIR "/src/PushMessageMVC"
RUN dotnet build "PushMessageMVC.csproj" -c Release -o /app/build

FROM build AS publish
RUN dotnet publish "PushMessageMVC.csproj" -c Release -o /app/publish

FROM base AS final
WORKDIR /app
COPY --from=publish /app/publish .
ENTRYPOINT ["dotnet", "PushMessageMVC.dll"]