## Core Service

### VM

### WEB APP

### Storage

### Network

## High Availability

### Resource Manager

### HA and Redundancy

### Load-balancing

### Scale

### Database

### Network Traffic and Routing

### Monitoring and Troubleshooting

## Security

### DR-Backups and Replication

### Encryption

### Securing information - Key Vault

### Security Center and Updates

## Extras

### ML and AI

### Automation

### Containers

### IoT

### Serverless

## C1
- Create an account with gibhub. Real good!
- Links need to be reviewed (Extra dash and space)
- On-premises ==> Server
- IaaS = Infrastructure as a Service ==> Managing VMs and Applications level
- PaaS = Platform as a Service ==> Managing Application level
- SaaS = Software as a Service ==> Access to the Application level
- SONiC: Software for Open Networking in the Cloud
- Git and Maven

## C2
- Install CLI 2.0
- Page 10: Second paragraph in point 4 and 7  with two comas
- Page 14: `sudo apt-get update && sudo apt-get install -y lamp-server^`
-

## C3
- App Service Plan  
- Create the app-level credential in the repository is  missing
- Viewing Diagnostic logs: Application Logging (Filesystem). WHAT is the level you recommend for the exercise??
- Swap menu is different

## C4
- Managed disks
- Access to premium SSD disks: `D2S_V3`, `Fs`, `Gs`, `Ls`
- Access to standard SSD or HDD disks: `D`, `A`, `F`, and `M`
- I suggest to add link where you can find more information about disk in Azure
- Table storage was not clear. This is a point that might need more work to explain for beginners.
- `QueueService` has been renamed to `QueueServiceClient`. https://github.com/MicrosoftDocs/azure-docs/issues/42228
- Script `storage_queue_demo.py` is not working.
- CLI 2.0 local: Install extra packages like `jq`
- I would recommend to use `pip3` on Linux distros since the default is `Python2`

## C5
- Typo in first paragraph 5.1.2.
- The TRY NOW in page 13 should mention the Jump-Box and Web VM

## C6
- Role-based access control (RBAC)
- The command `az resource list --tag workload=development` did not work
- Page 11 there is a typo in the title, end of 6.2.2
- Page 12 The link has an space before Azure
- Honest at the end of chapter 6??

## C7
- Page 2 Typo in the first paragraph
- Still does not materialize the creation of a load balancer in this chapter
- Availability Set
- Availability Zone

## C8 Load-balancing Applications
- Load-balancer: Layer 4 - Network traffic (Transport layer)
- Application Gateway: Layer 7 - Application data (Application  layer)
- Health probe: Port-based (TCP port 80) // HTTP Path-based (code 200)
- Path-based: Use Interval (every 15 secs) and Threshold (after two intervals)
- Session affinity mode
- Page 17 show the ssh switch that allow connection to VM1

## C9 Applications that Scale
- Resizing VM Vertically and Horizontally
- VM Scale Sets
- How do you prevent DDoS attack and auto-scale?

## C10  Global Cosmos DB
- SLQ and noSQL
- 
