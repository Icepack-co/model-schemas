# Icepack model schemas

This repo contains the schemas currently supported by the api. 

## A note on immutability

The schemas used by Icepack are immutable by design. This is why we've used the slightly convoluted naming convention for each schema. What this means for you is that if you design your code against a particular model the definitions and standards used by that model aren't going to change. As features are added, new schemas are introduced which accommodate new features, leaving older schemas unchanged.

# Schema descriptions

All schemas are described in a fair bit of detail in our [documentation](https://docs.icepack.ai). If you feel there is more information you require on any of the topics - feel free to pop us a mail on: info at icepack dot co.

Model | Group | Comment
--- |  --- | ---
problem | base | [Wrapper interface](https://docs.icepack.ai/model-overview/problem_envelope/) for ALL models submitted to the api
ns3-tbfvuwtge2iq | network-sourcing | Target model for [sourcing models]((https://docs.icepack.ai/ns3/))
ivrdata-o43e0dvs78zq | data-upload | Target upload schema for caching [data]((https://docs.icepack.ai/ivr/ivrdata/)) on the API
matrix-vyv95n7wchpl | network-data | Produces distance / time [matricies](https://docs.icepack.ai/distance-matrix/)
tsp-mcvfz472gty6	| vehicle-router | Simple [TSP](https://docs.icepack.ai/classic-tsp/) model
tsptw-kcxbievqo879 | vehicle-router | Simple [TSP with Time Windows](https://docs.icepack.ai/tsptw/) model
cvrp-jkfdoctmp51n | vehicle-router | Capacitated [VRP](https://docs.icepack.ai/cvrp/) - nice for academic problems
cvrptw-acyas3nzweqb	| vehicle-router | [CVRP](https://docs.icepack.ai/vcrptw/) with Time Windows - nice for academic problems
ivr7-kt461v8eoaif	| vehicle-router | [IVR7](https://docs.icepack.ai/ivr/)
ivr8-yni1c9k2swof	| vehicle-router | IVR7 + Compartments = [IVR8](https://docs.icepack.ai/ivr/)
nvd-hap0j2y4zlm1 |  vehicle-router | [Sales rep](https://docs.icepack.ai/nvd/) periodic solver (ivr7-backed)
