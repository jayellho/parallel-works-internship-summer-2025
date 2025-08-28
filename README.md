# About the company
- Parallel Works is a startup that provides a platform for seamless orchestration of AI and HPC workloads across hybrid multi-cloud environments.
- More info: https://parallelworks.com/

# About my role
- Core Platform Software Engineer intern over Summer 2025.
- Owned and developed a new feature end-to-end, with main work revolving around the backend using Golang.
- Feature: Single instance management (provisioning, configuration, deletion) via the platform for AWS, GCP and Azure.
- Tech stack used here: React, Typescript, Golang, RabbitMQ, MongoDB, Ansible, Bash scripting.

# Demo
*NOTE: Due to confidentiality, no actual code will be shown but just screengrabs of work done. Only GCP is shown for brevity although work was done on all three major clouds.*
### 1. Provisioning, configuration and deletion of instance
- Provisioning and deletion were done using the SDKs for each cloud service provider - Azure, GCP, AWS.
- Configuration was done via an Ansible playbook with several roles, one of which was to install our CLI agent onto the VM, which reports instance health and CPU and/or GPU utilization metrics back to the platform every 30 seconds.
- Interactions between the platform and the agent were authenticated with JSON Web Tokens (JWT).
- Instance information (status, metrics, details) were written / updated / deleted within MongoDB.

https://github.com/user-attachments/assets/1258566d-3f84-4dfb-8a81-5555cc3b93cd

### 2. Snapshots - save a reusable image of the root disk for use in future provisioning
- This involved similarly interacting with the CSP SDKs for Azure, GCP and AWS to do the snapshotting of the root disk for the instance, and also reusing endpoints from the existing `Snapshots` service within the platform to add and delete snapshots.
- These snapshots can then be used as the base images for newly provisioned instances.

https://github.com/user-attachments/assets/28461f62-6011-406e-bef6-e077cb09fafd

### 3. Agent - does configuration on instance and also periodic health and metrics updating
- This involved significant troubleshooting due to authentication issues with JWT and difficulty in debugging due to limited error messages and also slower iteration (needed to wait for instance provision).
- A better approach would have been to inject the agent onto a Docker container and iterate until the agent worked before using the actual instances.
- Specific configuration: installs Python and Goofys, installs CLI agent for monitoring, sets up SSH for user with appropriate permissions, runs user bootstrap script.

https://github.com/user-attachments/assets/2191b186-b1fc-4f32-8244-232ee9965282

# Overall Learning
1. Programming idioms and language quirks for: Golang, MongoDB, React
2. How to design API endpoints and use of related routers (chi, Fiber) and frameworks like Huma (no need to update API documentation with this!)
3. Understanding and modifying a large codebase of millions of lines of code.
4. Communication is key especially in a remote work setting with no physical interaction.

# Work done
### 1. Implement feature flag and toggle for sidebar.

https://github.com/user-attachments/assets/ae9d7f54-96cf-4abe-8778-e319b376167b

https://github.com/user-attachments/assets/856a2bc3-d8ab-463e-8c3d-8b07e14761d9

### 2. Implement listing of instances.



### 3. Implement provision and deletion of instances for AWS and GCP.

https://github.com/user-attachments/assets/6696be39-a3ed-422c-b03d-8f1f54b6f95c

### 4. Implement cleanup of instances on failure.

https://github.com/user-attachments/assets/87a0d859-bfa6-45cc-bf4f-345824c42f99

### 5. Show public IP as a field on instance list page.

https://github.com/user-attachments/assets/fc973ca8-1a9d-4287-892f-b79d7decd689

### 6. Implement Ansible playbook to do configuration (permissions,installation, enable SSH for specific users) and inject an agent that does reporting of health and resource usage metrics back to the platform.

https://github.com/user-attachments/assets/67336382-6d59-4176-b9f6-0f681f6c0d8e

https://github.com/user-attachments/assets/bfec951f-e52c-437b-bdc9-dd213cc14087

https://github.com/user-attachments/assets/305d8202-be75-458d-a87d-5ff8f1ce0b4f
