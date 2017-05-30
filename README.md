# Zcash Miner

The purpose of this project is to provide mechanisms for developing, testing and deploying Zcash miners.

NOTES
- this project uses git submodules so you will want to clone recursively to have all expected behaviours.

`git clone --recursive git@github.com:svo/zcash-miner.git`

## Setup

Requirements:
- Vagrant (tested with version: 1.9.3)
- VirtualBox (tested with version: 5.1.18 r114002)
- Ansible (tested with version: 2.1.1.0)

Setup environment by using the following: `vagrant up`

## Development

```
vagrant ssh
cd /vagrant
```

## Testing

```
vagrant ssh
cd /vagrant
./pre-commit.sh
```

Jenkins builds on commits and is available at: http://vagrant-zcash-miner-ci.local:8080/

## Build Instance

```
vagrant ssh
aws configure
cd /vagrant/terraform
terraform apply
```

## Provision Instance

```
vagrant ssh
cd /vagrant
./provision.sh <path-to-private-key> <ip-for-instance>
```

## Running Miner

```
~/silentarmy/silentarmy -c stratum+tcp://us1-zcash.flypool.org:3333 -u t1bv8jEyXEJ29juWjezwRA1zL6fPgBi5aE3
```
