---
author_name: Adrian Hall (MSFT)
layout: post
hide_excerpt: true
---
      [Adrian Hall (MSFT)](https://social.msdn.microsoft.com/profile/Adrian Hall (MSFT))  1/10/2017 5:03:53 PM  Today, we are releasing two new .NET SDK releases - [v2.0.0](http://www.nuget.org/packages/Microsoft.Azure.Mobile.Server/) on the server side and [v3.1.0](http://www.nuget.org/packages/Microsoft.Azure.Mobile.Client/) on the client side. The NuGet packages are available from the [main NuGet repository](http://www.nuget.org/) and the symbols have been updated on [symbolsource](http://www.symbolsource.org/Public/Home/VisualStudio). ### Azure Mobile Apps ASP.NET Server SDK v2.0.0

 It's been a while since we updated the [ASP.NET Server SDK](https://docs.microsoft.com/en-us/azure/app-service-mobile/app-service-mobile-dotnet-backend-how-to-use-server-sdk). We've updated the base framework that we use to .NET Framework 4.6 and updated all the dependencies so that we are using the latest versions that we can while maintaining compatibility as a protocol level. In addition, we have deprecated the Azure Notification Hubs push registration endpoint. This is still included in the package, but marked as Obsolete and will be removed in a future version. You should use the App Service Push endpoint instead. In your ASP.NET Owin Startup class, you can remove the reference to .AddPushNotifications() from the configuration. App Service Push has been significantly enhanced over the last couple of months. It now supports white-listing of tags and automatic addition of tags based on authenticated claims available from the authentication provider. This lays the groundwork for re-introducing tag support into the client SDKs in a future release. In the interim, you can build your own Notification Hub Installation class and submit that via the .InvokeApiAsync() method. For examples on this, check out Chapter 5 of my [Azure Mobile Apps book](http://aka.ms/zumobook). We are also releasing the [Swagger](https://github.com/Azure/azure-mobile-apps-net-server/wiki/Adding-Swagger-Metadata-and-Help-UI-to-a-Mobile-App) and Custom Authentication packages as generally available. You can read about the Swagger customization on our [Wiki](https://github.com/Azure/azure-mobile-apps-net-server/wiki/Adding-Swagger-Metadata-and-Help-UI-to-a-Mobile-App). Finally, we've also been working behind the scenes on updating the Azure Storage SDK, updating our testing and build processes so that those are more aptly done in the public, publishing more topics to our [Wiki](https://github.com/Azure/azure-mobile-apps-net-server/wiki/Adding-Swagger-Metadata-and-Help-UI-to-a-Mobile-App) and adding information to our documentation. ### Azure Mobile Apps Client SDK v3.1.0

 The [Client SDK](https://docs.microsoft.com/en-us/azure/app-service-mobile/app-service-mobile-dotnet-how-to-use-client-library) has had the following updates since the last update:  - ([#266](https://github.com/Azure/azure-mobile-apps-net-client/issues/266)) A bug that caused problems when two libraries both used SQLite. This was fixed by updating the dependency on the SQLitePCL.raw to the latest version. Thanks to [Eric Sink](https://github.com/ericsink) for the fast turnaround on the fix for this, and for providing an awesome open source project that we can leverage here.
 - ([#215](https://github.com/Azure/azure-mobile-apps-net-client/issues/215)) We were inconsistent in the generation of GUID style primary keys between the client and server. We've standardized the production of keys to a hyphen-less version.
 - ([#196](https://github.com/Azure/azure-mobile-apps-net-client/issues/196)) We had a method for querying the underlying SQLite store that was not exposed. Sometimes, it's good to do queries against the raw tables stored in SQLite. We now expose the SQLiteStore.ExecuteQueryAsync() method that does the appropriate locking to ensure the operation is safe.
  We've also done numerous documentation updates and will be updating the SDK documentation on the MSDN site soon. As always, you can ask questions on both of these SDKs on [Stack Overflow](http://stackoverflow.com/questions/tagged/azure-mobile-services) or [Azure Forums](https://social.msdn.microsoft.com/forums/en-US/home?forum=azuremobile&filter=alltypes&sort=lastpostdesc), or file questions and issues at the GitHub repositories ([Server](https://github.com/Azure/azure-mobile-apps-net-server/issues) and [Client](https://github.com/Azure/azure-mobile-apps-net-client/issues)). ### Read the Book

 On the "more documentation" front, I've been hard at work writing the Azure Mobile Apps book for C#, covering the ASP.NET server and Xamarin cross-platform development. It is nearing completion and all the "development" topics have been completed. You can find the book at <http://aka.ms/zumobook>. I would appreciate your feedback on the topics, especially where information is missing. You can file issues at [the GitHub repository](https://github.com/adrianhall/develop-mobile-apps-with-csharp-and-azure/issues).     