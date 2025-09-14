---
title: SSO
---
In this document we will learn about the implementation of Azure AD SSO in Swimm.

SSO stands for Single Sign On, which means a service that centralizes all of the sign on to all SaaS services in one place, making it easier to provision and block applications and employees in a centralized manner.\
&nbsp;The biggest company that offers these kind of services is Okta and another is Azure Active Directory.

Our implementation of SSO in Swimm allows users to sign in to Swimm using their existing SSO credentials, requiring that SSO enabled domains will sign in using the service, and logging users out while their session expires.

# How do I add a new SSO client

## Client Guide - How to create an Azure AD Application for Swimm

To add a new SSO client you'll need to ask the client to create an SSO application on their Azure Active Directory instance, by going to "App Registration" in the Azure Active Directory Admin and clicking "New registration"

&nbsp;

<p align="center"><img src="https://firebasestorage.googleapis.com/v0/b/swimmio-content/o/repositories%2FveezvxCuzpPrRLLXWD2E%2F7e5e44f1-4b27-4d19-a77e-a2ba54bae46d.png?alt=media&amp;token=bf681e4a-64b0-4053-9468-36fc9c311f52"></p>

Then writing down "Swimm" as the name and select Single tenant or Multiple tenants according to your organization set up

&nbsp;

<p align="center"><img src="https://firebasestorage.googleapis.com/v0/b/swimmio-content/o/repositories%2FveezvxCuzpPrRLLXWD2E%2F253ec485-0184-40ab-986e-787ce571f804.png?alt=media&amp;token=2d6932a5-9ef3-4737-ae06-507dab5972d2"></p>

Then under redirect URI select Single Page Application and write down <https://app.swimm.io/sso> and click register

&nbsp;

<p align="center"><img src="https://firebasestorage.googleapis.com/v0/b/swimmio-content/o/repositories%2FveezvxCuzpPrRLLXWD2E%2Fe97e6328-9825-40dc-9825-83b7cfee7d15.png?alt=media&amp;token=32e2dee3-3f57-4632-b80d-a3af51110ee4"></p>

Next, you can click endpoints and copy the URL under OpenID Connect metadata document and save it for later, Swimm would need it.

&nbsp;

<p align="center"><img src="https://firebasestorage.googleapis.com/v0/b/swimmio-content/o/repositories%2FveezvxCuzpPrRLLXWD2E%2Fe4ecf6db-d69a-4f89-b0c0-e647935d5df1.png?alt=media&amp;token=aa3047b0-e30e-4153-9ea6-e11dbff4fa7c"></p>

After that you can then go the "API permissions" make sure User.Read permissions is set and then click on "add permission"

&nbsp;

<p align="center"><img src="https://firebasestorage.googleapis.com/v0/b/swimmio-content/o/repositories%2FveezvxCuzpPrRLLXWD2E%2F1f5e7136-6563-4398-a455-4b11040e853c.png?alt=media&amp;token=dd8a63f5-c119-4f97-be3f-d130dd524691"></p>

Select "Microsoft Graph" and then "Delegated Permissions"

&nbsp;

<p align="center"><img src="https://firebasestorage.googleapis.com/v0/b/swimmio-content/o/repositories%2FveezvxCuzpPrRLLXWD2E%2F07454e83-1add-4551-9a59-618e6c798628.png?alt=media&amp;token=2cbcd245-4aec-42b2-8c85-90b7f5b3b7a7"></p>

&nbsp;

<p align="center"><img src="https://firebasestorage.googleapis.com/v0/b/swimmio-content/o/repositories%2FveezvxCuzpPrRLLXWD2E%2F3c232556-a5e4-465b-8219-f2571841536a.png?alt=media&amp;token=1976815c-5af9-47fe-a517-b09e672e4d21"></p>

And select the 4 Openid permissions and click "Add permissions"

&nbsp;

<p align="center"><img src="https://firebasestorage.googleapis.com/v0/b/swimmio-content/o/repositories%2FveezvxCuzpPrRLLXWD2E%2F0b88b719-aef7-46eb-8e5d-5f29af18a997.png?alt=media&amp;token=70b92ff2-3d1d-4e34-a67d-bc9236701db4"></p>

Finally make sure to "Grant admin consent to Default Directory"

&nbsp;

<p align="center"><img src="https://firebasestorage.googleapis.com/v0/b/swimmio-content/o/repositories%2FveezvxCuzpPrRLLXWD2E%2F048de69d-7649-4879-9147-a93807d954fc.png?alt=media&amp;token=8be4bc71-654f-4a3d-9e23-fa46bbac8756"></p>

You can then go to Branding and properties and add the Swimm logo (squarelogo.png) and homepage (<https://app.swimm.io>)

&nbsp;

<p align="center"><img src="https://firebasestorage.googleapis.com/v0/b/swimmio-content/o/repositories%2FveezvxCuzpPrRLLXWD2E%2F9556e695-0549-4f3c-a685-e890b09a0ba2.png?alt=media&amp;token=55a5bc6f-beb9-41ab-b4cd-1177c51a8737"></p>

Finally, you can go back to the main Azure Active Directory page and then to the Enterprise Applications page and select the Swimm Application and under properties make sure the assignment required is set to Yes

&nbsp;

<p align="center"><img src="https://firebasestorage.googleapis.com/v0/b/swimmio-content/o/repositories%2FveezvxCuzpPrRLLXWD2E%2Fc6cd5011-b95c-4d30-acad-50521edddbde.png?alt=media&amp;token=e2e73b70-7baa-49e6-b5e2-236685ed6f53"></p>

&nbsp;

<p align="center"><img src="https://firebasestorage.googleapis.com/v0/b/swimmio-content/o/repositories%2FveezvxCuzpPrRLLXWD2E%2Fcbe43541-596f-4d2a-a78e-516cd070a85c.png?alt=media&amp;token=1ae0fcaf-38fa-4299-8605-637ef0974cdc"></p>

&nbsp;

<p align="center"><img src="https://firebasestorage.googleapis.com/v0/b/swimmio-content/o/repositories%2FveezvxCuzpPrRLLXWD2E%2F8141e469-aa2c-4b36-b919-5cab19803205.png?alt=media&amp;token=bd5cfb44-0959-4bf2-9650-86b74180c193"></p>

And on the App Overview page (still under Enterprise Applications) you can copy the Client Id, the Object Id which Swimm would need.

And that's it, once you pass the Client Id, Object Id and OpenId Metadata URL to the Swimm team, we'll allow you to require SSO for all users under your domain, please let us know what is the domain your employees use as we don't have automatic provisioning set up just yet.

# Swimm - How to set the details from the Client

## Firebase

Once the client has given us the details the first thing we'll need to do is to create the Firebase authentication set up, to do that, you'll have to go into Firebase -> Authentication -> Sign In method, and click on add new Provider.

&nbsp;

<p align="center"><img src="https://firebasestorage.googleapis.com/v0/b/swimmio-content/o/repositories%2FveezvxCuzpPrRLLXWD2E%2F0cc0c414-dcd7-41f2-80cc-bbbc759af438.png?alt=media&amp;token=a3981f4d-1962-42d1-bb82-201acf3039fe"></p>

The Select Open ID Connect under Custom Providers

&nbsp;

<p align="center"><img src="https://firebasestorage.googleapis.com/v0/b/swimmio-content/o/repositories%2FveezvxCuzpPrRLLXWD2E%2Ff705fbdf-1573-4e19-b313-eafc25d48d7c.png?alt=media&amp;token=cbce3c1a-ef62-4dd1-9b79-8cf8ef304a5f"></p>

1. **Grant Type**

   - Select **implicit_flow (id_token)**.

2. **Name**

   - Make sure the name starts with **SSO**, followed by the company name.

   - Example: `SSO Swimm` (this makes it easier to identify).

3. **Client ID**

   - Use the **Client ID** you received previously.

4. **Issuer URL**

   - Example: `https://login.microsoftonline.com/{tenantID}/v2.0`

&nbsp;

<p align="center"><img src="https://app.swimm.io/storage/v0/b/swimmio-content/o/repositories%2FveezvxCuzpPrRLLXWD2E%2F57db4d3a-c7b6-4f0c-8320-017ab8d12400.png?alt=media&amp;token=1caa3394-5f49-4f75-94f4-11e0ae9fb306"></p>

Then click Next and Save.

Please remember the **provider id** that was set for you in firebase (oide.sso-swimm in our case) as we'll need it later.

As the next step, we need to add a new secret to the Google Cloud Secret Manager.

## Google Cloud Secret Manager

1. Open [google cloud](https://console.cloud.google.com/welcome)
2. Search for Secret Manager

&nbsp;

<p align="center"><img src="https://app.swimm.io/storage/v0/b/swimmio-content/o/repositories%2FveezvxCuzpPrRLLXWD2E%2Feccb28ee-a1e9-45ce-ae4e-9dca9f5d91a2.png?alt=media&amp;token=fb56c63f-a7d5-4093-b486-55fbe6691dc3"></p>

3. Click 'Create secret'
   1. &nbsp;

      &nbsp;

      <p align="center"><img src="https://app.swimm.io/storage/v0/b/swimmio-content/o/repositories%2FveezvxCuzpPrRLLXWD2E%2F801399f9-a90d-4230-81f1-5de68f616239.png?alt=media&amp;token=c0ac7a85-f15e-4d1d-92c3-e24a7a4e4299"></p>
4. add name in this format  SSO\_{publisher provider}
   1. our publisher provider is [swimm.io](http://swimm.io) the name should be SSO_SWIMM_IO&nbsp;
5. Add secret&nbsp;

   ```plaintext
   {
   "issuer":"https://login.microsoftonline.com/{tenantID}",
   "client_id":"{client ID}",
   "auth_name":"{Provider ID}",
   "type":"azure", 
   "object_id":"{Object ID}"
   }
   ```
6. **Location of the relevant data required for the secret**
   1. Go to **Azure Portal**.
      1. Navigate to **App registrations**.
      2. Select the **relevant application**.
      3. Go to the **Overview** tab.
      4. The relevant data will be visible, including:
         - **Tenant ID**

         - **Client ID**

         - **Object ID**

           &nbsp;

           <p align="center"><img src="https://app.swimm.io/storage/v0/b/swimmio-content/o/repositories%2FveezvxCuzpPrRLLXWD2E%2F5d3f8c30-a9f5-4651-af2e-41cda4f12533.png?alt=media&amp;token=515c9601-c505-48f4-b47c-4ea9bd8e057b"></p>

         - Firebase

           1. Provider ID&nbsp;

              &nbsp;

              <p align="center"><img src="https://app.swimm.io/storage/v0/b/swimmio-content/o/repositories%2FveezvxCuzpPrRLLXWD2E%2F7ef421f8-dcfd-4b14-aad8-64f9fc385dbf.png?alt=media&amp;token=0427d311-e50d-459a-bf90-8c0929adad48"></p>

&nbsp;

&nbsp;

# How to test Azure AD SSO accounts?

SSO are a bit tricky as we require them for an entire domain, so having it set for [swimm.io](http://swimm.io) would have caused some frustration for our devs, luckily, Azure Active Directory can add a user with it's own email address, for our instance that address is @giladswimm.onmicrosoft.com , so, in order to test an SSO account on both Staging and Production, try logging in / registering with that kind of email, keep in mind that you should also be an admin on our Azure instance (ask Itai / Shaul / Gilad for permissions), and that you can give / remove access under Applications and then choosing either Swimm Stagingg or Swimm according to if it's staging or prod.\
\
Here is how to create a new user:\
&nbsp;Go to <https://portal.azure.com/#view/Microsoft_AAD_UsersAndTenants/UserManagementMenuBlade/~/AllUsers> - sign in with your Swimm email (like mentioned before, please talk to Itai / Shaul / Gilad for access) and then click on "New user" and "Create new user"

&nbsp;

<p align="center"><img src="https://firebasestorage.googleapis.com/v0/b/swimmio-content/o/repositories%2FveezvxCuzpPrRLLXWD2E%2Fc2816b5a-849a-42e4-96a1-b2aac6aed70c.png?alt=media&amp;token=b43071fd-6e66-44fa-b517-9d77c45a6b05"></p>

Then fill in the details required (you can set a password if you'd like)

&nbsp;

<p align="center"><img src="https://firebasestorage.googleapis.com/v0/b/swimmio-content/o/repositories%2FveezvxCuzpPrRLLXWD2E%2F9e922d9e-b596-4dd4-b889-282b8c2d6bca.png?alt=media&amp;token=535c0378-89d4-4341-b957-a7d94c125a60"></p>

Important! make sure to go to the properties tab and add an email for the user, the same email as you selected ([X@giladswimm.onmicrosoft.com](mailto:X@giladswimm.onmicrosoft.com))

&nbsp;

<p align="center"><img src="https://firebasestorage.googleapis.com/v0/b/swimmio-content/o/repositories%2FveezvxCuzpPrRLLXWD2E%2Fe50834e6-cc31-427c-8049-9d7461805110.png?alt=media&amp;token=b1dc32e7-2650-47c4-8ff1-c58e1e73ac23"></p>

&nbsp;

<p align="center"><img src="https://firebasestorage.googleapis.com/v0/b/swimmio-content/o/repositories%2FveezvxCuzpPrRLLXWD2E%2Fc7988171-cd52-4859-8775-4746f1f2fa9d.png?alt=media&amp;token=908cf09c-dfe4-4fae-9103-2637a6b03a28"></p>

And that's it, you should have a user to test with.

# Known Limitations

We have a few limitations with our current SSO integration:

1. 60-90 minutes deactivation period - this is a Microsoft limitation, when a user has an access token, it can't be revoked until it expires and a refresh attempt is made, that means that if a user is disabled it could take up to an hour and a half until the user is logged out.

2. Email requirement - for some reason, even after updating a user, if they already tried to login to our app and did not have an email we would not receive it from Azure, we tried deactivating, reassigning, to no avail. that's why every provisioned user should have their email property set before logging in.

3. No automatic de-provisioning of users - while we will require all users under a certain domain to have a valid Azure AD session, if a user is removed access from Azure AD, they won't be able to log in, but will still exist in Swimm and have a seat used for the workspace in question, meaning they would still pay for them.

4. No IDE disconnection - when users log into the IDE, we will require they log in with Azure AD, but if the Azure AD session has expired, their IDE session will remain active, while this is not great, the only way for a user to use the IDE is with access to the repo (which also doesn't have a way to be disconnected), so the risk here will happen even if the IDE extension is disconnected since as long as a user has access to the code, they have access to the docs.

5. No marketplace availability - at the moment the Swimm Azure Active Directory App would be created by each enterprise client, which means there is no central place where they can install our app and set everything up on their own, as you can see from the onboarding process mentioned above, since we need to set auth with firebase, automating that process is unlikely without some research and heavy investment.

6. No background disconnection - Firebase only validates auth once people login, and the Azure Active Directory tokens are stored with the user, which means we don't have a webhook or any way to be notified or check when a user session expires aside from polling using the front end on refresh, it means that if someone has a doc open, they would be able to see it until they refresh / their firebase auth is updated, it doesn't really matter, but just something to be aware of.

7. Email domain level requirement - in order to know and prevent users from signing up and disconnecting existing ones, and since each Azure Active Directory integration has a different API endpoint we should check, we need to have a clear criteria to make the decision of whether or not to require SSO, since new users are not part of a workspace, and old users may have used other means of signing up, the best way for us to do so is to look at the email domain of these users, however, this means that users who use an email not under this domain (whether it's a slightly different one, or contractors, etc...) won't be required to log in with SSO, even if they have an Azure Active Directory user.

<SwmMeta version="3.0.0" repo-id="Z2l0aHViJTNBJTNBUUElM0ElM0Fyb2JTd2ltbQ==" repo-name="QA"><sup>Powered by [Swimm](https://staging.swimm.cloud/)</sup></SwmMeta>
