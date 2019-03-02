#### Overview

This playbook installs and configures [Pixelfed](https://pixelfed.org/), "A
free and ethical photo sharing platform, powered by ActivityPub federation.",
on your machine.

**Important**: This role is generally ready-to-use, however due to the ongoing
heavy development of Pixelfed, that may change. I'll try to keep this updated
as good as possible.

#### Requirements

* A debian-based machine with administrative access
* A domain with an A- / AAAA-record pointed to the machine
* Configure all the variables in `vars/main.yml`
* Create a `hosts`-file that contains the host that should be configured

Functionality has been tested on Debian (Jessie, Stretch) and Ubuntu (16.04,
18.04); it should work with most Debian-based distributions. If you don't have
prepared Ansible-compatibility on your remote host (or if you are unsure),
please make sure you execute the following command as root before attempting to execute
this playbook:

```
(test -e /usr/bin/python && test -d /etc/ca-certificates) || (apt -y update && apt install -y python-minimal python-apt ca-certificates unzip)
```

In case you are wondering what this does: It installs the bare minimum for Ansible to work.

#### Usage

`ansible-playbook -kK -i hosts site.yml`

##### Why are you not utilizing the `postgres_*`-modules of Ansible?
I couldn't get them to work, no matter what I tried. If you have a solution,
I'm more than happy to take Pull-Requests.

