---
title: Task 3
weight: 35
---

# Continuous Deployment with Github and Azure Static Web App

### Objective:

In this task, you will learn about code repository [Github](https://github.com) and will set up your first repo to store your web app code. Then you will provision Azure Static Web App and configure continuous deployment from your Github repository.

### Prerequisites:

You will need to create [Github](https://github.com) account if you don't have one already.

### Instructions:

  - #### Part 1 - Github repository

    - Step 1: Create Github repository ([Ref](https://docs.github.com/en/get-started/quickstart/create-a-repo)) under Bitakle organization.
    - Step 2: Create the following files under `src` folder.

      *index.html*
      ```html
      <!DOCTYPE html>
      <html lang="en">

      <head>
        <meta charset="UTF-8">
        <meta name="viewport" content="width=device-width, initial-scale=1.0">
        <link rel="stylesheet" href="styles.css">
        <title>Vanilla JavaScript App</title>
      </head>

      <body>
        <main>
          <h1>Vanilla JavaScript App</h1>
        </main>
      </body>

      </html>
      ```
      *styles.css*
      ```css
      * {
          font-family: Arial, Helvetica, sans-serif;
        }

        html, body {
          margin: 0;
          border: 0;
          padding: 0;
          background-color: #fff;
        }

        main {
          margin: auto;
          width: 50%;
          padding: 20px;
        }

        main > h1 {
          text-align: center;
          font-size: 3.5em;
        }
      ```
    - Step 3: Upload `src` folder to the repository.

- #### Part 2 - Provision Azure Static Web App

    - Step 1: Create static web app and connect it to Github repository from the previous step ([Ref](https://docs.microsoft.com/en-us/azure/static-web-apps/get-started-portal?tabs=vanilla-javascript#create-a-static-web-app))

    - Step 2: Once completed, navigate to Github repository and check **Actions** tab. Verify that the action completed successfully.

    - Step 3: Navigate to the web app URL and verify its content.

- #### Part 3 - Verify Continuous Deployment

    - Step 1: Make changes to **index.html** and **styles.css** files and update them in Github repository.
    - Step 2: Check to make sure action under **Actions** tab is completed successfully.
    - Step 3: Refresh the webpage and verify the changes are displayed.

{{% notice info %}}
This guide is an outline of the steps and the goals for each part. It is not a comprehensive guide. You may experience errors or find a need for additional steps in the process. Use your troubleshooting skills, official documentation, and any other resources to complete this task.
{{% notice info %}}