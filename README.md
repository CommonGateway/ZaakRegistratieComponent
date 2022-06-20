# Zaak Registratie Component API
[![Automated Testing](https://github.com/CommonGateway/ZaakRegistratieComponent/actions/workflows/tests.yml/badge.svg)](https://github.com/CommonGateway/ZaakRegistratieComponent/actions/workflows/tests.yml)

A example implementation of a Common Gateway configuration for generating an API. This example has been specifically setup to use as a temple, read more about that under [Using this repositry as a temple](#Using this repositry as a temple).

- [API Defintion (redocly)](https://redocly.github.io/redoc/?url=https://raw.githubusercontent.com/CommonGateway/ZaakRegistratieComponent/main/OAS.yaml&nocors)
- [API Defintion (file)](https://github.com/CommonGateway/ZaakRegistratieComponent/blob/main/OAS.yaml)
- [Publiccode](https://github.com/CommonGateway/ZaakRegistratieComponent/blob/main/publiccode.yaml)

## About Common Gateway configuration files
Read more..

## Creating your own documentation
This Commmon Gateway configuration repository is bassed on [petstore](https://redocly.github.io/redoc/) an example [Open API Specification]([https://redocly.com/docs/openapi/reference-docs-example/overview/](https://swagger.io/specification/)) from our friends at [redocly](https://redocly.com/docs/). In order to create and maintain Open Api Secifications files we recomend using [stoplight](), you can find the stoplight project for Pet Store [here](https://conduction.stoplight.io/docs/pet-store/branches/main/ls7mp80wwy88k-swagger-petstore). For convience purpose a copy of the Pet strore oas is stored in this repository [here](https://github.com/CommonGateway/ZaakRegistratieComponent/blob/main/OAS.yaml).

The [public code](https://yml.publiccode.tools/) for this ropository was genereted trough the [publiccode yaml editor](https://publiccode-editor.developers.italia.it/).

## Running the API locally

You need [Docker desktop](https://www.docker.com/) if you want to use this API locally on the [gateway](https://github.com/ConductionNL/commonground-gateway).
Once you have installed docker you need to go to the root of the project with a command line.

Then you can run the image with:

`docker compose up`

If the php container shows "Ready to handle connections" the gateway is ready.
The API runs on port :80 and the endpoints of this API fall under /api

## Running the API online

To run the API on a online gateway the helm secret PUBLICCODE must be set with the url to the raw publiccode.yaml, like: https://raw.githubusercontent.com/CommonGateway/PetStoreAPI/main/publiccode.yaml

If its properly set you can run the following command in a PHP pod:

`bin/console app:load-publiccodes`

The console should show if the API has been loaded successfully, and then you can make API requests to yourdomain/api.


## (Unit) Testing the API

On every commit github launches a action that generates a postman collection and tests the API. Its results can be viewed under Actions on the github page.
