## Vagrant - Apache
[![MIT licensed](https://img.shields.io/badge/license-MIT-blue.svg)](https://raw.githubusercontent.com/taherbs/Puppet5-ServerAgent/master/LICENSE)

A Vagrant environment to deploy an apache server.<br />
* Server runs on **Ubuntu16.04**.

### Usage:

Provision the VM and ssh it:

```bash
vagrant up
vagrant ssh "node_name"
```

### Configure Vagrant Nodes and Parameters

You can configure the Vagrant project nodes and params by editing the [nodes.json](./nodes.json).

### Useful commands: 

```bash
vagrant destroy #delete the VM, and you will lose any and all work on the instance
vagrant up      #create a VM
vagrant suspend #suspend the vm 
vagrant resume  #resume a suspended vm
```
