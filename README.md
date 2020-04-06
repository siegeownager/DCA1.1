# Docker Certified Associate Exam Guide (v1.1 March 2020)
The DCA Exam has been updated to v1.1 as of March 2020. This edition's biggest change from previous versions of the exam is the inclusion of Kubernetes. With the sale of Docker EE to Mirantis, it seems more and more likely that Docker Swarm might be entirely phased out in the future in favor of Kubernetes. 
Two important points regarding this exam that I feel are essential to be declared at this point:
1. Docker Swarm still exists and there still are questions about it on this version of the exam
2. The version of the exam I took probably had between 25-35% of all questions requiring some kind of Kubernetes knowledge (the study guide mentions a few of these resources, but only knowing about those is nowhere near enough)

In this initial version, I plan to only provide quicklinks to what is present in the study guide without expanding on what other knowledge may be essential for getting a passing grade on the exam. 

Before trying to tackle the study guide, it may help immensely to read ['Docker Deep Dive'](https://www.amazon.com/Docker-Deep-Dive-Nigel-Poulton-ebook/dp/B01LXWQUFF) by Nigel Poulton. Book is about 2 years old and a few things have changed since then, but for core knowledge as well as an easier introduction to Docker Enterprise Edition, this is the best resource I am aware of.

## Examination Domains

### Domain 1: Orchestration (25% of exam)
Content may include the following:

● [Complete the setup of a swarm mode cluster, with managers and worker nodes](https://docs.docker.com/engine/swarm/swarm-tutorial/)

```Note: You don't have to know about docker-machine. You can run multiple virtualized nodes in other ways if needed.```

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

● Describe how to deploy containerized workloads as Kubernetes [pods](https://kubernetes.io/docs/concepts/workloads/pods/pod/) and [deployments](https://kubernetes.io/docs/concepts/workloads/controllers/deployment/).

  - Kubernetes quickstart - https://kubernetes.io/docs/tutorials/kubernetes-basics/

● Describe how to provide configuration to Kubernetes pods using [configMaps](https://kubernetes.io/docs/tasks/configure-pod-container/configure-pod-configmap/) and [secrets.](https://kubernetes.io/docs/concepts/configuration/secret/)

### Domain 2: Image Creation, Management, and Registry (20% of exam)
Content may include the following:

------------------------------------------------------------------------------------------------------------------------------

● Describe the use of Dockerfile.

● Describe options, such as add, copy, volumes, expose, entry point.

● Identify and display the main parts of a Dockerfile.

● Describe and demonstrate how to create an efficient image via a Dockerfile.

   - [Building & running an Image](https://docs.docker.com/get-started/part2/)

   - [Complete Dockerfile reference](https://docs.docker.com/engine/reference/builder/)

   - [Best practices](https://docs.docker.com/develop/develop-images/dockerfile_best-practices/)
   
------------------------------------------------------------------------------------------------------------------------------

● [Describe and demonstrate how to use CLI commands to manage images, such as list, delete,
prune, rmi.](https://docs.docker.com/engine/reference/commandline/image/)

● Describe and demonstrate how to inspect images and report specific attributes using filter and
format

  - [CLI command](https://docs.docker.com/engine/reference/commandline/image_inspect/)

  - [Formatting the output](https://docs.docker.com/config/formatting/)

  - [Filtering the output](https://docs.docker.com/config/formatting/)

  - [Golang reference](https://golang.org/pkg/text/template/)

```NOTE: You don't have to dive in-depth on any of these. Just know that they exist, and learn how to figure out what kind of output they may be grabbing (almost always self explanatory)```

● [Describe and demonstrate how to tag an image.](https://docs.docker.com/engine/reference/commandline/tag/)

● [Describe and demonstrate how to apply a file to create a Docker image.](https://docs.docker.com/engine/reference/commandline/build/)

● [Describe and demonstrate how to display layers of a Docker image](https://docs.docker.com/engine/reference/commandline/history/)

```The `docker history` command is not exactly used for viewing the layers of an image, but roughly speaking, it's good enough for many cases.```

```The actual image layer storage location can be viewed with `docker image inspect` and then checking the directories under
'GraphDriver.Data' For example, on a Linux system with overlay2 configured as the filesystem, the directory structure will 
look like `/var/lib/docker/overlay2/xxxxxx`. You don't need to know much here beyond knowing where it is found in the 
filesystem. If you're curious to know more:```
https://www.freecodecamp.org/news/where-are-docker-images-stored-docker-container-paths-explained/

● Describe and demonstrate how to modify an image to a single layer.

  - [Old export/import method](https://forums.docker.com/t/how-to-flatten-an-image-with-127-parents/1600)

  - [Experimental squash flag](https://docs.docker.com/engine/reference/commandline/build/#squash-an-images-layers-squash-experimental-only)

------------------------------------------------------------------------------------------------------------------------------

● Describe and demonstrate registry functions.

  - https://docs.docker.com/registry/
  - https://docs.docker.com/registry/introduction/

```
'Registry' and 'Docker Trusted Registry' are related but separate concepts when it comes to the DCA.
```

● [Deploy a registry.](https://docs.docker.com/registry/deploying/)

● [Log into a registry.](https://docs.docker.com/engine/reference/commandline/login/)

● Utilize search in a registry.

```
Docker Hub: https://docs.docker.com/engine/reference/commandline/search/

Private registries: https://github.com/docker/distribution/blob/master/docs/spec/api.md
From the second link, check out `GET /v2/<name>/tags/list` and `GET /v2/_catalog`
  
The API isn't important, just know that it exists and take a quick look at the various methods available to you.
```

● [Push an image to a registry.](https://docs.docker.com/engine/reference/commandline/push/)

● [Sign an image in a registry.](https://success.docker.com/article/introduction-to-docker-content-trust)

● Pull and delete images from a registry.

```
Pull: https://docs.docker.com/engine/reference/commandline/pull/

Delete: https://github.com/docker/distribution/blob/master/docs/spec/api.md#deleting-an-image
```

### Domain 3: Installation and Configuration (15% of exam)
Content may include the following:

● Describe sizing requirements for installation.

  - [UCP](https://docs.docker.com/ee/ucp/admin/install/system-requirements/)

  - [DTR](https://docs.docker.com/ee/dtr/admin/install/system-requirements/)

  - [Docker Engine](https://docs.docker.com/install/)

● Describe and demonstrate the setup of repo, selection of a storage driver, and
installation of the Docker engine on multiple platforms.

  - Depending on the OS, the installation method varies: 
  
    https://docs.docker.com/search/?q=Docker%20Engine%20-%20Community

  - [Storage drivers](https://docs.docker.com/storage/storagedriver/select-storage-driver/)

```While you should know the pros/cons of each type of storage driver, the most important ones to read about are overlay2 and device-mapper. You don't need to bother with learning how to configure the others. You don't need to know exactly how to configure device-mapper in direct-lvm mode but you need to know about the various options that exist and how it compares with loopback-lvm.```

● [Describe and demonstrate configuration of logging drivers (splunk, journald, etc.).](https://docs.docker.com/config/containers/logging/configure/)

● [Describe and demonstrate how to set up swarm, configure managers, add nodes, and setup the
backup schedule.](https://docs.docker.com/engine/swarm/admin_guide/)

● [Describe and demonstrate how to create and manage user and teams.](https://docs.docker.com/ee/ucp/authorization/create-users-and-teams-manually/)

● [Describe and demonstrate how to configure the Docker daemon to start on boot.](https://docs.docker.com/install/linux/linux-postinstall/#configure-docker-to-start-on-boot)

● [Describe and demonstrate how to use certificate-based client-server authentication to
ensure a Docker daemon has the rights to access images on a registry.](https://docs.docker.com/engine/security/certificates/)

● [Describe the use of namespaces, cgroups,](https://docs.docker.com/engine/docker-overview/) and [certificate configuration.](https://docs.docker.com/engine/security/https/)

● [Describe and interpret errors to troubleshoot installation issues without assistance.](https://docs.docker.com/config/daemon/)

● Describe and demonstrate the steps to deploy the Docker engine, UCP, and DTR
on AWS and on-premises in an HA configuration.

Docker EE engine (installation guides based on OS near the bottom of the page): 

https://docs.docker.com/ee/supported-platforms/

**UCP:**

[On-premise](https://docs.docker.com/ee/ucp/admin/install/)

[AWS](https://docs.docker.com/ee/ucp/admin/install/cloudproviders/install-on-aws/)

**DTR:**

[Install](https://docs.docker.com/ee/dtr/admin/install/)

[Store images on S3](https://docs.docker.com/ee/dtr/admin/configure/external-storage/s3/)

● Describe and demonstrate how to configure backups for [UCP](https://docs.docker.com/ee/admin/backup/back-up-ucp/) and [DTR.](https://docs.docker.com/ee/admin/backup/back-up-dtr/)

### Domain 4: Networking (15% of exam)
Content may include the following:

● [Describe the Container Network Model and how it interfaces with the Docker engine and network
and IPAM drivers.](https://success.docker.com/article/networking#thecontainernetworkingmodel)

● [Describe the different types and use cases for the built-in network drivers.](https://docs.docker.com/network/#network-drivers)

● Describe the types of traffic that flow between the Docker engine, registry and UCP
controllers.

Familiarize yourself with the networks and ports relevant to each of these as well as have an idea about how they work at a high level.

  - https://docs.docker.com/ee/ucp/ucp-architecture/

  - https://docs.docker.com/ee/ucp/admin/install/system-requirements/ 

  - https://docs.docker.com/ee/dtr/architecture/


● [Describe and demonstrate how to create a Docker bridge network for developers to use for their
containers.](https://docs.docker.com/network/bridge/)

● [Describe and demonstrate how to publish a port so that an application is accessible externally.](https://docs.docker.com/config/containers/container-networking/#published-ports)

● [Identify which IP and port a container is externally accessible on.](https://docs.docker.com/engine/reference/commandline/port/)

● [Compare and contrast “host” and “ingress” publishing modes.](https://docs.docker.com/engine/swarm/ingress/)

● Describe and demonstrate how to configure Docker to use external DNS.

There are three ways to do this:

  - [Add the 'dns' property in /etc/daemon.json](https://docs.docker.com/engine/reference/commandline/dockerd/#daemon-configuration-file)

  - [Start the dockerd process with the necessary value passed to the dns flag](https://docs.docker.com/engine/reference/commandline/dockerd/#daemon-dns-options)
  
  - [Set it on a per-container basis](https://docs.docker.com/config/containers/container-networking/#published-ports#dns-services)

● [Describe and demonstrate how to use Docker to load balance HTTP/HTTPs traffic to
an application (Configure L7 load balancing with Docker EE).](https://docs.docker.com/ee/ucp/interlock/)

The interlock configuration is done through the UCP Web UI

● [Describe and demonstrate how to deploy a service on a Docker overlay network.](https://docs.docker.com/engine/swarm/services/#connect-the-service-to-an-overlay-network#connect-the-service-to-an-overlay-network)

● Describe and demonstrate how to troubleshoot [container](https://docs.docker.com/engine/reference/commandline/logs/) and [engine](https://docs.docker.com/config/daemon/) logs to resolve connectivity issues between containers.

● Describe how to route traffic to Kubernetes pods using ClusterIP and NodePort services.

https://kubernetes.io/docs/tutorials/kubernetes-basics/expose/expose-intro/

https://kubernetes.io/docs/concepts/services-networking/service/

```ClusterIP: Exposes the Service on a cluster-internal IP. Choosing this value makes the Service only reachable from within the cluster. This is the default ServiceType.```

```NodePort: Exposes the Service on each Node’s IP at a static port (the NodePort). A ClusterIP Service, to which the NodePort Service routes, is automatically created. You’ll be able to contact the NodePort Service, from outside the cluster, by requesting <NodeIP>:<NodePort>.```

● Describe the Kubertnetes’ container network model.

  - https://kubernetes.io/docs/concepts/cluster-administration/networking/
  
  - https://github.com/containernetworking/cni
  
You don't have to know how these work at a lower level, but you do need to understand the concepts and also how to specify a CNI plugin. The official documentation does not do a very good job of explaining some of these points.

If you have the book [Kubernetes in Action](https://www.manning.com/books/kubernetes-in-action) by Marko Lukša (1st edition, 2017), then page 335 does a fantastic job of explaining these in a much more condensed form.
  

### Domain 5: Security (15% of exam)
Content may include the following:

------------------------------------------------------------------------------------------------------------------------------

This entire section is extremely poorly documented in the official documentation. You will have to piece together information from multiple pages in the docs as well as have a decent level of technical skill in order to be able to implement them if you rely purely on the official documentation. For learning about this section, it is highly recommended to read the book ``Docker Deep Dive`` mentioned in the introduction. If you are unable to obtain the book, I would recommend searching around on sites like reddit, stackoverflow, etc. I do not wish to link third party websites due to the risk of these websites going down in the future, so I have only included links to official documentation wherever possible.

------------------------------------------------------------------------------------------------------------------------------

● [Describe security administration and tasks.](https://docs.docker.com/engine/security/)
  
● [Describe the process of signing an image.](https://docs.docker.com/engine/security/trust/content_trust/)

● [Describe default engine security.](https://docs.docker.com/engine/security/security/)

● [Describe swarm default security.](https://docs.docker.com/engine/swarm/how-swarm-mode-works/pki/)

● [Describe MTLS.](https://docs.docker.com/engine/security/https/)

● [Describe identity roles.](https://docs.docker.com/ee/ucp/authorization/define-roles/)

● [Compare and contrast UCP workers and managers.](https://docs.docker.com/ee/ucp/ucp-architecture/)

● Describe the process to use external certificates with [UCP](https://docs.docker.com/ee/ucp/admin/configure/use-your-own-tls-certificates/) and [DTR.](https://docs.docker.com/ee/dtr/admin/configure/use-your-own-tls-certificates/)

Also see: 
https://success.docker.com/article/how-do-i-provide-an-externally-generated-security-certificate-during-the-ucp-command-line-installation




● [Describe and demonstrate that an image passes a security scan.]

● [Describe and demonstrate how to enable Docker Content Trust.]

● [Describe and demonstrate how to configure RBAC with UCP.]

● [Describe and demonstrate how to integrate UCP with LDAP/AD.]

● [Describe and demonstrate how to create UCP client bundles.]
