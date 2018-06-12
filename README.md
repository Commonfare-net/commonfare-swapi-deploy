# Social Wallet API deployment
This docker-compose project allows you to run an instance of the Social Wallet API service
and its storage.  

For more information please refer to https://github.com/Commonfare-net/social-wallet-api

## Configuration
Before running this service you should create your own configuration file located at
`data/social-wallet-api.yaml`.  
An example configuration file is provided at `data/social-wallet-api-example.yaml`.

### Additional settings
The `host` and `port` on which the Social Wallet API will be running can be specified by using the respectively `SWAPI_HOST` and `SWAPI_PORT` environment variables respectively.

## Running
To run this service just use:  
```
docker-compose up -d
```

At this point you shall be able to access the Swagger UI at http://localhost:3000.

## Dependency management
To overcome a problem with the docker image `commonfare/social-wallet-api` which causes all dependencies to be downloaded every time the image is run
we store them in the host and use them as a volume in the docker-compose configuration. By default dependencies will be stored in `data/swapi/m2`.