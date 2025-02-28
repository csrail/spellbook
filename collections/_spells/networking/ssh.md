---
layout: spell
date: 27-02-2025
---

"SSH, Secure Shell, is a network protocol that provides secure remote access, encrypted data communications and strong authentication."\\
$~\Rightarrow$ SSH enables a user on their source machine to access a destination machine securely.\\
$~\Rightarrow$ Public $\cup$ Private SSH key pairs must be generated.\\
$~\Rightarrow$ Configuration of network files required to connect all endpoints.

<br>

On the **destination machine**, the intended machine you want remote access to:\\
$~-$ generate the public/private key pair,\\
$~-$ add the public key to the list of authorised keys\\
$~-$ confirm access to gateway is available\\
$~-$ confirm access to lab machine available through gateway

```shell
## Generate the public/private key pair
# upon running the below command
# the default file path for saving will be ~/.ssh/id_ed25519
# change this file path to be ~/.ssh/id_ed25519_identifier
# where 'identifier' is something recognisable for where this key belongs to,
# since key pairs will be generated for separate organisations you want secure shell access to
# e.g. github ssh key pairs for pull and push, university ssh key pairs for lab access
# ---
# set a password for this key pair to guard its authorisation,
# this provides an extra layer of security to the keys
ssh-keygen -t ed25519 -C <student university email address>

## Permissions may need to be adjusted for remote shell access to work
# change the permissions on the ssh directory
chmod 0700 ~/.ssh
# ---
# change permissions on the private key
chmod 0600 ~/.ssh/id_ed25519_identifier

## Add the public key to the authorized_keys file
# note the American spelling
cat id_ed25519_identifier.pub >> ~/.ssh/authorized_keys

## Confirm acess to gateway is available
ssh <gateway address>

## Confirm access to lab machine through gateway is available
# the gateway is also known as the bastion host or the jump host
# hence the -J flag
# ensure the lab machine address is different to the current machine being used,
# if on lab machine 1, then log onto any other lab machine other than 1
ssh <lab machine address> -J <gateway address>
```

<br>

A copy of the public and private key pair from the destination machine should be put on your source machine. An offline medium like USB is most secure, but personal cloud storage will do.

<br>

On the **source machine**, the personal machine you drive on:\\
$~-$ copy the key pair to the `.ssh` directory\\
$~-$ set up the network config file\\
$~-$ confirm remote shell access to destination machine\\
$~-$ automate password entry

```shell
## Copy the key pair to the .ssh directory
# Move the public key
mv id_ed25519_identifier.pub ~/.ssh/.
# Move the private key
mv id_ed25519_identifier ~/.ssh/.
```

<br>

```shell
## Set up the network config file
vi ~/.ssh/config

# Put the following in the configuration file.
# This preconfigures the ssh command so you don't need to remember all the overheads

Host *
ForwardAgent yes
Host <gateway-alias>
  # username must be specified otherwise personal device username is used
  User <username>
  HostName <gateway address>
  IdentityFile <file path of associated private key>
Host <destination-machine-alias>*
  User <username>
  # the %h symbol substitutes the Host alias above,
  # so if <destination-machine-alias> was lab-host-x-
  # then Host would be lab-host-x-*
  # where * is a wildcard regex
  # so HostName would then be lab-host-x<lab-host-address>
  HostName %h<lab-host-address>
  ProxyJump <gateway-alias>
```

<br>

```shell
## Confirm shell access
# no need to enter full lab machine address,
# and no need to include jump host address
# since network config file above takes care of that
# enter password to the key
ssh <lab-machine-alias>

# use ctrl+D to exit remote shell
```

<br>

```shell
## Automate password entry
# check if ssh-agent is running
# should return a process id
eval $(ssh-agent -s)

# special flag --aple-use-keychain required for MacOS
# enter password to the key
ssh-add --apple-use-keychain ~/.ssh/id_ed25519_identifier

# confirm that password entry is no longer required during ssh
ssh <lab-machine-alias>
```
