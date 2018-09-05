# Snippets
Some usefull snippets


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


### ASP NET MVC4 with OpenID and Owin
1. Startup.cs
2. [assembly: OwinStartup(typeof(Startup))] over namespace
3. 
```c#

public void Configuration(IAppBuilder app)
        {
            AntiForgeryConfig.UniqueClaimTypeIdentifier = JwtClaimTypes.Name;

            app.UseCookieAuthentication(new CookieAuthenticationOptions
            {
                AuthenticationType = "Cookies"
            });

            app.UseOpenIdConnectAuthentication(new OpenIdConnectAuthenticationOptions
            {
                Authority = "https://{authority}.com",
                ClientId = "client",
                RedirectUri = "https://{redirectUri}:{port}/",
                ResponseType = "code id_token token",
                SignInAsAuthenticationType = "Cookies",
                Scope = "scope scope scope",
                Notifications = new OpenIdConnectAuthenticationNotifications
                {
                    AuthorizationCodeReceived = AuthorizationCallback
                }
            });
        }
        
        private Task AuthorizationCallback(AuthorizationCodeReceivedNotification message)
        {
            // handle sign in
            return Task.CompletedTask;
        }

```

