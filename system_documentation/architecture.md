# Architecture

![Architecture diagram](./media/architecture.drawio.svg)


## Optional components

### A front end website / CMS

You may choose any other front end website or CMS to use with the workbench.
We typically partition the workbench and the front end website into separate
subdomains.

### An analysis cluster

The server's analysis is done by running analysis on a cluster. At current
we only support the PBS cluster software. 


### The audio search engine

The audio search engine is a separate service that is used to search for audio
that is similar to a given input audio snippet. It is not required for the
workbench to function.



### DataCite credentials

**Not implemented: this is future work listed here for planning purposes**.

The workbench can be configured to mint DOIs for datasets. This requires
credentials for the DataCite service.