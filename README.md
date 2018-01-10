# Steps to deploy on Azure App Service

1. Build docker image from the code: 
    
        docker build -f Dockerfile -t <app-name>:latest .

2. Run and test your new docker image locally (pass required env variables): 

        docker run -p 8080:8080 -e AZURE_STORAGE_KEY=<key> --rm <app-name>

3. Locate the image id by running `docker images` and tag existing image with your Docker Hub username: 

        docker tag <image-id> <dockerhub-username>/<app-name>

4. Push the image to Docker Hub: 

        docker push <dockerhub-username>/<app-name>


For more information, please see the [Use a custom Docker image for Web App for Containers](https://docs.microsoft.com/en-us/azure/app-service/containers/tutorial-custom-docker-image).

