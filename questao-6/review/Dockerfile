FROM mcr.microsoft.com/dotnet/aspnet:5.0.4 AS base
WORKDIR /app
EXPOSE 8282

FROM mcr.microsoft.com/dotnet/sdk:5.0 AS build
WORKDIR /app
COPY ./src/*.sln ./
COPY ./src/Review.Web/*.csproj ./Review.Web/
RUN dotnet restore
COPY ./src/Review.Web/ ./Review.Web/
WORKDIR /app/Review.Web/
RUN dotnet publish -c Release -o /app/out

FROM base AS final
WORKDIR /app
COPY --from=build /app/out ./
ENTRYPOINT ["dotnet", "Review.Web.dll"]
