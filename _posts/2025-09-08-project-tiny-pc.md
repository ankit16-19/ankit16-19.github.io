---
layout: post
title: Project Tiny PC
date: 2025-09-08 21:56 +0530
categories: projects homelab
tags: projects diy tinkering tinypc 10gbps
---

Tiny PC (aka: 1 Liter PC), are best machine for homelab scneario speciall the ones with PCIE expansion slot, some of these units can hold as large as 64GB max Ram, which is great for homelab scneario as unlike CPU, memory is not a shared resource. K8s cluster are super ram hungry.

Hp thinclient t740 comes with a ready to use PCIE slot, but Lenovo tiny pc i.e 720q/920q/p330 comes with propriety expansion slot and needs expansion [rise card](https://www.amazon.in/Replacement-Expansion-ThinkCentre-ThinkStation-01AJ940/dp/B0CCS1738B) to install PCIE.

I will be using dual 10Gbpx sfp+ card on all core machines, wiht PCIE3.0 x8, the max theoriticla speed can acieve is 64Gbps dual band. Which mean we can expand upto dual 25Gbps, total to 50Gbps.

![image.png](/assets/img/image-2.png)
_PCIE_SPEEDs_

## Arsenal

| Code Name | Mini PC             | CPU                       | Ram  | Connectivity         | PCIE Expanion |
| --------- | ------------------- | ------------------------- | ---- | -------------------- | ------------- |
| Mordex    | Lenovo 920q         | 9100T                     | 16GB | Intel x710 dual SFP+ | PCIE3.0 x8    |
| Jiro      | Lenovo p330         | 9300                      | 48GB | Intel x710 dual SFP+ | PCIE3.0 x8    |
| Oxygen    | HP thin client t640 | AMD Ryzen Embedded R1305G |      | Intel x710 dual SFP+ | PCIE3.0 x8    |
| Hydrogen  | Hp thin client t740 | AMD Ryzen Embedded V1756B |      | Onboard Gigabit lan  | N/A           |

## Remote Management using AMT Vpro

Altough according to intel, vpro CPU and chipset combination is required to support Vpro completely.

| Model      | Chipset | Generation                    | Vpro SupporAmt/t |
| ---------- | ------- | ----------------------------- | ---------------- |
| M720q Tiny | B360    | 8th-Gen (Coffee Lake)         | No               |
| M920q Tiny | Q370    | 9th-Gen (Coffee Lake Refresh) | Yes              |
| P330 Tiny  | Q370    | 9th-Gen (Coffee Lake Refresh) | Yes              |

## Rack Mounting Tiny pc

I want that tiny PC fits/sits nicely in my Server Rack, You can see their current state.

TODO: Add tiny pc current state

I will be printing a 19 inch 1U rack Mount using this [model](https://www.thingiverse.com/thing:4769452) that i found on thingsverse.

### What I am using for printing?

- 3D printer: [Creality Ender 3 S1 pro](https://www.creality.com/products/creality-ender-3-s1-pro-fdm-3d-printer)
- Material: [PTEG](https://www.amazon.in/dp/B0FFB98MZZ?ref=ppx_yo2ov_dt_b_fed_asin_title)
- Screw and nuts from [OnlyScrews.in](https://onlyscrews.in/products/m3-allen-button-head-ss304-assorted-box?_pos=1&_sid=d06059bdf&_ss=r)
- Slicing Software: [Ultimate Cura](https://ultimaker.com/software/ultimaker-cura/)

TODO: Add 3d Printer Photo

### Printer settings

| Settings          | Value               |
| ----------------- | ------------------- |
| Infill            | 20%                 |
| Temp              | 220                 |
| Bed Temp          | 90                  |
| Support           | Yes                 |
| Support Type      | Tree                |
| Support Placement | Touching Buildplate |

## Improving Print Quality & Speed

Next: Project Shaka Laka Boom Boom