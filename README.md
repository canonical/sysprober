# sysprober

![PyPI - Version](https://img.shields.io/pypi/v/sysprober)
![PyPI - Downloads](https://img.shields.io/pypi/dm/sysprober)
![GitHub License](https://img.shields.io/github/license/canonical/sysprober)
[![Matrix](https://img.shields.io/matrix/ubuntu-hpc%3Amatrix.org?logo=matrix&label=ubuntu-hpc)](https://matrix.to/#/#hpc:ubuntu.com)

A Python library for probing system-level information about a machine.

sysprober provides a set of utilities for retrieving details about the CPU,
memory, network interfaces, PCI devices, and package manager on a Linux system.
It is designed to be used by charms and other tools that need to gather
system information programmatically.

Current probing modules shipped in the sysprober package include:

#### `from sysprober import ...`

* `cpu`: Probe CPU architecture, model, cores, and frequency.
* `memory`: Probe total and available memory.
* `network`: Probe network interfaces, IP addresses, and MAC addresses.
* `pci`: Probe PCI device information.
* `pkgmanager`: Detect the system package manager.

## ✨ Getting Started

### Installation

#### Option 1: Install from PyPI

```shell
python3 -m pip install sysprober
```

#### Option 2: Install from source

```shell
pip install .
```

### Usage

```python
from sysprober import cpu, memory, network

# Probe CPU information
cpu_info = cpu.probe()
print(cpu_info.architecture)

# Probe memory information
mem_info = memory.probe()
print(mem_info.total)

# Probe network interfaces
net_info = network.probe()
for iface in net_info.interfaces:
    print(iface.name, iface.ip_address)
```

## 🤔 What's next?

If you want to learn more about all the things you can do with sysprober,
here are some further resources for you to explore:

* [Open an issue](https://github.com/canonical/sysprober/issues/new?title=ISSUE+TITLE&body=*Please+describe+your+issue*)
* [Ask a question](https://discourse.ubuntu.com/c/project/hpc/151)

## 🛠️ Development

The project uses [tox](https://tox.wiki/) for development,
which provides some useful commands that will help you while hacking on sysprober:

```shell
tox -e fmt           # Apply formatting standards to code
tox -e lint          # Check code against coding style standards
tox -e network       # Run unit tests
```

If you're interested in contributing your work to sysprober,
take a look at our [contributing guidelines](./CONTRIBUTING.md) for further details.

## 🤝 Project and community

sysprober is a project of the [Ubuntu High-Performance Computing community](https://ubuntu.com/community/governance/teams/hpc).
Interested in contributing bug fixes, new editors, documentation, or feedback? Want to join the Ubuntu HPC community? You've come to the right place 🤩

Here's some links to help you get started with joining the community:

* [Ubuntu Code of Conduct](https://ubuntu.com/community/ethos/code-of-conduct)
* [Contributing guidelines](./CONTRIBUTING.md)
* [Join the conversation on Matrix](https://matrix.to/#/#hpc:ubuntu.com)
* [Get the latest news or ask and answer questions on the Ubuntu Discourse](https://discourse.ubuntu.com/c/project/hpc/151)

## 📋 License

sysprober is free software, distributed under the Apache Software License, version 2.0.
See the [Apache-2.0 LICENSE](./LICENSE) file for further details.
