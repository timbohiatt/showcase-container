
## Application Environment Variables
At runtime the application will look for environment varaiables which can be used to enhance the demonstration by providing a little bit more context to the running environment or to tailor the demo quickly to a customer and or client presentation with minimal branding.

The following environment variables are accepted by the running application. 

| Variable      | Data Type | Description | Default |
| ----------- | ----------- | ----------- | ----------- |
| PORT      | string | Container Runnign Port       | 8080       |
| CUSTOMER      | string| The Customer/Client name for demo purposes       | "You!"       |
| COLOR_PRIMARY   | Color HEX| Primary Text & Accent Color        | #000000       |
| COLOR_SECONDARY   | Color HEX| Secondary Text & Accent Color         | #5f5f61       |
| COLOR_BACKGROUND   | Color HEX| Web Application Background Color        | #FFFFFF        |
| LOCATION   | string| Google Cloud Region/Zone or Location Descriptive Text (europe-west1-a, us-central1, asia)        | "a Google Cloud region         |
| PLATFORM   | string | Running platform, GKE, Cloud Run, Autopilot, VM? You Choose;s        | Google Cloud Platform        |


<br>

## Build & Run the Container

This go application is simply written and Go and a Dockerfile has been provided in order for quick portability and running of the application for demo purposes. 

```
# Build the Container Image
docker build -t <IMAGE TAG> .

# Run the Container Image
docker run -p 8080:8080 <IMAGE TAG> 
```

There are several variants for running the container image. 

```
# Run the Container Image with a Custom Name and Custom Colors
docker run -p 8080:8080 \
    -e "CUSTOMER=<YOUR_CUSTOMER_NAME> \ 
    -e "COLOR_PRIMARY=#ff0000" \
    -e "COLOR_BACKGROUND=#9966ff" \
    <IMAGE TAG> 
```

```
# Run the Container Image with a Custom Name Custom Platform
docker run -p 8080:8080 \
    -e "CUSTOMER=<YOUR_CUSTOMER_NAME> \ 
    -e "PLATFORM=Google Cloud GCE Instance" \
    <IMAGE TAG> 
```

```
# Run the Container Image with a Custom Name Custom Platform & Region
docker run -p 8080:8080 \
    -e "CUSTOMER=<YOUR_CUSTOMER_NAME> \ 
    -e "PLATFORM=Google Cloud Run Instance" \
    -e "LOCATION=autralia-southeast1" \
    <IMAGE TAG> 
```


