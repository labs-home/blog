+++
title = 'Hardware'
+++

![Server Rack](/images/Rack.jpeg)

## Inventory (Top-Bottom)
- [StarTech.com 4-Post 25U Open Frame Server Rack](https://www.startech.com/en-gb/server-management/4postrack25)
- [Excel Keystone Jack Mount 16 Port Patch Panel](https://www.kenable.co.uk/networking/network-cabinets/patch-panels/excel-keystone-jack-mount-16-port-patch-panel-metal-cable-management-bar-19-inch-012413)
- [Ubiquiti Unifi Pro Max 24 Port](https://eu.store.ui.com/eu/en/products/usw-pro-max-24)
- [Cable Matters Rackmount 1U 24 Port Keystone Patch Panel](https://www.cablematters.com/pc-386-162-rack-or-wall-mount-24-port-blank-patch-panel.aspx)
- [Custom 1U OPNSense Appliance](#custom-1u-opnsense-appliance)
- [StarTech.com 2U Server Rack Shelf](https://www.startech.com/en-gb/server-management/cabshelfv) | [3x Lenovo M720q Mini-PCs](#3x-lenovo-m720q-mini-pcs) | [HP 260 G2 Mini-PC](#hp-260-g2-mini-pc)
- [Custom Gaming PC](#gaming-pc)
- [Custom 4U NAS](#custom-4u-nas)
- [NUT-UPS Raspberry Pi 3 Model B](#nut-ups-raspberry-pi-3-model-b)
- [Eaton 3S 850VA](https://www.eaton.com/gb/en-gb/skuPage.3S850B.html)

## Custom 1U OPNSense Appliance
In February 2026, I retired a Dell Optiplex running a 7th Generation Intel CPU in favour of a more compact 1U custom build solution. This new system includes the following specs:
- [In-Win IW-RF100 1U Chassis](https://ipc.in-win.com/rackmount-chassis-iw-rf100)
- [Intel i3-9100T](https://www.intel.com/content/www/us/en/products/sku/134871/intel-core-i39100t-processor-6m-cache-up-to-3-70-ghz/specifications.html)
- [Asus Prime H310M-A](https://uk.store.asus.com/90mb0z10-m0eay0-feed.html)
- [Noctua L9i](https://www.noctua.at/en/products/nh-l9i) (Removed fan to run passive)
- [Intel I350-T4](https://www.intel.com/content/www/us/en/products/sku/184824/intel-ethernet-network-adapter-i350t4-for-ocp-3-0/specifications.html)
- [picoPSU-90 ATX PSU](https://www.mini-itx.com/~picoPSU-90)

**NOTE** Whilst these components are working well in my environment, some are _technically_ not compatible with a 1U chassis (notably motherboard and CPU cooler).

This appliance runs the [Proxmox VE](https://www.proxmox.com/en/products/proxmox-virtual-environment/overview) hypervisor, with a single VM running [OPNSense](https://opnsense.org/) operating as my router and firewall. I also run a Wireguard server for network access when away from home, as well as HAProxy to act as a reverse proxy on the edge of my network. Whilst many are against running OPNSense as a virtual machine due to potential complications, I have found it to run flawlessly - plus it allows me to backup the appliance daily using [Proxmox Backup Server](https://www.proxmox.com/en/products/proxmox-backup-server/overview).

## 3x Lenovo M720q Mini-PCs
Next in my server rack I have 3 Lenovo M720q mini PCs that I purchased from eBay for £70 each. When purchased, each node had an i3-8100T CPU and 8GB RAM. I have since upgraded the nodes to each include an [i5-9500T](https://www.intel.com/content/www/us/en/products/sku/191052/intel-core-i59500t-processor-9m-cache-up-to-3-70-ghz/specifications.html) CPU, 36GB RAM, Intel enterprise SATA SSD and a [2.5G network card](https://www.aliexpress.com/item/1005006967643496.html). Each of these nodes runs [Proxmox VE](https://www.proxmox.com/en/products/proxmox-virtual-environment/overview) so I can run VMs and LXC containers, plus backup selected VMs using [Proxmox Backup Server](https://www.proxmox.com/en/products/proxmox-backup-server/overview). The standard 1G network connection is used for management of Proxmox and resources, and the 2.5G network connection is used for VM network connectivity.

## HP 260 G2 Mini-PC
Alongside the Lenovo mini PCs, a single HP 260 G2 is present. Currently, this node runs [Proxmox VE](https://www.proxmox.com/en/products/proxmox-virtual-environment/overview) with no VMs or containers. However, I do have plans in the near future for this node. It will run a number of GitHub actions runners to create Docker images, apply Terraform changes and a few other small tasks. This machine consists of an [Intel i3-6100T](https://www.intel.com/content/www/us/en/products/sku/90734/intel-core-i36100t-processor-3m-cache-3-20-ghz/specifications.html), 8GB RAM and 250GB storage from a SATA SSD.

## Custom Gaming PC
My custom gaming PC is also stored in my server rack to save space by my desk. I built this in 2022 using what was considered mid-range components, and it is still performing well today in the few games I play. The specs are as follows:
- [Intel i5-12400F](https://www.intel.com/content/www/us/en/products/sku/134587/intel-core-i512400f-processor-18m-cache-up-to-4-40-ghz/specifications.html)
- [ASUS TUF Gaming B660-Plus D4](https://www.asus.com/uk/motherboards-components/motherboards/tuf-gaming/tuf-gaming-b660-plus-wifi-d4/)
- [NVIDIA GeForce RTX 3070 Founders Edition](https://www.nvidia.com/en-gb/geforce/graphics-cards/30-series/rtx-3070-3070ti/)
- [NZXT H510 Flow (White)](https://support.nzxt.com/hc/en-us/articles/37464879064347-H510-Series-Specs)
- [NZXT Kraken X63 280mm All-in-One Liquid CPU Cooler](https://nzxt.com/en-intl/products/kraken-280)

By a stroke of luck, I had this case long before I purchased my server rack but it was the perfect size to fit in a 19" rack! I used the [StarTech.com 1U 19 inch Server Rack Rails](https://www.startech.com/en-us/server-management/unirails1ub) which were just narrow enough to fit the case on and secure it in the rack.

## Custom 4U NAS
I also built this NAS prior to using it in a server rack, with the components installed in a [Fractal Design Node 804](https://www.fractal-design.com/products/cases/node/node-804/black/) case. Once I purchased the server rack, I migrated the internals into a Logic Case LC-4680-16B-WH 4U Rackmount Storage Chassis. Whilst expensive (I believe around £400!), this provides hotswap capabilities for when I need to add or remove drives without shutting down the system. Below is a list of the other components:
- [Intel i3-10105](https://www.intel.com/content/www/us/en/products/sku/201894/intel-core-i310105-processor-6m-cache-up-to-4-40-ghz/specifications.html)
- Stock Intel CPU Cooler
- [Corsair Vengeamce LPX 32GB (2x16GB) DDR4 3200MHz](https://www.corsair.com/uk/en/p/memory/cmk32gx4m2e3200c16/vengeance-lpx-32gb-2-x-16gb-ddr4-dram-3200mhz-c16-memory-kit-black-cmk32gx4m2e3200c16)
- [LSI MegaRAID 9211-8i (IT Mode)](https://www.bargainhardware.co.uk/lsi-sas9211-8i-fh-pcie-x4-raid-controller)

| Array        | Configuration | Drives              |
| ------------ | ------------- |-------------------- |
| Boot         | Stripe        | Intel SSDSC2BB160G4 |
| Mass Storage | RAIDZ1        | 3x [Hitachi HUH721212AL4200](https://www.bargainhardware.co.uk/hitachi-huh721212al4200-12tb-lff-3-5in-sas-3-12gbps-7-2k-256mb-hdd) |
| Speed        | Stripe        | [Samsung SSD 980 1TB](https://www.samsung.com/uk/memory-storage/nvme-ssd/980-1tb-nvme-pcie-gen-3-mz-v8v1t0bw) |
| Other        | Stripe        | WD WD40EFRX         |

This NAS runs [TrueNAS scale](https://www.truenas.com/truenas-community-edition/). Alongside the storage pools, a VM is also running for [Proxmox Backup Server](https://www.proxmox.com/en/products/proxmox-backup-server/overview). I did want this VM to run on the HP mini PC, however I required a good amount of storage so the NAS was the best choice for this.

## NUT-UPS Raspberry Pi 3 Model B
Next to the Eaton UPS I have a Raspberry Pi 3 Model B, which is running utilities relating to NUTUPS.

## Broadband
My current broadband provider is EE UK with there 900 full fibre, which offers ~900Mbps download and ~110Mbps upload. During off-peak times, I have seen 1.1Gbps download - above the advertised speeds.