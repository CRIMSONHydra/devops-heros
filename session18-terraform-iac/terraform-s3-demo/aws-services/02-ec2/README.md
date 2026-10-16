# EC2 - Elastic Compute Cloud (Compute)

## What is EC2?
EC2 gives you virtual servers in the cloud. You pick the size and the operating system, and you pay only for the time it runs. It is like renting a computer from AWS.

## AMI
An AMI (Amazon Machine Image) is a template used to start an instance. It contains the operating system and any software already installed. You can use AWS-made AMIs or make your own.

## Instance types
An instance type decides how much CPU, memory, storage, and network the server has. Names look like `t3.micro` or `m5.large`. The letter shows the purpose (t = general, c = compute, r = memory), and the size shows how big it is.

## Key pairs
A key pair is a public key and a private key used to log in to an instance safely. AWS keeps the public key, and you keep the private key file (`.pem`). If you lose the private key, you cannot log in with it.

## Security Groups
A security group is a virtual firewall for an instance. It decides which traffic can come in and go out, by port and IP address. For example, allow port 22 for SSH and port 80 for web traffic.

## EBS
EBS (Elastic Block Store) is a hard disk for your EC2 instance. Data stays on it even when the instance is stopped. You can also take snapshots to back it up.

## Public vs private IP
A private IP is used inside your VPC and cannot be reached from the internet. A public IP can be reached from the internet, but it can change when you stop and start the instance. An Elastic IP is a public IP that stays fixed.

## Instance lifecycle
An instance goes through these states: pending, running, stopping, stopped, and terminated. While stopped, you do not pay for compute, but you still pay for the EBS disk. Terminated means it is deleted for good.

## Common use cases
- Host websites and APIs.
- Run backend apps and batch jobs.
- Run databases that you manage yourself.
- Create dev and test machines.
