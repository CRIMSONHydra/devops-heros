# VPC - Virtual Private Cloud (Networking)

## What is VPC?
A VPC is your own private network inside AWS. You choose the IP range, create subnets, and control what can talk to what. Your EC2 and RDS resources live inside a VPC.

## CIDR
CIDR is a way to write an IP range, like `10.0.0.0/16`. The number after the slash shows how big the range is(bytes prefix of the network ip adress): a smaller number means more IP addresses. `/16` gives about 65,000 addresses and `/24` gives 256.

## Subnets
A subnet is a smaller part of your VPC's IP range. Each subnet sits in one Availability Zone. You split a VPC into subnets to separate things like web servers and databases.

## Route tables
A route table is a set of rules that tells network traffic where to go. For example, a rule can say "send internet traffic to the Internet Gateway". Each subnet is linked to one route table.

## Internet Gateway
An Internet Gateway (IGW) connects your VPC to the internet. It lets resources with public IPs send and receive traffic. Without it, your VPC has no internet access.

## NAT Gateway
A NAT Gateway lets private resources go out to the internet, for example to download updates. The internet cannot start a connection back in. It sits in a public subnet and costs money per hour.

## Security Groups
A security group is a firewall at the instance level. It is stateful, meaning return traffic is allowed automatically. It only has allow rules, and everything else is blocked.

## Network ACLs
A Network ACL is a firewall at the subnet level. It is stateless, so you must allow traffic both in and out. It supports both allow and deny rules, and rules are checked in number order.

## Public vs private subnet
A public subnet has a route to the Internet Gateway, so its resources can be reached from the internet. A private subnet has no direct route to the internet, so it is safer for databases and backend apps. Private resources can use a NAT Gateway for outbound access.
