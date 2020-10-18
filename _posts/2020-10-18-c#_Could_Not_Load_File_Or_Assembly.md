# C# Could Not Load File Or Assembly Error

# Brief : 
Recently, while working on a project, I have to upgrade my mvc web app from .Net Framework 4.5 to .Net Famework 4.6 in Visual Studio 2019.I had a fresh installation of Visual Studio 2019 Preview.All seemed good in development/local environment.But when I updated the app on sever (Windows Server),
it gave error like : "Could not load file or assembly "System.Net.Http, Version=4.0.0.0, Culture=neutral, PublicKeyToken=b03f5f7f11d50a3a" or one of its dependencies. The system cannot find the file specified."

> What Worked For Me :
- Removed all binding redirects from web.config.
- Added this to the .csproj file:
- `<PropertyGroup>`
  `<AutoGenerateBindingRedirects>true</AutoGenerateBindingRedirects>`
 `<GenerateBindingRedirectsOutputType>true</GenerateBindingRedirectsOutputType>`
  `</PropertyGroup>`
- ReBuild the project
- Copied the redirects from the (WebAppName).dll.config file to application's web.config file
- Removed the above snipped from the .csproj file (In 2nd Step)
- Error Gone !!
