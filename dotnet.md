.NET
======

# Nuget
## Updating Packages
### Nuget Package Manager Console
With the Nuget Package Manager console, you can update all packages in a project (or solution I think) with
```powershell
Update-Package -Include-Prerelease
```

### dotnet-outdated
I believe you cannot update all packages in a project with the dotnet CLI, surprisingly, but you can use [dotnet-outdated-tool](https://github.com/dotnet-outdated/dotnet-outdated).

Install:
```bash
dotnet tool update --global dotnet-outdated-tool
```

Preview changes:
```bash
dotnet-outdated -pre Always
```

Make changes
```bash
dotnet-outdated -pre Always -u
```