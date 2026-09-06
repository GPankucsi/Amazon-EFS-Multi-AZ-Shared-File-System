# Amazon EFS Multi-AZ Shared File System

## Overview

In this project, I built and tested a shared file system using Amazon EFS and Amazon EC2 instances across multiple Availability Zones.

The objective was to understand how Amazon EFS provides shared file storage that can be accessed by multiple EC2 instances using the NFS protocol.

## Architecture

The architecture consists of:

- Amazon EC2 instances running Amazon Linux 2023
- Amazon EFS file system
- EFS mount targets in multiple Availability Zones
- Security Groups controlling SSH and NFS traffic
- NFS protocol for communication between EC2 and EFS

![EFS Architecture](architecture/efs-architecture.png)

## AWS Services Used

- Amazon EC2
- Amazon EFS
- Amazon VPC
- Security Groups

## What I Built

1. Created a security group for the EC2 instances.
2. Allowed SSH access to the instances.
3. Allowed NFS traffic on TCP port 2049.
4. Created an Amazon EFS file system.
5. Configured EFS mount targets for the Availability Zones.
6. Created an EFS mount point on the EC2 instances.
7. Installed the NFS client.
8. Mounted the EFS file system using NFS.
9. Created a test file on the EFS file system.
10. Installed `amazon-efs-utils`.
11. Mounted EFS using the EFS mount helper with TLS encryption in transit.

## Mounting EFS

The EFS file system was mounted to:

```bash
~/efs-mount-point
