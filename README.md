# Securing your Raspberry Pi with Ansible

Ansible playbook to secure your Raspberry Pi.
Source: https://www.raspberrypi.org/documentation/configuration/security.md

### Prerequisites

What things you need to install the software and how to install them

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

## Deployment

This chapter describes how to
* get a copy of the project
* edit the config files
* run the Ansible playbook to secure your Raspberry Pi

**How to get a copy of the project**

```
git clone https://github.com/tomgelbling/Securing-your-Raspberry-Pi-with-Ansible.git
cd Securing-your-Raspberry-Pi-with-Ansible/
```

**Mandatory - How to edit the config files**

Add your Raspberry Pi IP address to the pi host group
```
echo "192.168.2.110" >> hosts
```

Add your public key to the authorized_keys files
```
cat ~/.ssh/id_rsa.pub >> roles/security/files/authorized_keys
```




ansible-playbook -i hosts playbook.yaml

## Built With

* [Ansible 2.3.1](https://github.com/ansible/ansible/releases/tag/v2.3.1.0-1) - IT automation platform
* [Raspberry Pi 2 Model B](https://www.raspberrypi.org/products/raspberry-pi-2-model-b/) - Hardware
* [Raspbian 2017-11-29-raspbian-stretch](https://www.raspberrypi.org/downloads/raspbian/) - Operating system

## Authors

[Tom Gelbling](https://github.com/tomgelbling) - *Project initiator*

See also the list of [contributors](https://github.com/tomgelbling/Securing-your-Raspberry-Pi-with-Ansible/graphs/contributors) who participated in this project.

## License

This project is licensed under the GNU General Public License v3.0 - see the [LICENSE.md](LICENSE.md) file for details

## Acknowledgments

* **Raspberry Pi Foundation** - *Initial work* - [Securing your Raspberry Pi](https://www.raspberrypi.org/documentation/configuration/security.md)
