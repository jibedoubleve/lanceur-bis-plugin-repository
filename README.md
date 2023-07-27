# Repository of plugins for Lanceur 2

Here you can find all official plugins for Lanceur 2

## How to publish on this repository

- Create a package `.lpk``
- Clone this repository
- Add your package `<my_package>.lpk` into the repository `plugins`
- Update the file `toc.json`
- Create a PR

### What to add in `toc.json`
```json
{
    "name": "<name_of_plugin>",
    "description": "<small_description_of_the_plugin>",
    "url": "<relative_url_to_the_package_lpk>",
    "version": "<x.x.x>"
}
```

### Automatise packing in solution

1. Add a directory `.build` in your solution and add the script `pack.ps1`
1. Edit the `.csproj` file like this:

```xml
<Target Name="PostBuild" AfterTargets="GetVersion">
    <Exec Command="powershell -NoProfile -ExecutionPolicy RemoteSigned $(ProjectDir).build\pack.ps1 -name $(AssemblyName) -version $(VersionInfo) -output $(ProjectDir)$(OutDir)" />
</Target>

<Target Name="GetVersion" AfterTargets="PostBuildEvent">
    <GetAssemblyIdentity AssemblyFiles="$(TargetPath)">
        <Output TaskParameter="Assemblies" ItemName="AssemblyInfo" />
    </GetAssemblyIdentity>
    <PropertyGroup>
        <VersionInfo>%(AssemblyInfo.Version)</VersionInfo>
    </PropertyGroup>
    <!--And use it after like any other variable:-->
    <Message Text="VersionInfo = $(VersionInfo)" Importance="high" />
</Target>
```

## Further information

 - About [Lanceur 2](https://github.com/jibedoubleve/lanceur-bis)
 - About [how to create a plugin](https://github.com/jibedoubleve/lanceur-bis/wiki/DEV_create_plugin)
