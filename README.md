# The winter is coming, a little bit less of snowflake servers with Ansible
Once upon a time when containers an immutable infrastructure wasn't a thing I was in a situation where you build it, you shit it, you run it was a thing. There I was responsible for more than a handful linux machines with just a ssh access in my hand. My beard wasn't strong at that time and I was struck by imposter syndrome when I heard about sed, awk, pinging and grepping. Born and bread with CI, Testings and source control it felt very odd to hand craft machines every single time.

## TL;DR
- Install Vagrant
- Install Ansible
- Run `vagrant up`

## Ansible
- The requirement is SSH access to the machines
- Code as documentation
- Idempotent roles
- Fail safe
- Provisioning of multiple machines at the same time

## Vagrant
Vagrant is tool to automate the creation of virtual machines and Ansible is a first class citizen in Vagrant for the provisioning part.

## Docker
Docker is great but it's a different beast and it's optimal to use it for developing your provisioning steps. https://www.quora.com/What-is-the-difference-between-Docker-and-Vagrant-When-should-you-use-each-one/answer/%C3%81d%C3%A1m-G%C3%B6rbe?srid=bUCN the problem is that systemd is not suited to run in a docker container.

However Ansible is great at controlling docker host.

## Windows
https://www.vagrantup.com/docs/provisioning/ansible_local.html
or run Ansible from a docker container.
