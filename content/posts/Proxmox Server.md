+++
title = 'Proxmox Server'
date = 2025-08-05T11:46:54+10:00
+++
# Proxmox Is Amazing

The best way to describe Proxmox, would be to define the operating system as the "end-game" for operating systems. It's every operating system ever made, but better. And it actually can be every operating system ever made. That's what is so amazing about it. 

## Why choose Proxmox

Proxmox takes a different approach to being an operating system. It actually acts as a host to virtual containers (or LXCs) and gives the user full control over what they want to run on their system. The whole operating system is centered around the Web UI, giving you the ability to configure your system (or systems in this case) from any computer that is on the same network.

There are obvious alternatives to Proxmox, like Docker and using containers on a regular OS, or even QEMU Virtual machines. But both of those options are  great at their respective container approach, while not providing any option for the other. Docker, for example, doesn't have the same level of separation compared to a VM, while a VM isn't exactly the most lightweight. And picking between these two (or using both) is leaving a lot of efficiency on the table. So Proxmox just combines both.

## LXC Or VM?

In Proxmox you can either use an LXC (Lightweight Unix Container) or a CT (Container / VM). Both are interchangeable for most tasks, but each is better at doing specific application hosting, compared to the other. 

**LXCs** are best used for single applications that can be run on limited hardware, and require little separation. For my home server, I have used LXCs for my media stack, with **Community VE helper scripts** to build them in a single command. These containers easily run on some very limited resources, I'm talking a quarter of a gigabyte of RAM and less than a gigabyte of disk space, allowing them to stack up.

**Virtual Machines** are for the bigger tasks. Think Virtual Windows Machines, or Network Attached Storage operating systems like Truenas. These applications need to be treated like individual devices, and VMs are pretty much as close as you'll get without building a whole different machine. Comparatively though, they will use a lot more resources than an LXC because they need to create a whole new system. 

## Proxmox Portion of my Home Network
