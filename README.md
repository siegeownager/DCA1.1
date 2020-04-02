# Docker Certified Associate Exam Guide (v1.1 March 2020)
The DCA Exam has been updated to v1.1 as of March 2020. This edition's biggest change from previous versions of the exam is the inclusion of Kubernetes. With the sale of Docker EE to Mirantis, it seems more and more likely that Docker Swarm might be entirely phased out in the future in favor of Kubernetes. 
Two important points regarding this exam that I feel are essential to be declared at this point:
1. Docker Swarm still exists and there still are questions about it on this version of the exam
2. The version of the exam I took probably had between 25-35% of all questions requiring some kind of Kubernetes knowledge (the study guide mentions a few of these resources, but only knowing about those is nowhere near enough)

In this initial version, I plan to only provide quicklinks to what is present in the study guide without expanding on what other knowledge may be essential for getting a passing grade on the exam. 

## Examination Domains

### Domain 1: Orchestration (25% of exam)
Content may include the following:

● [Complete the setup of a swarm mode cluster, with managers and worker nodes](https://docs.docker.com/engine/swarm/swarm-tutorial/)

Note: You don't have to know about docker-machine. You can run multiple virtualized nodes in other ways if needed.

● [Describe and demonstrate how to extend the instructions to run individual containers into running services under swarm.](https://docs.docker.com/engine/swarm/services/)

● [Describe the importance of quorum in a swarm cluster.](https://docs.docker.com/engine/swarm/raft/)

● [Describe the difference between running a container and running a service.](https://docs.docker.com/engine/swarm/how-swarm-mode-works/services/)

● [Interpret the output of “docker inspect” commands.](https://docs.docker.com/engine/reference/commandline/inspect/)

● [Convert an application deployment into a stack file using a YAML compose file with "docker stack deploy"](https://docs.docker.com/engine/swarm/stack-deploy/)

● [Manipulate a running stack of services.](https://docs.docker.com/engine/reference/commandline/stack_services/#related-commands)

● [Describe and demonstrate orchestration activities.](https://docs.docker.com/engine/reference/commandline/swarm/)

● [Increase the number of replicas.](https://docs.docker.com/engine/reference/commandline/service_scale/)

● [Add networks,](https://docs.docker.com/engine/reference/commandline/network_create/) [publish ports.](https://docs.docker.com/config/containers/container-networking/)

● [Mount volumes.](https://docs.docker.com/storage/volumes/)

● [Describe and demonstrate how to run replicated and global services.](https://docs.docker.com/engine/swarm/services/#replicated-or-global-services)

● [Apply node labels](https://docs.docker.com/engine/reference/commandline/node_update/#add-label-metadata-to-a-node) to demonstrate [placement of tasks.](https://docs.docker.com/engine/reference/commandline/service_create/#specify-service-constraints---constraint)

● [Describe and demonstrate how to use templates with “docker service create”.](https://docs.docker.com/engine/reference/commandline/service_create/#create-services-using-templates)

● [Identify the steps needed to troubleshoot a service not deploying.](https://success.docker.com/article/swarm-troubleshooting-methodology)

● [Describe how a Dockerized application communicates with legacy systems.](https://docs.docker.com/network/macvlan/)

------------------------------------------------------------------------------------------------------------------------------

● Describe how to deploy containerized workloads as Kubernetes pods and deployments.

  Kubernetes quickstart - https://kubernetes.io/docs/tutorials/kubernetes-basics/
  
  Pods - https://kubernetes.io/docs/concepts/workloads/pods/pod/
  
  Deployments - https://kubernetes.io/docs/concepts/workloads/controllers/deployment/
  
------------------------------------------------------------------------------------------------------------------------------

● Describe how to provide configuration to Kubernetes pods using [configMaps](https://kubernetes.io/docs/tasks/configure-pod-container/configure-pod-configmap/) and [secrets.](https://kubernetes.io/docs/concepts/configuration/secret/)

### Domain 2: Image Creation, Management, and Registry (20% of exam)
Content may include the following:

------------------------------------------------------------------------------------------------------------------------------

● Describe the use of Dockerfile.

● Describe options, such as add, copy, volumes, expose, entry point.

● Identify and display the main parts of a Dockerfile.

● Describe and demonstrate how to create an efficient image via a Dockerfile.

Building & running an Image: https://docs.docker.com/get-started/part2/

Complete Dockerfile reference: https://docs.docker.com/engine/reference/builder/

Best practices: https://docs.docker.com/develop/develop-images/dockerfile_best-practices/

------------------------------------------------------------------------------------------------------------------------------

● [Describe and demonstrate how to use CLI commands to manage images, such as list, delete,
prune, rmi.](https://docs.docker.com/engine/reference/commandline/image/)

------------------------------------------------------------------------------------------------------------------------------

● Describe and demonstrate how to inspect images and report specific attributes using filter and
format

CLI command: https://docs.docker.com/engine/reference/commandline/image_inspect/

Formatting the output: https://docs.docker.com/config/formatting/

Filtering the output: https://docs.docker.com/config/formatting/

Golang reference: https://golang.org/pkg/text/template/

**NOTE**: You don't have to dive in-depth on any of these. Just know that they exist, and learn how to figure out what kind of output they may be grabbing (almost always self explanatory)

------------------------------------------------------------------------------------------------------------------------------

● [Describe and demonstrate how to tag an image.](https://docs.docker.com/engine/reference/commandline/tag/)

● [Describe and demonstrate how to apply a file to create a Docker image.](https://docs.docker.com/engine/reference/commandline/build/)

------------------------------------------------------------------------------------------------------------------------------

● [Describe and demonstrate how to display layers of a Docker image](https://docs.docker.com/engine/reference/commandline/history/)

The ```docker history``` command is not exactly used for viewing the layers of an image, but roughly speaking, it's good enough for many cases.

The actual image layer storage location can be viewed with ```docker image inspect``` and then checking the directories under 'GraphDriver.Data' For example, on a Linux system with overlay2 configured as the filesystem, the directory structure will look like /var/lib/docker/overlay2/xxxxxx. You don't need to know much here beyond knowing where it is found in the filesystem.

------------------------------------------------------------------------------------------------------------------------------

------------------------------------------------------------------------------------------------------------------------------

● Describe and demonstrate how to modify an image to a single layer.

The old way to do it was to use docker export and docker import.
https://forums.docker.com/t/how-to-flatten-an-image-with-127-parents/1600

The newer way (still experimental) is to use the ```--squash``` flag. https://docs.docker.com/engine/reference/commandline/build/#squash-an-images-layers-squash-experimental-only

------------------------------------------------------------------------------------------------------------------------------

● [Describe and demonstrate registry functions.]

● [Deploy a registry.]

● [Log into a registry.]

● [Utilize search in a registry.]

● [Push an image to a registry.]

● [Sign an image in a registry.]

● [Pull and delete images from a registry.]

### Domain 3: Installation and Configuration (15% of exam)
Content may include the following:

● [Describe sizing requirements for installation.]

● [Describe and demonstrate the setup of repo, selection of a storage driver, and
installation of the Docker engine on multiple platforms.]

● [Describe and demonstrate configuration of logging drivers (splunk, journald, etc.).]

● [Describe and demonstrate how to set up swarm, configure managers, add nodes, and setup the
backup schedule.]

● [Describe and demonstrate how to create and manage user and teams.]

● [Describe and demonstrate how to configure the Docker daemon to start on boot.]

● [Describe and demonstrate how to use certificate-based client-server authentication to
ensure a Docker daemon has the rights to access images on a registry.]

● [Describe the use of namespaces, cgroups, and certificate configuration.]

● [Describe and interpret errors to troubleshoot installation issues without assistance.]

● [Describe and demonstrate the steps to deploy the Docker engine, UCP, and DTR
on AWS and on-premises in an HA configuration.]

● [Describe and demonstrate how to configure backups for UCP and DTR.] 

### Domain 4: Networking (15% of exam)
Content may include the following:

● [Describe the Container Network Model and how it interfaces with the Docker engine and network
and IPAM drivers.]

● [Describe the different types and use cases for the built-in network drivers.]

● [Describe the types of traffic that flow between the Docker engine, registry and UCP
controllers.]

● [Describe and demonstrate how to create a Docker bridge network for developers to use for their
containers.]

● [Describe and demonstrate how to publish a port so that an application is accessible externally.]

● [Identify which IP and port a container is externally accessible on.]

● [Compare and contrast “host” and “ingress” publishing modes.]

● [Describe and demonstrate how to configure Docker to use external DNS.]

● [Describe and demonstrate how to use Docker to load balance HTTP/HTTPs traffic to
an application (Configure L7 load balancing with Docker EE).]

● [Understand and describe the types of traffic that flow between the Docker engine,
registry, and UCP controllers]

● [Describe and demonstrate how to deploy a service on a Docker overlay network.]

● [Describe and demonstrate how to troubleshoot container and engine logs to resolve connectivity
issues between containers.]

● [Describe how to route traffic to Kubernetes pods using ClusterIP and NodePort services.]

● [Describe the Kubertnetes’ container network model.]

### Domain 5: Security (15% of exam)
Content may include the following:

● [Describe security administration and tasks.]

● [Describe the process of signing an image.]

● [Describe default engine security.]

● [Describe swarm default security.]

● [Describe MTLS.]

● [Describe identity roles.]

● [Compare and contrast UCP workers and managers.]

● [Describe the process to use external certificates with UCP and DTR.]

● [Describe and demonstrate that an image passes a security scan.]

● [Describe and demonstrate how to enable Docker Content Trust.]

● [Describe and demonstrate how to configure RBAC with UCP.]

● [Describe and demonstrate how to integrate UCP with LDAP/AD.]

● [Describe and demonstrate how to create UCP client bundles.]
