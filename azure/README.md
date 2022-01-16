## Description

Playground how to use Ansible to automate cloud provisioning in Azure


## Requirements

- ansible version 2.10
- Install az cli, please refer the [documentation](https://docs.microsoft.com/en-us/cli/azure/install-azure-cli-linux?pivots=apt)


## Installation

Install python-pip

```bash
sudo apt install python3-pip
```

Suggested to using virtualenv, skip if you sure what you are doing,

```bash
pip3 install virtualenv
virtualenv --python=python3 ~/venv
source ~/venv/bin/activate
```

Install Azure dependencies:

```bash
pip install -r requirements.txt --use-feature=2020-resolve
```

install Azure collection hosted in Galaxy:

```bash
ansible-galaxy collection install azure.azcollection
```

#### Sign in to Azure with the Azure CLI

```bash
az login
```


## How to Provisioning

resource group provisioning
```bash
ansible-playbook -i inventories/infra-network-staging/ playbook/create-resource-group.yaml -v
```

network security group provisioning
```bash
ansible-playbook -i inventories/infra-network-staging/ playbook/create-network-security-group.yaml -v
```

virtual network provisioning
```bash
ansible-playbook -i inventories/infra-network-staging/ playbook/create-virtual-networks.yaml -v
```

virtual machine provisioning
```bash
ansible-playbook -i inventories/infra-network-staging/ playbook/create-virtual-machine.yaml -e "password_vm=<password>" -v
```