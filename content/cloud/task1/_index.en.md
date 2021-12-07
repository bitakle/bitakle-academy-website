---
title: Task 1
weight: 10
disableToc: true
---

# Azure Static Webpage Hosting

### Objective:

This task is intended to familiarize you with Azure portal and how the resources are provisioned. To complete the task, you will need to provision several Azure resources and upload HTML file to it.

### Instructions:

- Step 1: Sign in to [Azure Portal](https://portal.azure.com) using yor credentials

- Step 2: Create a storage account within new resource group. [Ref](https://docs.microsoft.com/en-us/azure/storage/common/storage-account-create?tabs=azure-portal)

- Step 3: Configure storage account for static website hosting. [Ref](https://docs.microsoft.com/en-us/azure/storage/blobs/storage-blob-static-website-host)

- Step 4: Update this HTML template with custom data and upload it to Storage Blob
    ```html
    <!DOCTYPE html>
    <html>
    <body>

    <h1>My First Heading</h1>
    <p>My first paragraph.</p>

    </body>
    </html>
    ```

- Step 5: Retrieve the FQDN to the website and verify you can view the webpage.

#### Extra credit

- Step 6: Create a CNAME DNS Record under `bitakle.academy` public domain pointing to the static website's URL from **Step 5**

- Step 7: Verify you can access static webpage using new URL