# Introduction

## About the company
- Parallel Works is a startup that provides a platform for seamless orchestration of AI and HPC workloads across hybrid multi-cloud environments.
- More info: https://parallelworks.com/

## About my role
- Core Platform Software Engineer intern over Summer 2025
- Owned and developed a new feature end-to-end, with main work revolving around the backend using Golang.
- Feature: Single instance management (provisioning, configuration, deletion) via the platform for AWS, GCP and Azure
- Tech stack used here: React, Typescript, Golang, RabbitMQ, MongoDB, Ansible, Bash scripting

## Demo
*NOTE: Due to confidentiality, no actual code will be shown but just screengrabs of work done.*
1. Provisioning, configuration and deletion of instance
2. Snapshots - save a reusable image of the root disk for use in future provisioning
3. Agent - does configuration on instance and also periodic health and metrics updating

## Work done
1. Implement feature flag and toggle for sidebar.
2. Implement listing of instances.
3. Implement provision and deletion of instances for AWS and GCP.
4. Implement cleanup of instances on failure.
5. Show public IP as a field on instance list page.
6. Implement Ansible playbook to do configuration (permissions,installation, enable SSH for specific users) and inject an agent that does reporting of health and resource usage metrics back to the platform.

## Additional demos for AWS and Azure.
- AWS: 

- Azure: