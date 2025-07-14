# Troubleshooting Notes

## Problem

While running sudo dnf install -y kubelet kubeadm kubectl on kubenode1, kubenode2 received the following error:

Error:
 Problem: cannot install the best candidate for the job
  - nothing provides conntrack-tools needed by kubelet-1.30.14-150500.1.1.x86_64 from kubernetes
  
## Solution

Needed to install conntrack-tools and its required libraries (Manually downloaded from https://rpmfind.net)

- conntrack-tools-1.4.7-4.el9_5.x86_64.rpm
- libnetfilter_queue-1.0.5-1.el9.x86_64.rpm
- libnetfilter_cttimeout-1.0.0-19.el9.x86_64.rpm
- libnetfilter_cthelper-1.0.0-22.el9.x86_64.rpm

## Note kubectl did not experience this, required packages were already installed.

## Problem

When initializing the Cluster with kubeadm init (on kubectl)

[@kubectl ~]# sudo kubeadm init --pod-network-cidr=192.168.0.0/16
I0708 09:23:06.635474    3257 version.go:256] remote version is much newer: v1.33.2; falling back to: stable-1.30
[init] Using Kubernetes version: v1.30.14
[preflight] Running pre-flight checks
        error execution phase preflight: [preflight] Some fatal errors occurred:
        [ERROR NumCPU]: the number of available CPUs 1 is less than the required 2
		
## Solution

Increase CPU allocation to at least 2 vCPUs

## Temporary workaround

You can bypass the CPU check for testing by adding the flag

sudo kubeadm init --pod-network-cidr=192.168.0.0/16 \
  --ignore-preflight-errors=NumCPU