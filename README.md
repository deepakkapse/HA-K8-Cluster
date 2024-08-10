# High Availability Kubernetes Cluster with HAProxy Load Balancer
<img src='https://github.com/deepakkapse/HA-K8-Cluster/blob/main/Images/haproxy_image.jpg' />

## Introduction

This project demonstrates how to set up a High Availability (HA) Kubernetes cluster using HAProxy as a load balancer. The setup is designed to run on EC2 instances with specific security group configurations.

## Why High Availability for Kubernetes Clusters?

High Availability in Kubernetes is crucial for maintaining continuous operations and minimizing downtime. Here's why it's important:

1. **Fault Tolerance**: HA setups ensure that if one component fails, others can take over, preventing system-wide outages.
2. **Load Distribution**: Multiple nodes allow for better distribution of workloads, improving overall performance.
3. **Scalability**: HA clusters can easily scale to handle increased demand.
4. **Maintenance Without Downtime**: Updates and maintenance can be performed on individual components without affecting the entire system.

## HAProxy Load Balancer

HAProxy is used as the load balancer in this setup. It's responsible for:

- Distributing incoming traffic across multiple Kubernetes API servers.
- Providing a single entry point for accessing the Kubernetes cluster.
- Improving fault tolerance by redirecting traffic if one API server becomes unavailable.

## Prerequisites

- AWS account with EC2 instances set up
- Security group with necessary inbound rules configured
- Basic understanding of Kubernetes and Linux administration

## Setup Steps

Follow these steps to set up your HA Kubernetes cluster:

### 1. Prepare the Environment

- Launch EC2 instances for HAProxy, master nodes, and worker nodes.
- Ensure all instances are in the same VPC and can communicate with each other.
- Configure security groups to allow necessary traffic between instances.
<img src='https://github.com/deepakkapse/HA-K8-Cluster/blob/main/Images/instances.png' />
<img src='https://github.com/deepakkapse/HA-K8-Cluster/blob/main/Images/securitygroup.png' />

### 2. Install and Configure HAProxy

- Install HAProxy on the designated load balancer instance.
- Configure HAProxy to distribute traffic to Kubernetes API servers.

### 3. Set Up Kubernetes Master Nodes

- Install Kubernetes components on master nodes.
- Initialize the first master node.
- Join additional master nodes to the cluster.

### 4. Configure Worker Nodes

- Install Kubernetes components on worker nodes.
- Join worker nodes to the cluster.

### 5. Verify Cluster Status

- Check the status of nodes and pods to ensure proper setup.

## Detailed Instructions

For step-by-step instructions, please refer to the [HA-k8-cluster.md](HA-k8-cluster.md) file in this repository. It contains detailed commands and explanations for each step of the setup process.

## Configuration Files

Key configuration files are included in this repository:

- `haproxy.cfg`: HAProxy configuration file
- `kubeadm-config.yaml`: Kubernetes cluster configuration

## Screenshots
- HAProxy Stat Page Dashboard
  <img src='https://github.com/deepakkapse/HA-K8-Cluster/blob/main/Images/haproxydashboard.PNG' />

- Instance Master Node 3 terminated to test High availibility
  <img src='https://github.com/deepakkapse/HA-K8-Cluster/blob/main/Images/instance_afterdelete.png' />

- HAProxy Stat Page Dashboard Highlighting Master node 3 is down after master node 3 hosted ec2 instance is deleted
  <img src='https://github.com/deepakkapse/HA-K8-Cluster/blob/main/Images/haproxydashboard2.PNG' />

- Instance Master Node 3 terminated to test High availibility
  <img src='https://github.com/deepakkapse/HA-K8-Cluster/blob/main/Images/instance_afterdelete.png' />

- Website deployed is still running post the master node 3 is terminated
  <img src='https://github.com/deepakkapse/HA-K8-Cluster/blob/main/Images/websitepage.PNG' />


## Troubleshooting

Common issues and their solutions will be added here based on user feedback and experiences.

## Contributing

Contributions to improve this setup or documentation are welcome. Please submit pull requests or open issues to discuss proposed changes.

## License



## Contact

