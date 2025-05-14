+++
title = 'Setting Up a NAS'
date = 2024-12-07T20:00:42+11:00
+++

# NAS and Self-hosted server

Moving on from the Raspberry Pi, I've decided it would be a good idea to expand on my homelab by investing in a low-powered PC, giving me more headroom to actually host my services (properly at that). 

## The Operating System

While NAS-specific operating systems exist, for use cases like mine, I've decided that it would be more interesting to implement the functions provided by those operating systems myself, in Arch Linux. It isn't too difficult either. The main functions of a NAS can be achieved through services such as Samba and self-hosted cloud services like Nextcloud. 

## Why Docker?
    
I never actually understood why "homelabbers" used Docker instead of just bare-metal applications of the exact same services, with much more simple setups and configurations, until I decided to use a much larger amount of services, especially when you start messing around with networking. So I forced myself to use Docker for deployment on my NAS (running Arch obviously), and It's actually become extremely streamlined, to the point where I don't see myself using any other deployment method in future applications. 

## What services am I running?

Starting off with the mandatory dashboard to show off all the unnecessary data, I've opted for Homepage, mainly for the built-in API connections to popular applications and the extremely easy connection to other Docker containers. 

### Networking, Speedtest-tracker containers, and a VPN

Networking with Docker, I will admit, took far too long to get the hang of. But I'm happy to say that it worked out in the end. Currently, I have opted for my VPN to run in a container, which was an absolute lifesaver when it comes to seperating my traffic. qBittorrent for example, is also in a container, using the Gluetun VPN container to route traffic. This allows for the privacy benefits of a VPN, while keeping the regular network connections for my other services.

Speedtests can also be self-hosted, which is quite helpful for data collection, and determining if the device's connections are valid. Setting up the speedtest, unfortunately wasn't straightforward for me, with the documentation being extremely indirect. But after many hours of testing configurations, it finally works. In fact, I decided to spin up two, one for my regular WAN connection, and another for mmy VPN for a speedtest. I've got both running on a Cron schedule of 30 mins (*/30 * * * *)


## Storage, mounting, and a graphs

My storage solution for my NAS is very "all over the place", with 3 different hard-drives, and a boot SSD. For my hard drives, I have decided to not use any RAID configurations, mainly because I have different sized drives (Two 1TB drives, and a single 2TB drive, I don't have a need for backups (It isn't important media), and, more specifically, RAID0 wouldn't provide me a noticeable improvement of speeds since I am limited by my Gigabit network speeds. But, RAID0 would show an improvement in read and write speeds, with the outcome being the combined speeds of all the drives, however, lacking redundancy.

The drives are all mounted to my "/mnt" folder for simplicity, with their obvious names (EXTHDD for External drive, HDD0 for my first hard-drive), as their mount points. Nothing special, really. It's a lot of just manually conducting implementation for each function that a NAS serves, that would commonly be completed with NAS-specific operating systems, such as TrueNAS or Unraid. 
