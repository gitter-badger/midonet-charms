ミドネット
==========

This repository contains Ubuntu Juju Charms to install MidoNet, the distributed virtual network controller for building a network overlay solution (NVO) with OpenStack.

For help with these charms you can visit our community slack channel, as a customer of MEM you can also open a support request.

The community channel is available here: http://slack.midonet.org/ .

Contributing
============
You can report a bug using [MidoNet Issue tracking][jira].

All patches to midonet-charms are submitted to Gerrit, an open source,
web-based code review system. It's publicly hosted on [GerritHub][gerrithub].

To submit a patch, you'll need to sign into GerritHub using your GitHub
account and set up your ssh-key in `Settings->SSH public keys`. If you
need information to set up git review, or git-review workflows, please
check MidoNet Developer's Guide in the [wiki][dev-guide].

Submitting a review is simple, typically:

    git clone https://github.com/midonet/midonet-charms
    git checkout -b your_branch origin/master
    # .. make some changes ..
    git commit -as  # commit your changes, and sign off your commit
    git review master

Your review will now appear on [GerritHub][gerrithub]. Patches must be verified
in order to be merged. Verification must be done by the submitter and involves
the following:
- installing OpenStack Juno on Ubuntu 14.04 with the latest MidoNet OSS version
- testing creation of at least one VM
- ping the internet without associating a floating IP to the VM
- create a L4 load balancer using at least 3 VMs with a http server as backends
- test the load balancer from outside
- associate a floating IP and ping from outside, log into the VM, do a wget to www.midokura.com and any other website
- use iperf to test connectivity to the VM and from the VM to an outside host

After committers approve your change, it will get merged into the main
repository. Then, in the next release of the charm, it will be available in the
juju charms store.

Feel free to join other MidoNet charms developers at #juju-charms on
[midonet-slack] we will be happy to help you get set up.

[jira]: http://midonet.atlassian.net
    "MidoNet Issue tracking"
[gerrithub]: https://review.gerrithub.io/#/q/project:midonet/midonet-charms
    "GerritHub"
[dev-guide]: http://wiki.midonet.org/Developer%27s%20Guide
    "MidoNet developers guide"
[midonet-slack]: https://slack.midonet.org
    "MidoNet Slack channel"


Neutron
=======

MidoNet contains a neutron plugin for OpenStack.
The network controller agent is using the kernel flow datapath from openvswitch-datapath.
No user-space components of OVS are used.

Background
==========

Please watch the following slide for an introduction to MidoNet:
http://www.slideshare.net/takufukushima79/introduction-to-mido-net
