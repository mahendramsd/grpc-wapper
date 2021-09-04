# Getting started with gRPC
  
  Following below steps for the initiate project.
  
  -- Creating a gradle project to write proto files
  -- Create new proto and write simple grpc service
  -- publish the artifact to the local maven repository.

# Dependancies

following dependencies are require to crete the proto files, generate the java code and write & execute the grpc services.

implementation 'io.grpc:grpc-netty-shaded:1.39.0'
implementation 'io.grpc:grpc-protobuf:1.39.0'
implementation 'io.grpc:grpc-stub:1.39.0'

use the version availbe at the moment

You can creare a seperate project to manage only the proto files and publish the artifact as well as you can use the same project to implement your grpc service. I am using this project to manage the protos and publish the artifact and use a different project to implement the grpc service.

# Artifact details

all the details for artifact is there in the gradle.properties file

  libArtifactGroup=com.msd.grpc
  libArtifactId=grpc-wapper
  libArtifactVersion=0.0.1
  
# Publish the artifact to the local maven

    publishing {
        publications {
            mavenJava(MavenPublication) {
                from components.java
                artifactId = "${libArtifactId}"
            }
        }
    }

# Build Project

Build the command "gradlew clean build publishToMavenLocal" to publish to your local maven repository.
