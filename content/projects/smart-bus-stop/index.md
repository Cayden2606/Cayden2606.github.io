---
title: IoT Smart Bus Stop
summary: An all in one dashboard x prototype smth smth
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

Public transportation is the backbone of sustainable cities. However, commuters often face challenges such as unpredictable bus schedules, lack of shelter during extreme weather, and minimal access to real-time updates. The **Smart Bus Stop** addresses these issues by combining IoT, renewable energy, and user-centric design to revolutionize public transit infrastructure.

### Objectives

- To provide commuters with real-time bus tracking and arrival information.
- To integrate solar energy for powering displays and other utilities.
- To improve the user experience through interactive screens and weatherproof designs.

### Research

- Studies show that 75% of commuters prefer real-time transit updates to plan their journeys better.
- Solar-powered systems reduce carbon emissions and operational costs for public infrastructure.
- Incorporating accessibility features ensures inclusivity for all demographics, including differently-abled users.

### Project

<div style="text-align: center;">
  <img src="Media/busprototype.jpeg" alt="Wiring Diagram" style="max-width: 100%; height: auto;">
  <div style="font-size: small; margin-top: -10px;">Smart Bus Stop/div>
</div>
<div style="text-align: center;"></div>

- **Real-Time Tracking**  
  Displaying live bus locations and expected arrival times using GPS and cloud integration.
  
- **Solar Power Integration**  
  Solar panels to power the bus stop’s lighting, displays, and charging ports for sustainability.
  
- **Interactive Displays**  
  Touchscreen interfaces to provide information on routes, nearby services, and emergency contacts.
  
- **Passenger Comfort**  
  Weatherproof shelters with ergonomic seating and USB charging ports for convenience.
  
- **Accessibility Features**  
  Voice-enabled announcements and braille support for visually impaired users.

### Video Demonstration  
{{< youtube nPJaNwRcq4I >}}

### Behind The Scenes
#### Planning
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
<div style="text-align: center;"></div>

#### Lighting System

Uses a Modified LED Strip and a simple BJT amplifer circuit and uses reused light filter from an old Huawei Nova 3i Screen
Uses PWM to adjust light value.

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
<div style="text-align: center;"></div>

#### Wiring  

The wiring system integrates the LED strip, PWM controller, and BJT amplifier, ensuring seamless operation. Below is the diagram illustrating the connections and components involved.  
<div style="text-align: center; margin-top: 20px;">
  <img src="Media/wiring.jpg" alt="Wiring Diagram" style="max-width: 100%; height: auto; border: 1px solid #ccc; padding: 10px; box-shadow: 2px 2px 5px rgba(0, 0, 0, 0.1);">
</div>



