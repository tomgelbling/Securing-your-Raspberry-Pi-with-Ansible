# Securing your Raspberry Pi with Ansible

Ansible playbook to secure your Raspberry Pi.
Based on [Securing your Raspberry Pi](https://www.raspberrypi.org/documentation/configuration/security.md)  by the Raspberry Pi Foundation.

## What will be achieved by this Ansible playbook?

The playbook will perform configuration modifications in the following areas.

**Raspbian users**
* Change the password of the pi user
* Create an alternative superuser
* Make sudo require a password

**Software package updates**
* Establish Cronjob to update the openssh-server package on a daily basis

**SSH**
* Set users that are allowed to use SSH
* Set users that are not allowed to use SSH
* Establish key-based authentication and disable all other authenticaton methods

**Firewall**
* Install & enable ufw and fail2ban
* Set default and ssh firewall rules

---

## Prerequisites

The following software packages have to be installed on your local machine and the Raspberry Pi.

**On your local machine**
* Python 2.6 or later
  * [Python BeginnersGuide](https://wiki.python.org/moin/BeginnersGuide/Download)


* Ansible
  * [What version to pick?](http://docs.ansible.com/ansible/latest/intro_installation.html#what-version-to-pick)
  * [Installing the Control Machine](http://docs.ansible.com/ansible/latest/intro_installation.html#installing-the-control-machine)


* For macOS and Linux only
  * [Install sshpass from source](https://gist.github.com/arunoda/7790979#installing-from-the-source)

**On your Raspberry Pi**
* Raspbian
  * [Latest Raspbian images](https://www.raspberrypi.org/downloads/raspbian/)
  * [Installing Raspbian](https://www.raspberrypi.org/documentation/installation/installing-images/)


* Python 2.6 or later
  * [Python BeginnersGuide](https://wiki.python.org/moin/BeginnersGuide/Download)

---

## Deployment

This chapter describes how to
* get a copy of the project.
* edit the config files.
* run the Ansible playbook to secure your Raspberry Pi.

**How to get a copy of the project**

```
git clone https://github.com/tomgelbling/Securing-your-Raspberry-Pi-with-Ansible.git
cd Securing-your-Raspberry-Pi-with-Ansible/
```


**How to edit the config files**

Add your Raspberry Pi IP address to the pi host group
```
echo "192.168.2.110" >> hosts
```

Add your public key to the authorized_keys files
```
cat /.ssh/id_rsa.pub >> roles/security/files/authorized_keys
```

Edit the variables file to set e.g. the custom password for the pi user, the name of the alternative user etc.
```
vim roles/security/vars/main.yaml
```



**How to run the Ansible playbook to secure your Raspberry Pi**

```
ansible-playbook -i hosts playbook.yaml
```

---

### Built With

* [Ansible 2.3.1](https://github.com/ansible/ansible/releases/tag/v2.3.1.0-1)
* [Raspberry Pi 2 Model B](https://www.raspberrypi.org/products/raspberry-pi-2-model-b/)
* [Raspbian 2017-11-29-raspbian-stretch](https://www.raspberrypi.org/downloads/raspbian/)

---

## Authors

[Tom Gelbling](https://www.linkedin.com/in/tomgelbling/) - *Project initiator*

See also the list of [contributors](https://github.com/tomgelbling/Securing-your-Raspberry-Pi-with-Ansible/graphs/contributors) who participated in this project.

## License

This project is licensed under the GNU General Public License v3.0 - see the [LICENSE.md](LICENSE.md) file for details

## Acknowledgments

**Raspberry Pi Foundation** - *Initial work* - [Securing your Raspberry Pi](https://www.raspberrypi.org/documentation/configuration/security.md)
