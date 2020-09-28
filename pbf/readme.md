# Protobuf (pbf) API

Protobuf is a high-performance serialisation layer. For larger model submissions or responses we recommend using the protobuf interfaces as it is quicker to serialise or deserialise payloads. Part of the reason for this is that the majority of protobuf clients can only serialise a protobuf message if all the required fields are correctly populated. This means that the validity of the message submitted is actually enforced _before_ the message is sent to the API. This ensures that if there is an error in a particular message definition that it will be picked up on the client side where the message can be more easily analysed.

## Protobuf requirements

In order to use protobuf you require a protobuf compiler. You will need `protoc` compiler (version >= 3.6.1) available in your path.


### Windows

You can download [3.6.1 here](https://github.com/protocolbuffers/protobuf/releases/download/v3.6.1/protobuf-all-3.6.1.tar.gz) or download a newer version if you prefer from the [github releases page](https://github.com/protocolbuffers/protobuf/releases).
After compiling the `protoc` executable you can add it to your system path (see environmental variables) and then use the command line interface to target the particular output format you would like.

### Linux 

Installing from source is the best way to go about this as package managers typically deliver a version from the 2.x.x series. To compile from source on debian you can run:

* `apt-get install autoconf automake libtool curl make g++ unzip`
* You can download [3.6.1 here](https://github.com/protocolbuffers/protobuf/releases/download/v3.6.1/protobuf-all-3.6.1.tar.gz) or download a newer version if you prefer from the [github releases page](https://github.com/protocolbuffers/protobuf/releases).
* Unzip the contents of protobuf-all-x.x.x
* `./configure`
* `make`
* `make check`
* `sudo make install`
* `sudo ldconfig`

 ## Compilation examples

 Once `protoc` is available in your path, you can compile the schemas to several possible output languages. Examples of output languages include cpp, c#, Java, JavaScript, Objective-C, PHP, Python and Ruby.

 Here is an example of how to generate the language-native objects from the ivr7 schema file using `protoc` producing native Java objects:
 ```
 protoc --proto_path ./ ivr7-kt461v8eoaif.proto --java_out=src/main/my-java-app/
 ```

 For more information on `protoc` feel free to type:
 ```
 protoc --help
 ```

 ## Submitting models to the API

 The protobuf end points routes are separated according to the model-type. All routing-styling models can be submitted to the `vehicle-router` route. Similarly for the network-sourcing models and data-upload models. The pbf API uses a master envelope which defined the sub-type of the problem submitted (which has been serialised into the problem envelope). This allows the API to interpret the message according to it's type. Similarly, a standard response message is returned by the API which the client can then deserialise according to the designated response message (corresponding to the model type submitted).

 This may sound very complicated, but if you're familiar with R, C#, Java or Python, feel free to check out the [examples repo](https://github.com/Icepack-co/examples) which has code samples of how to do this using a single API interface across the majority of the Icepack supported models.

 If you're not comfortable with these languages, or working with protobuf - we recommend you check out the Json interfaces in this repo which use the open-api specification to define which models may be submitted to the different endpoints.
