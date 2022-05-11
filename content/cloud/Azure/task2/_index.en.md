---
title: Task 2
weight: 25
---

# Containerized Web App

### Objective:

In this task, you will provision Azure Container Registry to host container images used to deploy web app. The container images will be built using Azure Container Registry tasks via Azure CLI or using [Docker](https://docs.docker.com/engine/).

### Instructions:

  - #### Part 1 - Azure Container Registry

    - Step 1: Provision Azure Container Registry ([Ref](https://docs.microsoft.com/en-us/azure/container-registry/container-registry-get-started-portal))
    - Step 2: Install Azure CLI on your machine ([Ref](https://docs.microsoft.com/en-us/cli/azure/install-azure-cli))
    - Step 3: Log in to ACR: `az login; az acr login --name <registry_name>`

- #### Part 2 - Build Web App Container

    - Step 1: Create simple HTML file **index.html** to serve out of NGINX container
      ```html
      <html>
        <head>
            <title>Href Attribute Example</title>
        </head>
        <body>
            <h1>Href Attribute Example</h1>
            <p>
            <a href="https://bitakle.org">The Bitakle Page</a> shows you where you can start your InfoTech journey.
            </p>
        </body>
      </html>
      ```
    - Step 2: Create simple NGINX Dockerfile to build container image from
      ```Dockerfile
      FROM nginx:latest
      COPY ./index.html /usr/share/nginx/html/index.html
      ```
    - Step 3: Install Docker to build and test the image locally [Ref](https://docs.docker.com/engine/install/ubuntu/)

    - Step 4: Build container image locally
      ```bash
      # Change to the same directory with Dockerfile
      docker build -t webserver .
      ```
    - Step 5: Run the image locally
      ```bash
      docker run -it --rm -d -p 8080:80 --name web webserver
      ```
    - Step 6: Navigate to the http://localhost:8080 to verify the webpage is being served correctly
    - Step 7: Push the image to Azure Container Registry:
      ```bash
      docker tag webserver <registry_name>.azurecr.io/web/webserver
      docker push <registry_name>.azurecr.io/web/webserver
      ```
      {{% notice note %}} Alternatively, you can build and push images directly using az-cli acr task
      ```bash
      az acr build --registry <registry_name> --image /web/webserver:v1 .
      ```
      {{% /notice %}}

- #### Part 3 - Run container in Azure

    - Step 1: Create and configure Azure App service or Web App with the appropriate settings
    - Step 2: Point the service to utilize the container image from the [Step-2](#part-2---build-web-app-container)
    - Step 3: Visit the webpage of the Web App service and verify the expected result

{{% notice info %}}
This guide is an outline of the steps and the goals for each part. It is not a comprehensive guide. You may experience errors or find a need for additional steps in the process. Use your troubleshooting skills, official documentation, and any other resources to complete this task.
{{% notice info %}}
