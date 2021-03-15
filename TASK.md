# Task list

- [x] 1. Create Kubernetes cluster using Vagrant in VirtualBox VM (or multiple VMs) using method you prefer
  - > **RESULT** took base roles and vagrantfile from [https://github.com/hajdaini/k8s-cluster-vagrant-ansible]
- [x] 2. Install and configure Apache Kafka
- [x] 3. Create 2 topics in Kafka called 'input' and 'output'
- [x] 4. Create consumer and producer program in any programming language (preferable Golang or Python)
  - [x] 4.1. make producer continuously write messages to 'input' topic with epoch timestamp in MS
  - [x] 4.2. make consumer that reads from 'input' topic, transforms input message to date string (must be in RFC 3339) and sends to topic 'output'
- [x] 5. Deploy both applications (producer and consumer) to k8s cluster
- [ ] 6. Install Prometheus, Grafana to k8s cluster
- [ ] 7. Find a way to export Kafka metrics and metrics from applications (producer, consumer) to Prometheus and visualize them using Grafana dashboard
- [x] Requirements:
  - [x] 8.  VM, k8s cluster, Kafka, your application, Prometheus and Grafana deployment/provisioning/configuration MUST be automated (by any means, preferably Ansible)
  - [x] 9. Solution MUST NOT require installation of any additional packages on host machine except VirtualBox and Vagrant
  - [ ] 10. Basic documentation MUST be provided (how-to connect to cluster, access metrics and so on)
  - [x] 11. Solution MUST run on host machine under any operating system
