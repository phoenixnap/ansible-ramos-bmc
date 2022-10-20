<h1 align="center">
  <br>
  <a href="https://phoenixnap.com/bare-metal-cloud"><img src="https://user-images.githubusercontent.com/78744488/109779287-16da8600-7c06-11eb-81a1-97bf44983d33.png" alt="phoenixnap Bare Metal Cloud" width="300"></a>
  <br>
  Install Custom OS (Rocky Linux) On BMC
  <br>
</h1>

<p align="center">
Ansible playbooks for provisioning a Custom OS server (RAM OS) and installing a custom OS on the BMC server.  Choose whether to set up RAID 0 or 1, the root disk size, LVM, and the OS.
</p>

<p align="center">
  <a href="https://phoenixnap.com/bare-metal-cloud">Bare Metal Cloud</a> •
  <a href="https://galaxy.ansible.com/phoenixnap/bmc">Ansible Galaxy</a> •
  <a href="https://developers.phoenixnap.com/">Developers Portal</a> •
  <a href="http://phoenixnap.com/kb">Knowledge Base</a> •
  <a href="https://developers.phoenixnap.com/support">Support</a>
</p>

## Requirements

- [Bare Metal Cloud](https://bmc.phoenixnap.com) account
- Ansible 2.9+
- Python 2 (version 2.7) or Python 3 (versions 3.5 and higher)
  - Python **_requests_** package

## Creating a Bare Metal Cloud account

1. Go to the [Bare Metal Cloud signup page](https://support.phoenixnap.com/wap-jpost3/bmcSignup).
2. Follow the prompts to set up your account.
3. Use your credentials to [log in to Bare Metal Cloud portal](https://bmc.phoenixnap.com).

:arrow_forward: **Video tutorial:** [How to Create a Bare Metal Cloud Account in Minutes](https://www.youtube.com/watch?v=hPR60XWOSsQ)
<br>

:arrow_forward: **Video tutorial:** [How to Deploy a Bare Metal Server in a Minute](https://www.youtube.com/watch?v=BzBBwLxR80o)

## Installing Ansible

Follow these helpful tutorials to learn how to install Ansible on Ubuntu and Windows machines.

- [How to Install and Configure Ansible on Ubuntu 20.04](https://phoenixnap.com/kb/install-ansible-ubuntu-20-04)
- [How to Install and Configure Ansible on Windows](https://phoenixnap.com/kb/install-ansible-on-windows)

## Installing the Bare Metal Cloud Ansible module

This Ansible collection contains the **_server_** module which requires the Python **_requests_** HTTP library to work properly. If you don't have it installed on your machine already, run this command to install it:

    pip install requests

Now install the Ansible collection by running:

    ansible-galaxy collection install phoenixnap.bmc

You can view the **_server_** module documentation with this command:

    ansible-doc phoenixnap.bmc.server

## Authentication

You need to create a configuration file called `config.yaml` and save it in the user home directory. This file is used to authenticate access to your Bare Metal Cloud resources.

In your home directory, create a folder `.pnap` and a `config.yaml` file inside it.

This file needs to contain only two lines of code:

    clientId: <enter your client id>
    clientSecret: <enter your client secret>

To get the values for the clientId and clientSecret, follow these steps:

1. [Log in to the Bare Metal Cloud portal](https://bmc.phoenixnap.com).
2. On the left side menu, click on API Credentials.
3. Click the Create Credentials button.
4. Fill in the Name and Description fields, select the permissions scope and click Create.
5. In the table, click on Actions and select View Credentials from the dropdown.
6. Copy the values from the Client ID and Client Secret fields into your `config.yaml` file.

## Ansible Playbooks for provisioning and installing a Custom OS (Rocky Linux) using RAM OS

The Ansible Playbook allows you to provision and install a custom OS on a Bare Metal Cloud server.
* **_inventory.yaml_** contains all the information about the BMC server. Custom values in this file allows custom OS setup.
* **_provision.yaml_** deploys the BMC server using the RAM OS feature. The playbook uses the information from **_inventory.yaml_** to deploy and set up custom OS on the server.

This example shows you how to deploy and install:
* An **s2.c1.medium** server in **Phoenix** at an **hourly rate**.
* **Rocky OS** with a **50G root volume**, **LVM**, and **RAID level 0**.

To run the example, use:

    
    ANSIBLE_HOST_KEY_CHECKING=False ansible-playbook provision.yaml -i inventory.yaml
    

For the full guide, check out this helpful tutorial: [How to Install Custom OS (Rocky Linux) On BMC](https://phoenixnap.com/kb/bmc-custom-os)

## Bare Metal Cloud community

Become part of the Bare Metal Cloud community to get updates on new features, help us improve the platform, and engage with developers and other users.

- Follow [@phoenixNAP on Twitter](https://twitter.com/phoenixnap)
- Join the [official Slack channel](https://phoenixnap.slack.com)
- Sign up for our [Developers Monthly newsletter](https://phoenixnap.com/developers-monthly-newsletter)

### Resources

- [Product page](https://phoenixnap.com/bare-metal-cloud)
- [Instance pricing](https://phoenixnap.com/bare-metal-cloud/instances)
- [YouTube tutorials](https://www.youtube.com/watch?v=8TLsqgLDMN4&list=PLWcrQnFWd54WwkHM0oPpR1BrAhxlsy1Rc&ab_channel=PhoenixNAPGlobalITServices)
- [Developers Portal](https://developers.phoenixnap.com)
- [Knowledge Base](https://phoenixnap.com/kb)
- [Blog](https:/phoenixnap.com/blog)

### Documentation

- [Ansible Galaxy - phoenixNAP](https://galaxy.ansible.com/phoenixnap)
- [API documentation](https://developers.phoenixnap.com/docs/bmc/1/overview)

### Contact phoenixNAP

Get in touch with us if you have questions or need help with Bare Metal Cloud.

<p align="left">
  <a href="https://twitter.com/phoenixNAP">Twitter</a> •
  <a href="https://www.facebook.com/phoenixnap">Facebook</a> •
  <a href="https://www.linkedin.com/company/phoenix-nap">LinkedIn</a> •
  <a href="https://www.instagram.com/phoenixnap">Instagram</a> •
  <a href="https://www.youtube.com/user/PhoenixNAPdatacenter">YouTube</a> •
  <a href="https://developers.phoenixnap.com/support">Email</a> 
</p>

<p align="center">
  <br>
  <a href="https://phoenixnap.com/bare-metal-cloud"><img src="https://user-images.githubusercontent.com/81640346/115243282-0c773b80-a123-11eb-9de7-59e3934a5712.jpg" alt="phoenixnap Bare Metal Cloud"></a>
</p>
