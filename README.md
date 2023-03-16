# Multi Language Api Custom Extensions

If you like this repository, please drop a :star: on Github!


## Installation

The library is available on [NuGet](https://www.nuget.org/packages/MultiLanguageApiCustomExtensions) or run the following command in the .NET CLI:

```bash
dotnet add package MultiLanguageApiCustomExtensions
```


## Registering services at Startup

```csharp
public Startup(IConfiguration configuration)
{
  Configuration = configuration;
}

public IConfiguration Configuration { get; }
	
public void ConfigureServices(IServiceCollection services)
{
    var supportedCultures = new[] { "en", "it" };
    services.AddSupportedCultures(supportedCultures);
}

//OMISSIS

public void Configure(WebApplication app)
{
    app.UseLocalizationConfiguration();
}
```

Note: The supportedCultures values can be changed to suit your needs.

But remember to create the resx files of the supported languages in the resources folder, setting the access modifier to Public.
