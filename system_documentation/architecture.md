# Architecture

![Architecture diagram](./media/architecture.drawio.svg)


## Optional components

### A front end website / CMS

You may choose 

### An analysis cluster

The server's analysis is done by running analysis on a cluster. At current
we only support the PBS cluster software. 

You must have:

- SSH access to the cluster head node
- HTTPS access from the cluster workers to the workbench server
- Access to the same shared network storage as the workbench server
  - (we intend to remove this requirement in the future)

### The audio search engine

The audio search engine is a separate service that is used to search for audio
that is similar to a given input audio snippet. It is not required for the
workbench to function.

You must have:

- A managed Kubernetes cluster
- A minimum of 10 vCPUs and 70 GB of RAM
- As the number of embeddings scale, so to does the amount of resources required
  - For 4 billion embeddings you will need 50 vCPUs and 300 GB of RAM
  - (4 billion embeddings indexes 634 years of data)

### DataCite credentials

**Not implemented: this is future work listed here for planning purposes**.

The workbench can be configured to mint DOIs for datasets. This requires
credentials for the DataCite service.