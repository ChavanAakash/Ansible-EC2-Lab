# Security notes

- Keep SSH private keys and `.pem` files out of GitHub.
- Allow SSH to Master only from your own IP.
- Allow SSH to the Slaves from the Master security group.
- Use private IPs for Master-to-Slave traffic in the same VPC.
- Keep real credentials out of inventory and YAML files.
