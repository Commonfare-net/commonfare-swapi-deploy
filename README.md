# Social Wallet API deployment
This docker-compose project allows you to run an instance of the Social Wallet API service and its storage.  

For more information about the Social Wallet API, please refer to [the official repo](https://github.com/Commonfare-net/social-wallet-api).

## Configuration

Please follow the next steps before running the service.

### Docker compose
Copy `docker-compose.example.yml` to `docker-compose.yml` and change your settings if needed (e.g. port number).

### SWAPI
#### Configuration
Before running this service you must create your own configuration file located at
`conf/social-wallet-api.yaml`. An example configuration file is provided at `conf/social-wallet-api.example.yaml`.

In `conf/social-wallet-api.yaml` replace `YOUR_SWAPI_ID` and `YOUR_CURRENCY_NAME` with your values.

#### API key
Create the file for storing the API key by copying the file `conf/apikey.example.yaml` in `conf/apikey.yaml`.
On the first execution, SWAPI will generate the API key and will stored it in this file (see [here](https://github.com/Commonfare-net/social-wallet-api/blob/master/APIKEY.md) for details).

### Additional settings
The `host` and `port` on which the Social Wallet API will be running can be specified by using the respectively `SWAPI_HOST` and `SWAPI_PORT` environment variables in `docker-compose.yml`.

## Running
Before running for the first time, be sure you gone throuh all the previous steps.

To run this service just use:  
```
docker-compose up -d
```

At this point you shall be able to access the Swagger UI at http://localhost:3000 (or your `SWAPI_PORT`). Click on the 'Authorize' button and paste the API key you get from `conf/apikey.yaml`.

### Update
To update the images
```
docker-compose pull
```

## Acknowledgements

This software is a Free and Open Source research and development activity funded by the European Commission in the context of the [Collective Awareness Platforms for Sustainability and Social Innovation (CAPSSI)](https://ec.europa.eu/digital-single-market/en/collective-awareness) program. Ths software uses the [Social Wallet API](https://github.com/Commonfare-net/social-wallet-api) and it has been adopted as a component of the [Commonfare platform](https://commonfare.net) being developed for
the [Commonfare - PIE News project](https://pieproject.eu) (grant nr. 687922).

## Contributing

Bug reports and pull requests are welcome on GitHub at https://github.com/Commonfare-net/commonfare-swapi-deploy.
