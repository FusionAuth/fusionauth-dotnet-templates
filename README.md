# FusionAuth Templates for .NET
Quickly create new secured .NET applications with FusionAuth Templates, using the .NET CLI or Visual Studio. The new applications are pre-configured to use FusionAuth for authentication and authorization. Only standard .NET libraries are used for authentication and authorization.

Currently, the following .NET templates are implemented:

* FusionAuth Blazor Server Application
* FusionAuth MVC Application
* FusionAuth Web API Application

To learn how to install and use the templates, check out the [FusionAuth Templates for .NET guide](https://fusionauth.io/docs/v1/tech/client-libraries/netcore).

## Building and Installing from source

To build and install the FusionAuth Templates from the source code, follow these steps:

1.[Clone](https://docs.github.com/en/repositories/creating-and-managing-repositories/cloning-a-repository) this repository onto your local machine.

2. Build a NuGet package by executing the following command in the root folder of the project:

   ```bash
   dotnet pack
   ```

   This will create a NuGet package in the `./bin/Debug/` folder.

3. Install the templates by running the following command:

   ```bash
   dotnet new install ./bin/Debug/FusionAuth.Templates.1.0.0.nupkg
   ```

## Publish

Use the .nupkg file and follow the instructions to [publish a nuget package](https://learn.microsoft.com/en-us/nuget/nuget-org/publish-a-package).

## Uninstalling

You can uninstall the templates using the following command:

   ```bash
   dotnet new uninstall FusionAuth.Templates
   ```
You will need to restart Visual Studio for the changes to take effect.


## License

This project is licensed under the [Apache license](License.txt).