---
title: Automatic Shutting System
summary: An efficient addon to pre-existing freezers in supermarkets, to reduce the cost of the freezers by automatically closing the doors.
date: 2024-10-22

# Featured image
# Place an image named `featured.jpg/png` in this page's folder and customize its options here.
image:
  caption: 'Image credit: **Me**'

authors:
  - admin
  - Kevin Lee
  - Hao Wen


tags:
  - IoT 
  - Prototype
---


{{< toc mobile_only=true is_open=true >}}
[![Hackster.io Logo](https://www.hackster.io/assets/hackster_logo_squared.png)](https://www.hackster.io/515083/automatic-shutting-system-66b8ab)

[![LinkedIn Logo](https://upload.wikimedia.org/wikipedia/commons/c/ca/LinkedIn_logo_initials.png?20140125013055)](https://www.linkedin.com/posts/m5stack_projectspotlight-tof-pir-activity-7255070732387254273-CgfR/?utm_source=share&utm_medium=member_desktop)

## Story

Supermarket fridges consume enough electricity to power 800, 000 homes. A study by the Department of Environment, Food, and Rural Affairs found that the entire retail food sector uses around 3% of the UK's annual energy output. Refrigeration accounts for 50-60% of the electricity consumed in a supermarket. In food and grocery stores, refrigeration is the largest consumer of energy, operating non-stop and responsible for around half of the store’s total energy consumption.

This project aims to address the significant energy consumption of refrigerators and freezers in supermarkets by targeting the forgetfulness of shoppers who leave the doors open or take too long to close them, ultimately promoting environmental sustainability.

### Objectives

- To develop a solution to reduce the power consumption of refrigerators and freezers in retail, supermarkets.
- Able to be modular to fit onto existing refrigeration units without requiring extensive modifications, minimising installation time and cost.

### Research

- Supermarket refrigeration is a major contributor to overall energy usage, and reducing its consumption can significantly impact energy efficiency.
- Understanding why shoppers leave fridge and freezer doors open can help design effective solutions to address this behaviour.
- Implementing sensors to detect door status and temperature can provide real-time data to optimise energy usage.

### Project

- Door Detection System - Utilising a TOF sensor to detect if a refrigerator or freezer door is left open and initiating alerts accordingly.
- Human Presence detector - Using a PIR sensor to sense if anyone is at the refrigerator door.
- Automated Door Closure - Automatically closing doors if left open for an extended period to conserve energy.
- User Interface - Providing visual and auditory alerts to shoppers to prompt them to close doors promptly.
- Real-time Monitoring - Continuous monitoring of internal temperature ENV III and door status on the dashboard via Qbitro to ensure optimal conditions

### Video Demonstration 
{{< youtube NVHdf7NcfQY >}}

### Pictures
![featured.jpg](featured.jpg)<span style="display: block; text-align: center; font-size: small; transform: translateY(-50px);">Prototype</span>![transmitter.jpg](transmitter.jpg)<span style="display: block; text-align: center; font-size: small; transform: translateY(-50px);">M5Stack 1 (Transmitter)</span>![receiver.jpg](receiver.jpg)<span style="display: block; text-align: center; font-size: small; transform: translateY(-50px);">M5Stack 2 (Receiver)</span>![dashboard.jpg](dashboard.jpg)<span style="display: block; text-align: center; font-size: small; transform: translateY(-50px);">Dashboard - Qubitro</span>![blk-dia-trans.jpg](blk-dia-trans.jpg)<span style="display: block; text-align: center; font-size: small; transform: translateY(-50px);">Block Diagram for M5Stack 1 (Transmitter)</span>![Blk-Dia-rec.jpg](Blk-Dia-rec.jpg)<span style="display: block; text-align: center; font-size: small; transform: translateY(-50px);">Block Diagram for M5Stack 2 (Receiver)</span>![flowchart1.png](flowchart1.png)<span style="display: block; text-align: center; font-size: small; transform: translateY(-50px);">Flowchart for M5Stack 1 (Transmitter)</span>![flowchart2.png](flowchart2.png)<span style="display: block; text-align: center; font-size: small; transform: translateY(-50px);">Flowchart for M5Stack 2 (Receiver)</span>  









