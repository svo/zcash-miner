Zcash Miner
==

The purpose of this project is to provide mechanisms for developing, testing and deploying a Zcash miner.

NOTES
- this project uses git submodules so you will want to clone recursively to have all expected behaviours.

`git clone --recursive git@github.com:svo/zcash-miner.git`

Setup
--

Requirements:
- Vagrant (tested with version: 1.9.3)
- VirtualBox (tested with version: 5.1.18 r114002)
- Ansible (tested with version: 2.1.1.0)

Setup environment by using the following: `vagrant up`

Development
--

```
vagrant ssh
cd /vagrant
```

Testing
--

```
vagrant ssh
cd /vagrant
./pre-commit.sh
```

Jenkins builds on commits and is available at: http://vagrant-zcash-miner-ci.local:8080/
