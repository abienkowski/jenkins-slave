# jenkins-slaves
Jenkin swarm slaves with docker installed and accessible to docker slave. 


## Running

# External Volumes

m2-repository: allows to have an external volume to store Maven repository and settings.xml file.
Using storage as a service this can be made availble to all jenkins-slaves.

To run a Docker container customizing the different tools with your credentials

    docker run \
    -e JENKINS_USERNAME=jenkins \
    -e JENKINS_PASSWORD=jenkins \
    -e JENKINS_MASTER=http://jenkins-master:8080 \
    -v m2-repository:/home/jenkins-slave/.m2 \
    abienkowski/jenkins-slave

### Optional Environment Variables

You can specify optional environment variables below when invoking docker run to customize the behavior of the swarm client.

| Parameter       | Default Value       | Description                                                                |
|-----------------|---------------------|----------------------------------------------------------------------------|
| SLAVE_EXECUTORS | number of cpu cores | This value specifies the number of concurrent jobs this worker can process |
