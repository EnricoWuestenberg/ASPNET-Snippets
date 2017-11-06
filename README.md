# ASPNET-Snippets
Some usefull snippets for ASPNET


### ServiceCollection: Add customize option from multi sections in IConfiguration
```C#
services.AddOptions();
services.Configure<ApplicationOption>(
    configOptions =>
    {
        Configuration.GetSection("ConfigStrings").Bind(configOptions.ProviderOptions);
        Configuration.GetSection("ConfigStrings").Bind(configOptions.SecretOptions);
        Configuration.GetSection("ConfigStrings").Bind(configOptions.AccountOptions);
    });
    
```
### Testing ASP.NET appsettings.json
https://github.com/aspnet/Configuration/blob/290b4989d409db0f3d73db93b2c1d2cd81a157a5/test/Microsoft.Extensions.Configuration.Json.Test/ArrayTest.cs#L192-L193

