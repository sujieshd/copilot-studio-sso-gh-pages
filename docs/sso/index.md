# Single Sign-On (SSO) Configuration

This section provides detailed instructions on how to configure Single Sign-On (SSO) for your application using Microsoft Copilot Studio. Follow the steps outlined below to ensure a successful setup.

## Prerequisites

Before you begin, ensure that you have the following:

- An active Microsoft account.
- Access to the Azure portal.
- Necessary permissions to configure SSO settings.

## Step-by-Step Guide

1. **Access the Azure Portal**
   - Log in to the [Azure portal](https://portal.azure.com/).
   - Navigate to the "Azure Active Directory" section.

2. **Register Your Application**
   - Click on "App registrations" and then "New registration".
   - Fill in the required details such as the name of your application and redirect URI.
   - Click "Register" to create the application.

3. **Configure SSO Settings**
   - After registration, go to the "Authentication" section.
   - Under "Platform configurations", add a new platform and select "Web".
   - Enter the redirect URI and configure other settings as needed.

4. **Set Up User Attributes and Claims**
   - Navigate to the "Token configuration" section.
   - Click on "Add group claim" and configure the claims as per your requirements.

5. **Test the SSO Configuration**
   - Use the provided test tools in the Azure portal to verify that the SSO configuration is working correctly.
   - Ensure that users can log in using their Microsoft accounts.

## Additional Resources

- [Microsoft Documentation on SSO](https://docs.microsoft.com/en-us/azure/active-directory/develop/quickstart-v2-aspnet)
- [Troubleshooting SSO Issues](troubleshooting.md)

For any further assistance, please refer to the troubleshooting section or contact support.