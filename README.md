# sdia-integration


## Architecture 
![SDIA Architecture](https://raw.githubusercontent.com/qcdia-sdia/sdia-orchestrator/master/images/Untitled%20drawing.png)

![Example Sequence Diagram](https://raw.githubusercontent.com/qcdia-sdia/sdia-integration/main/images/seq.png)


## SDIA-Orchestrator
Summary: Orchestrates the execution of TOSCA workflows. Generates declarative workflows which are automatically generated by the orchestrator based on nodes, relationships, and groups defined in the topology. Orchestrates the execution of imperative workflows which are manually specified.  

## Infrastructure Planner 
Summary: Generates valid infrastructure TOSCA description that can create a declarative workflow 
Input TOSCA Template with software components, policies and  partial or no infrastructure
Output  TOSCA Template with software components, policies and infrastructure


## Infrastructure Provisioner 
Summary: Cloud infrastructure API integrator. 
Input: TOSCA provision workflow
Output: TOSCA Template with node states (running, stopped, deleted,error, etc)

## Deployer 
Summary: Deploys software on infrastructure   
Input: TOSCA provision workflow
Output: TOSCA Template with node states (running, stopped, deleted,error, etc)

## Tosca Parser 
Summary: Can query TOSCA templates to get nodes, node names, etc.
REST API: https://app.swaggerhub.com/apis/skoulouzis/tosca-sure/1.0.1
CloudStorm https://cloudsstorm.github.io/ 
Summary: Performs cloud provisioning and configurations. Providers (EGI,ExoGENI, AWS)
Input:  CloudStorm topology language 
Output:  CloudStorm topology language 


## TOSCA Definitions 
Summary: TOSCA types, nodes, interfaces etc. adapted for the SDIA framework 


## External Components    

### TOSCA storage (MongoDB https://www.mongodb.com/, GIT)
Summary: DB to store TOSCA template documents 

### Ansible Playbook executor (Semaphore https://github.com/ansible-semaphore/semaphore )
Summary: Executes ansible playbooks 
REST API: https://ansible-semaphore.github.io/semaphore/

### Playbook project storage (MySQL https://www.mysql.com/ )
Summary: Used by the ansible executor to store playbook projects 
Metrics DB (Prometheus https://prometheus.io/ ) 
Summary: Stores application and infrastructure metrics 


## Install


All components of this architecture are build as docker containers. 
To quickly run the engine use this [docker-compose.yaml](./blob/master/docker-compose.yml)
```
sudo docker stack deploy qcdie -c docker-compose.yml
```




