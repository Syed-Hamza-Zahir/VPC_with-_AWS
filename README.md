# VPC_with_AWS


## Virtual Private Cloud 

• A private cloud is a cloud computing model that involves a secure cloud based environment where only the specified organization can access its resources.

• Data center may be wholly in-house on the company’s premises, or provided by a third party 

• can configure the network by defining IP address range, creation of subnets, and configuration of route tables and network gateways.

![vpc.jpg](/vpc.jpg)

## What is an internet gateway
A point where all traffic between the VPC and internet passes 

## What is a Subnet
A subnet, or subnetwork, is a segmented piece of a larger network. One goal of a subnet is to split a large network into a grouping of smaller, interconnected networks to help minimize traffic.

Groups of isolated resources can be placed in each segment of a VPC's IP address ranges
Can be used to limit IP's used

## Why Subnet? 
• You have a fixed block of IP addresses you must work with. You can’t use any other addresses 
• You need to divide your network into smaller subnetworks 
- Security – separate devices into their own segments (e.g. Servers, together)
- Traffic management – limit the impact of broadcasting to a smaller group

## What are cidr block – how to create one
CIDR blocks are groups of addresses that share the same prefix and contain the same number of bits

## What is an NACLs - use case of NACL
Network Access Control List (ACL)
Network Access Control (NAC) is a computer networking solution that uses a set of protocols to define and implement a policy that describes how to secure access to network nodes by devices when they initially attempt to access the network.

limiting user access
blocks access from endpoint devices that do not comply with corporate security policies.

Access Control Lists (ACL)
• A set of rules used to control traffic in and out of a firewall, router, or multilayer switch 
• Each packet is compared to the rules in the ACL and processed accordingly 
• Rules can include: Protocol, Source IP address, Destination IP address, Source port, Destination port 
• ACL actions are usually permit or deny 
• Most ACLs have an implicit “deny” at the end. If you configure deny rules, you need to have a “permit all” rule at the end to allow all other traffic
