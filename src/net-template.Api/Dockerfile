FROM mcr.microsoft.com/dotnet/aspnet:6.0 AS base
WORKDIR /app
EXPOSE 80
EXPOSE 443

FROM mcr.microsoft.com/dotnet/sdk:6.0 AS build
WORKDIR /src
COPY ["net-template.Api.csproj", "."]
RUN dotnet restore "./net-template.Api.csproj"
COPY . .
WORKDIR "/src/."
RUN dotnet build "net-template.Api.csproj" -c Release -o /app/build

FROM build AS publish
RUN dotnet publish "net-template.Api.csproj" -c Release -o /app/publish /p:UseAppHost=false

FROM base AS final
WORKDIR /app
COPY --from=publish /app/publish .
ENTRYPOINT ["dotnet", "net-template.Api.dll"]
