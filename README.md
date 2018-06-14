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

### URL Localization  root/en-US/Index
https://andrewlock.net/url-culture-provider-using-middleware-as-mvc-filter-in-asp-net-core-1-1-0/

### Zeitspannen / Lücken / Überschneidungen
https://www.codeproject.com/Articles/168662/Time-Period-Library-for-NET

### Slack-Integration
https://www.c-sharpcorner.com/UploadFile/bfb43a/integration-with-slack-using-C-Sharp/

