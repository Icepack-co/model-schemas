# Open-api V3 speciciation for the Icepack API

This repo contains the api specification for sending models using json to the Icepack API. Each model has a designated route for the POST/GET workflow as well as model-upload where appropriate.

The current specification uses the Open-API V3 format.

## Building the models

In order to build the client models you can use the `swagger-codegen-cli.jar`. This takes as input the specification file and a target output. It also assumes that you have Java installed on your system.

As an example, to build a golang client run:
```
java -jar swagger-codegen-cli.jar generate -i spec.yml -g go -o golang-client/
```
where `golang-client/` is the output directory and `spec.yml` is the main specification root for all the models which can be submitted to the api.

To see a list of supported client languages just type:
```
java -jar swagger-codegen-cli.jar langs
```

One can also use the `openapi-generator-cli.jar` (available [here](https://github.com/OpenAPITools/openapi-generator)) to validate the specification if you require.

## Working with the models

Once you have generated the objects in your target langauge, feel free to check out the [Icepack Documentation Site](https://docs.icepack.ai) which contains examples of how to build models and the interpretation of the object fields in their respective contexts.
