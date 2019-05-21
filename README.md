# Modern Share Migrator

## Deployment
### Register an application in Azure Active Directory

#### Add a new app registration in Azure Active Directory
1. Login to your [Azure Portal](http://portal.azure.com/) with an Admin Account.
2. Navigate to **Azure Active Directory**
3. Choose **App registrations**
4. Click **New registration**
5. Set supported account types to **Accounts in this organizational directory only**
6. Set the redirect URI to the app service URL of **Modern Share Migrator** 
![Screenshot](./docs/images/aadAppRegistration.png)
7. Save the **Application (client) ID** somewhere because you will need it for the deployment
![Screenshot](./docs/images/aadAppOverview.png)

> Note: 
> Redirect URI: https://[your app service name].azurewebsites.net/**signin-oidc**
>

#### Manage authentication
1. Select the **Authentication** blade
![Screenshot](./docs/images/authentication1.png)
2. Check **ID tokens** in the **Advaned settings** section
![Screenshot](./docs/images/authentication.png)
3. Save your changes
4. Ensure the redirect URI is valid!

#### Create a client secret
1. Select the **Certificates & secrets** blade
![Screenshot](./docs/images/certsSecrets.png)
2. Add a new client secret with **New client secret**
![Screenshot](./docs/images/newSecret.png)
3. Define a Description and set expiration to **Never**
4. Save the generated secret somewhere because you are not able to look it up again

#### Set API permissions
1. Select the **API permissions** blade
2. Click **Add a permission** to grant required permissions
3. Select **Microsoft Graph**
4. Expand **Group** and check **Group.ReadWrite.All**
5. Expand **User** and check **User.Read.All** and confirm with **Add permission**
6. Click **Grant admin consent** and confirm the displayed dialog with **Yes**
![Screenshot](./docs/images/api-permissions.png)

### Deploy to Azure

When the app registration is done use this button to deploy **Modern Share Migrator** to your Azure subscription.
#### Prod
<a href="https://portal.azure.com/#create/Microsoft.Template/uri/https%3A%2F%2Fraw.githubusercontent.com%2Fglueckkanja%2Fgk-modernsharemigrator%2Fmaster%2Fazuredeploy.json" target="_blank">
    <img src="http://azuredeploy.net/deploybutton.png"/>
</a>

#### Beta
<a href="https://portal.azure.com/#create/Microsoft.Template/uri/https%3A%2F%2Fraw.githubusercontent.com%2Fglueckkanja%2Fgk-modernsharemigrator%2Fmaster%2Fazuredeploy-beta.json" target="_blank">
    <img src="http://azuredeploy.net/deploybutton.png"/>
</a>
