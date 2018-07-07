# gRPC-maven-helloworld


HelloWorld code is based on the quick start at:
http://www.grpc.io/docs/

The purpose of this test was to see it build with maven, based on instructions on how to construct the POM plugins and depencies at at: https://github.com/grpc/grpc-java


Clone this respositry from github and then run:
```
mvn clean package
```

Note the hello_world.proto file defined the gRPC service at:
```
server/src/main/proto/helloworld.proto
client/src/main/proto/helloworld.proto
```
I did change the java_package name in helloworld.proto so the generated code would be in same package org.jpdna.grchhellow as the application code

Due to the protoc and gRPC plugins mentioned in the POM, code is generated during the build and placed in
````
target/generated-sources
​```

protoc binary will need to be available in your PATH

To run the server, from the root of the cloned repository run:
​```
cd server && mvn spring-boot:run
````

you should see:
```
INFO: Server started, listening on 50051
```

Next run the client:
```
cd client && mvn spring-boot:run
```

you sould see:
```
Nov 22, 2015 7:20:56 PM org.jpdna.grpchello.HelloWorldClient greet
INFO: Will try to greet world ...
Nov 22, 2015 7:20:56 PM org.jpdna.grpchello.HelloWorldClient greet
INFO: Greeting: Hello world
```

