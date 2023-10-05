# FusionAuth Templates for .NET
Quickly create new secured .NET applications with FusionAuth Templates, using the .NET CLI or Visual Studio. The new applications are pre-configured to use FusionAuth for authentication and authorization. Only standard .NET libraries are used for authentication and authorization.

Currently, the following .NET templates are implemented:

* FusionAuth Blazor Server Application
* FusionAuth MVC Application
* FusionAuth Web API Application

To learn how to install and use the templates, check out the [FusionAuth Templates for .NET guide](https://fusionauth.io/docs/v1/tech/client-libraries/netcore).

## NuGet Package

The base templates are created as NuGet packages.

### Building NuGet Package and Installing From Source

To build and install the FusionAuth Templates from the source code, follow these steps:

1. [Clone](https://docs.github.com/en/repositories/creating-and-managing-repositories/cloning-a-repository) this repository onto your local machine.

2. Build a NuGet package by executing the following command in the root folder of the project:

   ```bash
   dotnet pack
   ```

   This will create a NuGet package in the `./bin/Debug/` folder.

3. Install the templates by running the following command:

   ```bash
   dotnet new install ./bin/Debug/FusionAuth.Templates.1.0.0.nupkg
   ```

### Publishing NuGet Package

Use the .nupkg file and follow the instructions to [publish a nuget package](https://learn.microsoft.com/en-us/nuget/nuget-org/publish-a-package).

### Uninstalling NuGet Package

You can uninstall the templates using the following command:

   ```bash
   dotnet new uninstall FusionAuth.Templates
   ```
You will need to restart Visual Studio for the changes to take effect.

## VSIX Installer

In order to deploy the templates to the Visual Studio Marketplace, a .vsix file will need to be created.

1. Build the Nuget package as described above. This will produce `\bin\Debug\FusionAuth.Templates.1.0.0.nupkg`.
   
2. Open the `.\VsixProject\FusionAuthVisualStudioTemplates.sln` solution in Visual Studio and build the project. Alternatively, you can use MSBuild at the command line.
   I.E.
   ```
   MSBuild "C:\dev\fusionauth-dotnet-templates\VsixProject\FusionAuthVisualStudioTemplates\FusionAuthVisualStudioTemplates.csproj" -p:Configuration=Release
   ```
   This will create the `FusionAuthVisualStudioTemplates.vsix` file in the `...\FusionAuthVisualStudioTemplates\bin\Release` directory. (If you build in Visual Studio, you will need to set the configuration for the build manually) You may need to go into the project and update the vesion in the `source.extension.vsixmanifest` file.
   
3. Go to https://marketplace.visualstudio.com/ and sign in with the appropriate account. Click on the three dots next to the `FusionAUth Visual Studio Templates` extenstion. Select `edit`. Upload newly created extenstion and update information.

(Note: I had trouble uploading the extension to the marketplace using Chrome. When I tried with Edge, it worked fine.)

## License

This project is licensed under the [Apache license](License.txt).
