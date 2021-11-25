FROM mcr.microsoft.com/dotnet/sdk:5.0-alpine

WORKDIR /src

COPY . .

RUN dotnet restore
RUN dotnet build -c Release
RUN dotnet test -c Release
RUN dotnet publish -c Release -o /dist

ENV ASPNETCORE_ENVIRONMENT Production
ENV ASPNETCORE_URLS http://+:5000
EXPOSE 5000

WORKDIR /dist
CMD ["dotnet", "NetApi.dll"]