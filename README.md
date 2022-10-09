---
topic: HTML Hello World
languages:
  - HTML
products:
  - Azure App Service
  - Azure Web Apps
---

# HTML Hello World

This sample demonstrates a tiny Hello World HTML app for [App Service](https://docs.microsoft.com/azure/app-service).

# Azure

##### Configure static website hosting
The first step is to configure your storage account to host a static website in the Azure portal. When you configure your account for static website hosting, Azure Storage automatically creates a container named $web. The $web container will contain the files for your static website.

- Open the Azure portal in your web browser.
- Locate your storage account and display the account overview.
- Select Static website to display the configuration page for static websites.
- Select Enabled to enable static website hosting for the storage account.

In the Index document name field, specify a default index page of index.html. The default index page is displayed when a user navigates to the root of your static website.

In the Error document path field, specify a default error page of 404.html. The default error page is displayed when a user attempts to navigate to a page that does not exist in your static website.

- Click Save. The Azure portal now displays your static website endpoint.

# Create website/web app

- Navigate to your development folder on your local hard drive (i.e. C:\development)
- mkdir quickstart
- cd quickstart
- git clone https://github.com/Azure-Samples/html-docs-hello-world.git
- cd html-docs-hello-world
- ls
- mkdir src
- mv css/ js/ fonts/ img/ to src folder
- Open index.html and prepend all css/ js/ fonts/ img/ location with src/

# Parcel
Building a web app with Parcel
https://parceljs.org/getting-started/webapp/

##### Create a package.json
- npm init

Before we get started, you'll need to install Node and Yarn or npm, and create a directory for your project. 

- npm install --save-dev parcel

Parcel has a development server built in, which will automatically rebuild your app as you make changes. To start it, run the parcel CLI pointing to your entry file:

- npx parcel index.html

##### Package scripts
So far, we’ve been running the parcel CLI directly, but it can be useful to create some scripts in your package.json file to make this easier. We'll also setup a script to build your app for production using the parcel build command. Finally, you can also declare your entries in a single place using the source field so you don't need to duplicate them in each parcel command.

```json
{
  "name": "my-project",
  "source": "index.html",
  "scripts": {
    "start": "parcel",
    "build": "parcel build"
  },
  "devDependencies": {
    "parcel": "latest"
  }
}
```

Now you can run yarn build to build your project for production and yarn start to start the development server.

- npx parcel build

##### Deploy to Azure

Locate your storage account and display the account overview.

- Click on Containers
- Click on $web
- Click on Upload
- Select Files ( a dialog window sould appear)

Navigate to the dist folder and select all files

- Click Open button on Dialog window
- Click Upload

##### Test Website

Locate your storage account and display the account overview.

- Select Static website to display the configuration page for static websites.
- Copy Primary endpoint and paste in Web Browser to view web app


