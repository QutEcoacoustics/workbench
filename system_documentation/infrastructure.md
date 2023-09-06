# Infrastructure Requirements


To run your own instance of the workbench you will need the following resources:

- At least one Linux server
  - with a public facing IP address
  - that has docker installed
  - with 4 vCPUs
  - and 16 GB of RAM
- a large amount of storage space
- A domain name that you can point at the server

However a typical instance has the following resources (200 TB of stored audio):

- 1 ✕ load balancer (2 vCPUs, 8 GB RAM)
- 1 ✕ database server (4 vCPUs, 16 GB RAM)
- 2 ✕ web servers (4 vCPUs, 16 GB RAM)
- 4 ✕ worker servers (2 vCPUs, 8 GB RAM)
- a very large amount of network storage space (≈120% of raw audio size)
- A software defined domain name that you can point at the server (e.g. Route 53 or Azure DNS)

All of the above resources can be scaled horizontally as data stored in the workbench grows.

The workbench run in a containerized environment. 

## Optional components

### Analysis 

-  Access to a PBS cluster for analysis 
   -  via SSH, authenticated with a public key
   -  with access to your shared network storage
   -  with access to the REST API of the workbench server
   -  permission to run jobs
   -  permission to run docker containers (or singularity containers)

### Search  
  
You must have:

- A managed Kubernetes cluster
  - Which supports public facing egress and ingress options
- A minimum of 10 VCPUs and 70 GB of RAM
- As the number of embeddings scale, so to does the amount of resources required
  - For 4 billion embeddings you will need 50 vCPUs and 300 GB of RAM
  - (4 billion embeddings indexes 634 years of data)

## Development environment

The developer environment is currently supported via Docker Compose
and is not suitable for production use.

- Development is setup to use VS Code's remote containers feature.
- The development environment mirrors the production environment as closely as possible.
- Recommend specs:
  - WSL2 with Docker integration for Windows development
  - at least 32 GB of RAM