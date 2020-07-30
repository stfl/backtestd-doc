# Anaconda LXC Setup

The Anaconda Container needs to be priviliged to enable CIFS mount from the Win10 vm.

## user account

```sh
adduser condor
usermod -aG sudo condor
```

## install anaconda 

login as condor

[Installieren der Anaconda Python-Distribution unter Ubuntu 20.04 | DigitalOcean](https://www.digitalocean.com/community/tutorials/how-to-install-the-anaconda-python-distribution-on-ubuntu-20-04-de)

```sh
curl https://repo.anaconda.com/archive/Anaconda3-2020.02-Linux-x86_64.sh --output anaconda.sh
sha256sum anaconda.sh

# 2b9f088b2022edb474915d9f69a803d6449d5fdb4c303041f60ac4aefcc208bb  anaconda.sh

bash anaconda.sh
```

```sh
conda install -c pyviz holoviews hvplot panel
conda install -c plotly plotly
```

## deploy notebook

```sh
sudo apt install git
```

## setup smb cifs mount

```sh
mkdir /mnt/reports
chown condor:condor /mnt/reports
```

test with temp mount

```sh
mount -vv -t cifs -o username=Stefan,password=stefan,uid=1000,gid=1000,dir_mode=0755,file
_mode=0644 //192.168.12.23/users /mnt/reports
```

automount with fstab.
assing the condor user to the directory and allow write permissions...

```fstab
//192.168.12.23/users/Stefan/AppData/Roaming/MetaQuotes/Terminal/D0E8209F77C8CF37AD8BF550E51FF075/reports /mnt/reports  cifs    defaults,_netdev,nofail,username=Stefan,password=stefan,uid=1000,gid=1000,dir_mode=0755,file_mode=0644          0       0
```
