# utopia
This is my infrastructure-as-code playground. With the contents of this
repository I try out some things to implement running infrastructure in a way
that I think is practical, repeatable and useful.

Feel free to borrow any of these idea, and even submit your own as PR's. There
is a [TODO] list of things I'd like to implement. If there's something you'd
like to see implemented, feel free to register an issue describing it.

To actually run this environment, I build it on [Rackspace Public Cloud].

All orchestration is done via [Ansible] and executes against an [OpenStack]
cloud.

To try out this environment yourself, do the following:

``` console
$ git clone https://github.com/odyssey4me/utopia.git ~/code/utopia
$ cd ~/code/utopia
$ virtualenv ~/venvs/utopia
$ source ~/venvs/utopia/bin/activate
$ pip install -r requirements.txt -c constraints.txt
$ ansible-playbook playbooks/site.yml
```

The OpenStack client requires a configuration file for credentials and the API
endpoints. I've provided [a sample clouds.yaml] for anyone to look at - pick the
appropriate profile for your own OpenStack environment.

The [OpenStack inventory plugin for Ansible] accesses the OpenStack API to
dynamically build the inventory of instances present in the cloud.

[a sample clouds.yaml]: https://gist.github.com/odyssey4me/fd340be50301a8b7d6eca46f65866caa
[Ansible]: https://www.ansible.com/
[OpenStack]: https://www.openstack.org/
[OpenStack inventory plugin for Ansible]: https://docs.ansible.com/ansible/2.5/plugins/inventory/openstack.html
[Rackspace Public Cloud]: https://www.rackspace.com/en-gb/cloud/public
[TODO]: TODO.md
