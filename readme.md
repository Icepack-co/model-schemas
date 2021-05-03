# Icepack model schemas

This repo contains the schemas currently supported by the api. 

## A note on immutability

The schemas used by Icepack are immutable by design. This is why we've used the slightly convoluted naming convention for each schema. What this means for you is that if you design your code against a particular model the definitions and standards used by that model aren't going to change. As features are added, new schemas are introduced which accommodate new features, leaving older schemas unchanged.

## Repo Structure

The API will accept a protobuf problem envelope, which contains the details of the type  serialised request. Alternatively, the api will accept a JSON payload, however the route should reflect the model type being submitted.

The repo contains two approaches to building and submitting models, a protobuf (pbf) series of endpoints, and a json series of endpoints. A description of how to submit models to the pbf end-point (preferred) can be found [here](https://docs.icepack.ai/getting-started/calling-the-api/). The `spec.yml` file contains the details of the different routes for json model submissions.

# Schema descriptions

All schemas are described in a fair bit of detail in our [documentation](https://docs.icepack.ai). If you feel there is more information you require on any of the topics - feel free to pop us a mail on: info at icepack dot co.

Model | Group | Comment
--- |  --- | ---
problem | base | [Pbf wrapper](https://docs.icepack.ai/model-overview/problem_envelope/) for ALL models submitted to the api
ns3-tbfvuwtge2iq | network-sourcing | Target model for [sourcing models]((https://docs.icepack.ai/ns3/))
ivrdata-o43e0dvs78zq | data-upload | Target upload schema for caching [data]((https://docs.icepack.ai/ivr/ivrdata/)) on the API
matrix-vyv95n7wchpl | network-data | Produces distance / time [matricies](https://docs.icepack.ai/distance-matrix/)
tsp-mcvfz472gty6 | vehicle-router | Simple [TSP](https://docs.icepack.ai/classic-tsp/) model
tsptw-kcxbievqo879 | vehicle-router | Simple [TSP with Time Windows](https://docs.icepack.ai/tsptw/) model
cvrp-jkfdoctmp51n | vehicle-router | Capacitated [VRP](https://docs.icepack.ai/cvrp/) - nice for academic problems
cvrptw-acyas3nzweqb	| vehicle-router | [CVRP](https://docs.icepack.ai/vcrptw/) with Time Windows - nice for academic problems
ivr7-kt461v8eoaif	| vehicle-router | [IVR7](https://docs.icepack.ai/ivr/)
ivr8-yni1c9k2swof	| vehicle-router | IVR7 + Compartments = [IVR8](https://docs.icepack.ai/ivr/)
nvd-hap0j2y4zlm1 |  vehicle-router | [Sales rep](https://docs.icepack.ai/nvd/) periodic solver (ivr7-backed)
isr-z4foi53qznrv | vehicle-router | [Street Router]() - used for high frequency stops where the bearing of travel in conjunction with visiting segments once is important. See the docs for more info.
