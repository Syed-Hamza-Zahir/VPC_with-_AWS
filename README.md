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

## What are CIDR block – how to create one
CIDR (Classless Inter-Domain Routing) blocks are groups of addresses that share the same prefix and contain the same number of bits

## What is an NACLs - use case of NACL
Network Access Control (NAC) is a computer networking solution that uses a set of protocols to define and implement a policy that describes how to secure access to network nodes by devices when they initially attempt to access the network.

limiting user access
blocks access from endpoint devices that do not comply with corporate security policies.

Access Control Lists (ACL)
• A set of rules used to control traffic in and out of a firewall, router, or multilayer switch 
• Each packet is compared to the rules in the ACL and processed accordingly 
• Rules can include: Protocol, Source IP address, Destination IP address, Source port, Destination port 
• ACL actions are usually permit or deny 
• Most ACLs have an implicit “deny” at the end. If you configure deny rules, you need to have a “permit all” rule at the end to allow all other traffic

# Creating and seting up a VPC for my app
![vpc.png](/vpc.png)

![diagram.jpg](/diagram.jpg)

## Step 1: Create a VPC
1. On the AWS Dashboard click on `Your VCP`and select `Create VPC`

2. Create a **Name tag** , add `10.0.0.0/16` to the **IPv4 CIDRblock** and click `Create VPC`


## Step 2: Create Internet Gateway
1.  Select `Internet Gateways` and select `Create Internet gateway` 

2. Add a Name tag then click `Create Internet Gateway` 

3. Select `action` and `Attach VPC`. Attach the VPC you created previously.

4. Select `Attach Internet Gateway`


## Step 3: Creating a Subnet

1. Click on `Subnet` and select `Create subnet` 

2. Create a public subnet:

- Select the VPC you previously created 
- Add `10.0.11.0/24` to the **IPv4 CIDRblock** 

## Step 4: Creating a Route Table

1. On the left hand toolbar click on `route table`

2. Create a route table 

3. Select the route table and click `Action` then `Edit routes`

4. Then add a destination and target. The target I used was the internet gateway created earlier. Then click `save routes`

5. Click on subnet associations and then `edit subnet associations`. Select the public subnet and click on save.

## Step 5: Creating security groups

1. Create a security group for the app:

Inbound rules:
- HTTP: Anywhere
- SSH: My IP

**Step 6: Create the EC2 instances**

1. Create the app EC2 instance

- AMI: Ubuntu
- Instance type: t2 micro
- Instance Details: Your VPC -> Public Subnet -> Assign public ip enabled
- Security Group: app security group

