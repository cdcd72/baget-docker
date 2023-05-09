# baget-docker

Run [BaGet](https://github.com/loic-sharma/BaGet) nuget server with docker-compose.

# How to run

1. Modify your api key in docker-compose.yaml.

2. Start your baget nuget server.

   ```cmd
   docker compose up -d
   ```

# Push nuget package

```cmd
dotnet nuget push your-package-name.nupkg -s "http://localhost:5555/v3/index.json" -k "your-api-key"
```

# Pull nuget package

```cmd
dotnet nuget add source "http://localhost:5555/v3/index.json" -n "baget"
```

or directly edit NuGet.Config

```
<?xml version="1.0" encoding="utf-8"?>
<configuration>
  <packageSources>
	<add key="baget" value="http://localhost:5555/v3/index.json" />
  </packageSources>
</configuration>
```

# Reference

- https://loic-sharma.github.io/BaGet/installation/docker
