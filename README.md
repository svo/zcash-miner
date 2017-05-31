# Zcash Miner

The purpose of this project is to provide mechanisms for developing, testing and deploying Zcash miners.

__Donations:__ if you find this project helpful I suggest donating to the creator of _silentarmy_ via __Zcash__ address `t1cVviFvgJinQ4w3C2m2CfRxgP5DnHYaoFC`. Donations to myself also appreciated at __Zcash__ address: `t1bv8jEyXEJ29juWjezwRA1zL6fPgBi5aE3`.

__NOTES:__ this project uses git submodules so you will want to clone recursively to have all expected behaviours.

```
git clone --recursive git@github.com:svo/zcash-miner.git
```

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

## Build EC2 Instance

```
vagrant ssh
aws configure
cd /vagrant/terraform
terraform apply
```

## Provisioning

### Provision Instance

```
vagrant ssh
cd /vagrant
./provision.sh <path-to-private-key> <ip-for-instance>
```

### Provision Instance/s By IP/DNS

Create an `ansible_hosts` file with the IP/DNS for the Virtual Machine/s then:

```
ANSIBLE_HOST_KEY_CHECKING=False ansible-playbook --private-key <path-to-private-key> -u <username> -i ansible_hosts ansible/playbook.yml
```


## Running Miner

```
~/silentarmy/silentarmy -c stratum+tcp://us1-zcash.flypool.org:3333 -u t1bv8jEyXEJ29juWjezwRA1zL6fPgBi5aE3
```
