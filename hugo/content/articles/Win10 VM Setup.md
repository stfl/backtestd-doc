+++
title = "Windows 10 (VM) Setup"
author = ["Stefan Lendl"]
draft = false
+++

<https://davejansen.com/recommended-settings-windows-10-2016-2018-2019-vm-proxmox/>


## Drivers {#drivers}

{{< figure src="/ox-hugo/pve-win10-hw.png" caption="Figure 1: win10hw" >}}

Win10 Disk needs to be SCSI

Virtio driver Disk from RedHat

[Spice Agent and Drivers](https://www.spice-space.org/download.html)


### <span class="org-todo todo TODO">TODO</span> Launch ballooning ... {#launch-ballooning-dot-dot-dot}


## MetaTrader 5 {#metatrader-5}

-   Setup MetaTester agents for all (64) cores
-   make sure the network is configured as a **private** network, otherwise the
    agents won't be discoverable. Or setup the firewall accordingly


## MEGA {#mega}

[Setup Syncs](Mega Setup.md)


## Samba {#samba}

Enable Network Share for Metrtrader5 Terminal dir.


## Other stuff {#other-stuff}

disable sleep otherwise the VM will go to sleep after 30min :P


## Benchmarking Win 10 VM disk performance {#benchmarking-win-10-vm-disk-performance}

<https://bsdio.com/fio/>

```sh
    fio.exe --time_based --name=benchmark --size=5000M --runtime=30 --ioengine=windowsaio --numjobs=8 --iodepth=8 --rw=randwrite --blocksize=4k --group_reporting --direct=1
```
