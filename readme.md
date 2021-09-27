## Minimal repo to reproduce https://github.com/dotnet/aspnetcore/issues/35345

# Steps to reproduce the issue

- Build the `RazorClassLibrary` project (in VS, right-click -> `Build`)
- Run the following command in the `MyBlazorApp` folder: `dotnet publish`

This error pops-up:
> C:\Program Files\dotnet\sdk\6.0.100-rc.1.21463.6\Microsoft.Common.CurrentVersion.targets(5109,5): error MSB3030: Could not copy the file "C:\path\to\repo\StaticWebAssetsBug\RazorClassLibrary\obj\Debug\net5.0\staticwebassets\RazorClassLibrary.StaticWebAssets.xml" because it was not found. [C:\path\to\repo\StaticWebAssetsBug\MyBlazorApp\MyBlazorApp.csproj]

Running `dotnet publish` a second time works fine.

# How to create this repo?

- Create a templated Blazor App
- Add a templated Razor Component Library
- Refernce the RCL from the app and use a component from it.