# ASPNET-Snippets
Some usefull snippets fpr ASPNET


### ServiceCollection: Add customize option from multi sections in IConfiguration
```C#
services.AddOptions();
services.Configure<ApplicationOption>(
    configOptions =>
    {
        Configuration.GetSection(ConfigStrings.Providers).Bind(configOptions.ProviderOptions);
        Configuration.GetSection(ConfigStrings.ProviderSecrets).Bind(configOptions.SecretOptions);
        Configuration.GetSection(ConfigStrings.AccountOptions).Bind(configOptions.AccountOptions);
    });
