# Infrastructure


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

All of the above resources can be scaled horizontally as the size of your data
that is stored in the workbench grows.

