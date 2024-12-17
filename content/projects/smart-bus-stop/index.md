---
title: IoT Smart Bus Stop
summary: An innovative dashboard and prototype aimed at redefining bus stop functionality through IoT and sustainability.
date: 2024-08-07

# Featured image
# Place an image named `featured.jpg/png` in this page's folder and customize its options here.
image:
  caption: 'Image credit: **Me**'

authors:
  - admin
  - Rachel Lee
  - Xing Lu

tags:
  - IoT 
  - UI Design
  - Prototype
  - Sustainability
  - Smart City
---


{{< toc mobile_only=true is_open=true >}}

<a href="https://github.com/Cayden2606/Smart-Bus-Stop" style="display: flex; align-items: center;" target="_blank">
  <img src="https://github.githubassets.com/images/modules/logos_page/GitHub-Mark.png" alt="GitHub Logo" style="width: 30px; margin-right: 10px;">
  GitHub Repository for Smart Bus Stop
</a>

## Story

Public transportation is vital to sustainable cities but faces challenges like unreliable schedules, weather exposure, and limited real-time updates. The **Smart Bus Stop** combines IoT, renewable energy, and user-focused design to overcome these issues, modernizing transit infrastructure.

### Objectives

- **Real-Time Information**: Equip commuters with live bus tracking and arrival updates.  
- **Sustainability**: Use solar energy for powering lights, displays, and utilities.  
- **Enhanced User Experience**: Include interactive, weatherproof screens and ergonomic seating. 

### Research Insights

- **Real-Time Updates**: 75% of commuters prefer live transit data for better journey planning.  
- **Eco-Friendly Design**: Solar-powered systems reduce carbon footprints and costs.  
- **Accessibility**: Voice support and braille features ensure inclusivity for all users.

### Project Overview

<div style="text-align: center;">
  <img src="Media/busprototype.jpeg" alt="Wiring Diagram" style="max-width: 100%; height: auto;">
  <div style="font-size: small; margin-top: -10px;">Smart Bus Stop Prototype</div>
</div>

### Key Features:

1. **Real-Time Tracking**: Displays bus locations and arrival times using GPS and cloud integration.  
2. **Solar Power**: Provides sustainable energy for lighting, displays, and charging ports.  
3. **Interactive Displays**: Offers route information, nearby services, and emergency contacts.  
4. **Passenger Comfort**: Includes weatherproof shelters, ergonomic seating, and USB charging.  
5. **Accessibility**: Voice-enabled announcements and braille support for differently-abled users.  

### Video Demonstration  
{{< youtube nPJaNwRcq4I >}}

### Planning Stages
<div style="display: flex; flex-wrap: wrap; justify-content: center; gap: 20px;">
  <div style="text-align: center;">
    <img src="Media/tinkercad.png" alt="Tinkercad Design" style="max-width: 100%; height: auto;">
    <div style="font-size: small; margin-top: -10px;">Tinkercad Design</div>
  </div>
  <div style="text-align: center;">
    <video autoplay loop muted style="max-width: 100%; height: auto;">
      <source src="Media/busmodel.mp4" type="video/mp4">
      Your browser does not support the video tag.
    </video>
    <div style="font-size: small; margin-top: -10px;">Design Overview</div>
  </div>
  <div style="text-align: center;">
    <video autoplay loop muted style="max-width: 100%; height: auto;">
      <source src="Media/BBBWs.mp4" type="video/mp4">
      Your browser does not support the video tag.
    </video>
    <div style="font-size: small; margin-top: -10px;">BeagleBone Black Wireless with clicks</div>
  </div>
</div>


### Lighting System

- **Modified LED Strip**: Uses recycled light filters from a Huawei Nova 3i screen.  
- **PWM Control**: Adjusts brightness dynamically via a BJT amplifier circuit.  

<div style="display: flex; flex-wrap: wrap; justify-content: center; gap: 20px; margin-top: 20px;">
  <div style="text-align: center;">
    <img src="Media/Lighting.jpeg" alt="Modified LED Strip" style="max-width: 100%; height: auto;">
    <div style="font-size: small; margin-top: -10px;">Modified LED Strip</div>
  </div>
  <div style="text-align: center;">
    <img src="Media/Circuit.jpg" alt="BJT Amplifier Circuit" style="max-width: 100%; height: auto;">
    <div style="font-size: small; margin-top: -10px;">BJT Amplifier Circuit</div>
  </div>
  <div style="text-align: center;">
    <video autoplay loop muted style="max-width: 100%; height: auto;">
      <source src="Media/PWM.mp4" type="video/mp4">
      Your browser does not support the video tag.
    </video>
    <div style="font-size: small; margin-top: -10px;">PWM Demostration</div>
  </div>
    <div style="text-align: center;">
    <video autoplay loop muted style="max-width: 100%; height: auto;">
      <source src="Media/PWM2.mp4" type="video/mp4">
      Your browser does not support the video tag.
    </video>
    <div style="font-size: small; margin-top: -10px;">PWM Demostration</div>
  </div>
  
### Wiring and System Integration

The wiring system connects the LED strip, PWM controller, and BJT amplifier for seamless operation.  

<div style="text-align: center;">
  <img src="Media/wiring.jpg" alt="Wiring Diagram" style="max-width: 100%; height: auto; border: 1px solid #ccc; padding: 10px; box-shadow: 2px 2px 5px rgba(0, 0, 0, 0.1);">
</div>



