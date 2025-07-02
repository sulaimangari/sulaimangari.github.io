---
layout: post
title: Testing the Github Action Arm Machine #1 
categories: [arm, github, action, build, aarch64]
slug: github-arm-machine-1
---

Maybe I'm a little late to the game, but after a read this [news](https://github.blog/changelog/2025-01-16-linux-arm64-hosted-runners-now-available-for-free-in-public-repositories-public-preview/) of course it peaked my interest.  
![Git news](/assets/image/git-img.png)

After spend some time to learn github workflows, I finally make some workflows to directly access the VM. 

```console
OS: Ubuntu 24.04.2 LTS aarch64
Host: Virtual Machine (Hyper-V UEFI Release v4.1)
Kernel: Linux 6.8.0-1021-azure
Uptime: 5 mins
Packages: 1342 (dpkg)
Shell: bash 5.2.21
Display (Virtual-1): 1024x768
Theme: Yaru [GTK3]
Icons: Yaru [GTK3]
Cursor: Adwaita
Terminal: Runner.Worker
CPU: Neoverse-N2*4 (4)
Memory: 922.92 MiB / 15.58 GiB (6%)
Swap: 0 B / 3.00 GiB (0%)
Disk (/): 23.26 GiB / 71.61 GiB (32%) - ext4
Local IP (eth0): 10.1.0.174/16
Locale: C.UTF-8
```

From the basic spec we can learn that the CPU Cobalt 100 is based from Neoverse N2 architecture.
![Neoverse N2](https://www.arm.com/-/media/global/solutions/infrastructure/cloud-computing/n2-cloud-workload-900x900.jpg?rev=fabd13e5a8a54b729eae2ae33b225296&revision=fabd13e5-a8a5-4b72-9eae-2ae33b225296&h=900&w=900&la=en&hash=39866828C132BEEF1BC3D34BC9F06E90)

Neoverse N2 itself is fairly new architecture for balanced performance of aarch64 based enterprise server CPU. Unlike normal arm cpu using big little architecture, it fully utilized 1 core as it's thread. This resulted in more consistent performance and according to arm "improved security".   

There is so much to test on.  

In the next part maybe I will tried to explore the bios of the VM and maybe tried nested virtualization on the VM. 
If you want try the and spin simple VM of yourself you can visit this [repo](https://github.com/sulaimangari/cobalt-100-playground) and give it a spin.