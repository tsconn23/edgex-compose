## Edgex Docker Compose (Minnesota)

This branch contains the docker compose files that pull and run the **EdgeX Minnesota** release images.

These compose files are auto generated from the multiple files contained in the `compose-builder` folder. 
See Compose Builder [README](https://github.com/edgexfoundry/edgex-compose/blob/minnesota/compose-builder/README.md) for details.

### Compose Tool

The Makefile in this folder expects the `docker compose` CLI command.
The old stand-alone `docker-compose` tool is no longer supported.
See https://docs.docker.com/compose/install/ for installation details for the latest `docker compose` CLI command.

### Compose Files

This folder contains the following generated compose files:

> **Note to Developers:**
>
> - *DO NOT EDIT the files directly for permanent changes. Make all permanent changes to the source compose files in the `compose-builder` folder and then regenerate these files*
> - Use `make build` from **Compose Builder** to regenerate all the following compose files.
> - See each description for the convenience `make` commands that are provided to work with each of these compose files.

- **docker-compose.yml**
    Contains all the services required to run in secure configuration. Includes the Device Virtual & Device REST device services and the UI.
    **Make Commands** 
    
     - Use `make run <service(s)>` and `make down` to start and stop the services using this compose file.
    
     - Use `make pull <service(s)>` to pull all or some images for the services in this compose file.
    
     - Use `make get-token` to generate a Kong access token for remote access of the services running from this compose file.
    
- **docker-compose-arm64.yml**
    Contains all the services required to run in secure configuration on `ARM64` system.  Includes the Device Virtual & Device REST device services and the UI.
    **Make Commands** 
    
     - Use `make run arm64` and `make down` to start and stop the services using this compose file.
     - Use `make pull arm64 <service(s)>` to pull all or some images for the services in this compose file.
     - Use `make get-token arm64` to generate a Kong access token for remote access of the services running from this compose file.
    
- **docker-compose-with-app-sample.yml**
    Contains all the services required to run in secure configuration with Sample application service.  Includes the Device Virtual, Device REST, UI & App Sample services. Use this version when using the UI to make changes to the configurable pipeline on the Sample application service.
    **Make Commands**

    - Use `make run app-sample` and `make down` to start and stop the services using this compose file.
    - Use `make pull app-sample <service(s)>` to pull all or some images for the services in this compose file.
    
- **docker-compose-with-app-sample-arm64.yml**
    Contains all the services required to run in secure configuration with the Sample application service on `ARM64` system .  Includes the Device Virtual, Device REST, UI & App Sample services. Use this version when using the UI to make changes to the configurable pipeline on the Sample application service.

    **Make Commands**

    - Use `make run no-secty app-sample arm64` and `make down` to start and stop the services using this compose file.
    - Use `make pull no-secty ui app-sample <service(s)>` to pull all or some images for the services in this compose file.

- **docker-compose-no-secty.yml**
    Contains just the services needed to run in non-secure configuration.  Includes the Device Virtual & Device REST device services and the UI.
    **Make Commands**

    - Use `make run no-secty` and `make down` to start and stop the services using this compose file.
    - Use `make pull no-secty <service(s)>` to pull all or some images for the services in this compose file.

- **docker-compose-no-secty-alvarium.yml**
  Contains the EdgeX services needed to run in non-secure configuration, along with Alvarium services for scoring support.  Includes the Device Virtual & Device REST device services and the UI.
  **Make Commands**

    - Use `make run no-secty alvarium` and `make down no-secty alvarium` to start and stop the services using this compose file.
    - Use `make pull no-secty alvarium <service(s)>` to pull all or some images for the services in this compose file.

- **docker-compose-no-secty-arm64.yml**
    Contains just the services needed to run in non-secure configuration on `ARM64` system.  Includes the Device Virtual & Device REST device services and the UI.

    **Make Commands**

    - Use `make run no-secty arm64` and `make down` to start and stop the services using this compose file.
    - Use `make pull no-secty arm64 <service(s)>` to pull all or some images for the services in this compose file.


- **docker-compose-no-secty-with-app-sample.yml**
  Contains just the services needed to run in non-secure configuration with Sample application service.  Includes the Device Virtual, Device REST, UI & App Sample services. Use this version when using the UI to make changes to the configurable pipeline on the Sample application service.
  **Make Commands**

  - Use `make run no-secty app-sample` and `make down` to start and stop the services using this compose file.
  - Use `make pull no-secty app-sample <service(s)>` to pull all or some images for the services in this compose file.

- **docker-compose-no-secty-with-app-sample-arm64.yml**
  Contains just the services needed to run in non-secure configuration with the Sample application service on `ARM64` system .  Includes the Device Virtual, Device REST, UI & App Sample services. Use this version when using the UI to make changes to the configurable pipeline on the Sample application service.

  **Make Commands**

  - Use `make run no-secty app-sample arm64` and `make down` to start and stop the services using this compose file.
  - Use `make pull no-secty app-sample <service(s)>` to pull all or some images for the services in this compose file.

### TAF Compose files

The compose files under the `taf` subfolder are used for the automated TAF tests. These compose files are also generated from `Compose Builder` when the `make build` command is used.

### Additional make commands

- `make clean`

    Runs `down` command and removes all stopped containers, all volumes and all networks used by the EdgeX stack. Use this command when needing to do a fresh restart.
    
- `make get-token`
    For secure mode only. Runs command via docker to generate a new API Gateway token.

- `make get-consul-acl-token`
  For secure mode only. Runs command via docker to retrieve a Consul Access token.

### Additional compose files

- **docker-compose-portainer.yml**
    Stand-alone compose file for running Portainer which is a  Docker container management tool. Visit here https://www.portainer.io/ for more details on Portianer.
    Use `make portainer`and `make portainer-down` to start and stop Portainer.
