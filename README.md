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
You don't have to know about docker-machine. You can run multiple virtualized nodes in other ways if needed.

● [Describe and demonstrate how to extend the instructions to run individual containers into running services under swarm.](https://docs.docker.com/engine/swarm/services/)
● [Describe the importance of quorum in a swarm cluster.](https://docs.docker.com/engine/swarm/raft/)
● [Describe the difference between running a container and running a service.]
● [Interpret the output of “docker inspect” commands.]
● [Convert an application deployment into a stack file using a YAML compose file with "docker stack deploy"]
● [Manipulate a running stack of services.]
● [Describe and demonstrate orchestration activities.]
● [Increase the number of replicas.]
● [Add networks, publish ports.]
● [Mount volumes.]
● [Describe and demonstrate how to run replicated and global services.]
● [Apply node labels to demonstrate placement of tasks.]
● [Describe and demonstrate how to use templates with “docker service create”.]
● [Identify the steps needed to troubleshoot a service not deploying.]
● [Describe how a Dockerized application communicates with legacy systems.]
● [Describe how to deploy containerized workloads as Kubernetes pods and deployments.]
● [Describe how to provide configuration to Kubernetes pods using configMaps and secrets.]
