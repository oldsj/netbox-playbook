# netbox-playbook
An Ansible playbook for setting up a [netbox](https://github.com/digitalocean/netbox) host

## Getting Started
This config assumes you are running Ubuntu 16.04. It may work on other Debian variants but I have not tested that yet. 
This also assumes you are starting with a clean installation and will probably mess things up if not.
You should only need to modify variables in vars/vars.yml to configure your host. 
Use the configuration guide at https://github.com/digitalocean/netbox/blob/develop/docs/getting-started.md#configuration for configuration help.

For now this is configured to have ansible run from the host that will be running netbox

- Create a user "deploy" and give it nopasswd access to sudo:
```
adduser deploy
sudo visudo
deploy ALL=(ALL) NOPASSWD:ALL
```

- Configure your fresh Ubuntu installation for SSH, and install ansible:
  ```
  apt-get install ansible
  ```
- Run generate-secret.py and copy the generated secret to vars.yml netbox_secret_key variable, inside the quotes.
- Configure vars.yml with your own info making sure to put passwords inside quotes.
- Run deploy.sh:
  ```
  ./deploy.sh
  ```
