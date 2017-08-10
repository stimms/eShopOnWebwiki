# Deploying to Azure App Service

To deploy the eShopOnWeb sample to an Azure App Service, starting in the Azure Portal, follow these step-by-step instructions (or, [deploy to Azure directly from from Visual Studio 2017](https://github.com/dotnet-architecture/eShopOnWeb/wiki/Deploying-to-Azure-App-Service-from-VS2017)):

1. Clone or download the eShopOnWeb sample to a folder on your local machine.

2. Log in to the [Azure Portal](https://portal.azure.com/) with your Microsoft Account.

3. Click the `+` icon, then select `Web App`. Provide an `App name`.

![image](https://user-images.githubusercontent.com/782127/29045504-c8f96ab4-7b91-11e7-9679-34c49f5815d1.png)

4. Choose a new resource group name or select an existing one, then click `Create`. In a few moments you should see that the deployment was successful.

![image](https://user-images.githubusercontent.com/782127/29045678-6487bd6e-7b92-11e7-92a7-38677683aae8.png)

5. Select `Get publish profile`.

![image](https://user-images.githubusercontent.com/782127/29045764-bc07e410-7b92-11e7-9e0f-7b8c78a05a84.png)

6. Copy the `.PublishSettings` file to the `eShopOnWeb/src/Web` folder.

![image](https://user-images.githubusercontent.com/782127/29045952-6561799a-7b93-11e7-8f14-05b4bae27793.png)

7. Open the `eShopOnWeb.sln` solution file.

8. Right-click on the `Web` project and select `Publish`. Select `Import profile`. Click `OK`.

![image](https://user-images.githubusercontent.com/782127/29046255-a1567d14-7b94-11e7-9ba9-cc5fd5848cb3.png)

9. Select the `.PublishSettings` file you saved in the `eShopOnWeb/src/Web` folder. You should see something like this:

![image](https://user-images.githubusercontent.com/782127/29046302-df70b4ca-7b94-11e7-97a3-199570a1b201.png)

10. Click `Publish`. You should see files being copied. When the publish process completes, the site should open in your browser.

## Optional

If you are not seeing data initially in the store, the most likely reason is that the Azure App Service is configured for `Production`, not `Development` (**Note:** This is not the same as `Debug` vs. `Release` configuration). The sample data is only seeded in the `Development` environment. You can configure the App Service to run in `Development` as follows:

1. In the Azure Portal, navigate to your Web App.

2. Click Application settings.

3. Scroll down to App settings.

4. Add a new key `ASPNETCORE_ENVIRONMENT` with value `Development`.

5. Click `Save`.

![image](https://user-images.githubusercontent.com/782127/29046500-bdd6428e-7b95-11e7-9549-e2b2b728c062.png)

At this point, you should be able to refresh the site and see it loaded with data (if not, publish once more from Visual Studio).

![image](https://user-images.githubusercontent.com/782127/29046690-9530671e-7b96-11e7-9425-bd2223ddbe02.png)



