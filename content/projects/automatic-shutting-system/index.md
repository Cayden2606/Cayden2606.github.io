---
title: Automatic Shutting System
summary: An efficient addon to pre-existing freezers in supermarkets, to reduce the cost of the freezers by automatically closing the doors.
date: 2023-10-27

# Featured image
# Place an image named `featured.jpg/png` in this page's folder and customize its options here.
image:
  caption: 'Image credit: **Me**'

authors:
  - admin
  - Ted

tags:
  - IoT 
  - Prototype
---

Welcome 👋

{{< toc mobile_only=true is_open=true >}}

## Story

Supermarket fridges consume enough electricity to power 800, 000 homes. A study by the Department of Environment, Food, and Rural Affairs found that the entire retail food sector uses around 3% of the UK's annual energy output. Refrigeration accounts for 30-60% of the electricity consumed in a supermarket. In food and grocery stores, refrigeration is the largest consumer of energy, operating non-stop and responsible for around half of the store’s total energy consumption.

This project aims to address the significant energy consumption of refrigerators and freezers in supermarkets by targeting the forgetfulness of shoppers who leave the doors open or take too long to close them, ultimately promoting environmental sustainability.

### Objectives

- To develop a solution to reduce the power consumption of refrigerators and freezers in retail, supermarkets.
- Able to be modular to fit onto existing refrigeration units without requiring extensive modifications, minimising installation time and cost.

### Research:

- Supermarket refrigeration is a major contributor to overall energy usage, and reducing its consumption can significantly impact energy efficiency.
- Understanding why shoppers leave fridge and freezer doors open can help design effective solutions to address this behaviour.
- Implementing sensors to detect door status and temperature can provide real-time data to optimise energy usage.

### Project:

- Door Detection System - Utilising a TOF sensor to detect if a refrigerator or freezer door is left open and initiating alerts accordingly.
- Human Presence detector - Using a PIR sensor to sense if anyone is at the refrigerator door.
- Automated Door Closure - Automatically closing doors if left open for an extended period to conserve energy.
- User Interface - Providing visual and auditory alerts to shoppers to prompt them to close doors promptly.
- Real-time Monitoring - Continuous monitoring of internal temperature ENV III and door status on the dashboard via Qbitro to ensure optimal conditions

{{< youtube NVHdf7NcfQY >}}

![test](featured.jpg)


Code for M5Stack 1
This code manages the main logic for the automatic shutting system. And communicates with both the 2nd M5Stack and the dashboard.

```python
from m5stack import *
from m5ui import *
from uiflow import *
import espnow
import wifiCfg
import time
from m5mqtt import M5mqtt
import json

import unit


setScreenColor(0x222222)
tof_0 = unit.get(unit.TOF, unit.PAHUB1)
pir_0 = unit.get(unit.PIR, unit.PORTB)
pahub0 = unit.get(unit.PAHUB, unit.PORTA, 0x70)
env3_1 = unit.get(unit.ENV3, unit.PAHUB0)


modes = None
temp = None
state = None
current_temp = None
temp_state = None
distance = None
last_msg = None
temp_variable = None
Warning2 = None
critical_temp = None
Human = None
j = None
beep_return = None
i = None

wifiCfg.wlan_ap.active(True)
wifiCfg.wlan_sta.active(True)
espnow.init()

label0 = M5TextBox(130, 50, "-", lcd.FONT_Default, 0xFFFFFF, rotate=0)
label1 = M5TextBox(130, 80, "-", lcd.FONT_Default, 0xFFFFFF, rotate=0)
DataTransmit = M5Title(title="DataTransmit", x=6, fgcolor=0xFFFFFF, bgcolor=0x0000FF)
label2 = M5TextBox(14, 55, "Detection Range:", lcd.FONT_DefaultSmall, 0xFFFFFF, rotate=0)
label3 = M5TextBox(14, 80, "Door distance:", lcd.FONT_Default, 0xFFFFFF, rotate=0)
label4 = M5TextBox(169, 197, "Last State: ", lcd.FONT_Default, 0xFFFFFF, rotate=0)
label5 = M5TextBox(25, 214, "Timer:", lcd.FONT_Default, 0xFFFFFF, rotate=0)
label10 = M5TextBox(176, 80, "0", lcd.FONT_DejaVu24, 0xFFFFFF, rotate=0)
label13 = M5TextBox(176, 41, "Detection Temp:", lcd.FONT_DefaultSmall, 0xFFFFFF, rotate=0)
label6 = M5TextBox(169, 165, "-", lcd.FONT_DejaVu24, 0xFFFFFF, rotate=0)
label14 = M5TextBox(272, 41, "0", lcd.FONT_DefaultSmall, 0xFFFFFF, rotate=0)
label7 = M5TextBox(76, 205, "0", lcd.FONT_DejaVu24, 0xFFFFFF, rotate=0)
label15 = M5TextBox(290, 41, "°C", lcd.FONT_DefaultSmall, 0xFFFFFF, rotate=0)
label8 = M5TextBox(169, 217, "-", lcd.FONT_DefaultSmall, 0xFFFFFF, rotate=0)
rectangle0 = M5Rect(25, 136, 60, 60, 0xFFFFFF, 0xFFFFFF)
label9 = M5TextBox(169, 144, "Human Presence:", lcd.FONT_Default, 0xFFFFFF, rotate=0)
label11 = M5TextBox(210, 83, "°C", lcd.FONT_UNICODE, 0xFFFFFF, rotate=0)
image0 = M5Img(253, 60, "res/fire-small.png", False)
label12 = M5TextBox(176, 60, "Temp:", lcd.FONT_Default, 0xFFFFFF, rotate=0)
line0 = M5Line(M5Line.PLINE, 10, 120, 310, 120, 0xFFFFFF)
line1 = M5Line(M5Line.PLINE, 160, 30, 160, 230, 0xFFFFFF)
Add = M5TextBox(54, 225, "Add", lcd.FONT_Default, 0xFFFFFF, rotate=0)
Minus = M5TextBox(130, 225, "Minus", lcd.FONT_Default, 0xFFFFFF, rotate=0)
Modes = M5TextBox(220, 225, "Modes", lcd.FONT_Default, 0xFFFFFF, rotate=0)

from numbers import Number
import math


# Describe this function...
def MQTT():
  global modes, temp, state, current_temp, temp_state, distance, last_msg, temp_variable, Warning2, critical_temp, Human, j, beep_return, i
  if (tof_0.distance) < distance:
    state = 'Opened'
  else:
    state = 'Closed'
  current_temp = env3_1.temperature
  m5mqtt.publish(str('f8e49263-8704-43e4-a1b5-9d366e81806d'), str((json.dumps(({'human':(pir_0.state),'distance':(tof_0.distance),'temperature':current_temp,'door-state':state,'warning':Warning2,'temp-state':temp_state})))), )
  wait(1)

# Describe this function...
def temp_warnings():
  global modes, temp, state, current_temp, temp_state, distance, last_msg, temp_variable, Warning2, critical_temp, Human, j, beep_return, i
  if (env3_1.temperature) > temp + 5:
    temp_state = 'Critical'
    label10.setColor(0xff0000)
    label11.setColor(0xff0000)
    espnow.send(id=1, data=str('temp-warn'))
    wait(1)
    last_msg = 'temp-warn'
    image0.show()
    temp_variable = False
    while (env3_1.temperature) > temp + 5:
      espnow.send(id=1, data=str('temp-warn'))
      wait(2)


def multiBtnCb_CB():
  global modes, temp, state, current_temp, temp_state, distance, last_msg, temp_variable, Warning2, critical_temp, Human, j, beep_return, i
  espnow.send(id=1, data=str('test'))
  DataTransmit.setBgColor(0xff0000)
  wait_ms(100)
  DataTransmit.setBgColor(0x3333ff)
  DataTransmit.show()
  espnow.send(id=1, data=str('sound fazbear'))
  label8.setText('Test')
  pass
btn.multiBtnCb(btnC,btnB,multiBtnCb_CB)

def multiBtnCb_AB():
  global modes, temp, state, current_temp, temp_state, distance, last_msg, temp_variable, Warning2, critical_temp, Human, j, beep_return, i
  if modes:
    label2.setColor(0x33cc00)
    label13.setColor(0xffffff)
    distance = 60
    label0.setColor(0xff0000)
    label0.setText(str(distance))
    wait_ms(30)
    label0.setColor(0xffffff)
  else:
    label13.setColor(0x33cc00)
    label2.setColor(0xffffff)
    temp = 32
    label14.setColor(0xff0000)
    label14.setText(str(temp))
    wait_ms(30)
    label14.setColor(0xffffff)
  pass
btn.multiBtnCb(btnA,btnB,multiBtnCb_AB)

def multiBtnCb_AC():
  global modes, temp, state, current_temp, temp_state, distance, last_msg, temp_variable, Warning2, critical_temp, Human, j, beep_return, i
  label0.hide()
  label1.hide()
  label2.hide()
  label3.hide()
  label4.hide()
  label5.hide()
  label6.hide()
  label7.hide()
  label8.hide()
  label9.hide()
  label10.hide()
  label11.hide()
  label12.hide()
  label13.hide()
  label14.hide()
  label15.hide()
  rectangle0.hide()
  line0.hide()
  line1.hide()
  Add.show()
  Minus.show()
  Modes.show()
  wait(1)
  label0.show()
  label1.show()
  label2.show()
  label3.show()
  label4.show()
  label5.show()
  label6.show()
  label7.show()
  label8.show()
  label9.show()
  label10.show()
  label11.show()
  label12.show()
  label13.show()
  label14.show()
  label15.show()
  rectangle0.show()
  line0.show()
  line1.show()
  Add.hide()
  Minus.hide()
  Modes.hide()
  pass
btn.multiBtnCb(btnA,btnC,multiBtnCb_AC)

def buttonA_wasPressed():
  global modes, temp, state, current_temp, temp_state, distance, last_msg, temp_variable, Warning2, critical_temp, Human, j, beep_return, i
  if modes:
    label2.setColor(0x33cc00)
    label13.setColor(0xffffff)
    distance = (distance if isinstance(distance, Number) else 0) + -1
    if distance < 0:
      distance = 0
    label0.setColor(0xff0000)
    label0.setText(str(distance))
    wait_ms(30)
    label0.setColor(0xffffff)
  else:
    temp = (temp if isinstance(temp, Number) else 0) + -1
    label13.setColor(0x33cc00)
    label2.setColor(0xffffff)
    label14.setColor(0xff0000)
    label15.setColor(0xff0000)
    label14.setText(str(temp))
    wait_ms(30)
    label14.setColor(0xffffff)
    label15.setColor(0xffffff)
  pass
btnA.wasPressed(buttonA_wasPressed)

def buttonB_wasPressed():
  global modes, temp, state, current_temp, temp_state, distance, last_msg, temp_variable, Warning2, critical_temp, Human, j, beep_return, i
  if modes:
    label2.setColor(0x33cc00)
    label13.setColor(0xffffff)
    distance = (distance if isinstance(distance, Number) else 0) + 1
    label0.setColor(0xff0000)
    label0.setText(str(distance))
    wait_ms(30)
    label0.setColor(0xffffff)
  else:
    temp = (temp if isinstance(temp, Number) else 0) + 1
    label13.setColor(0x33cc00)
    label2.setColor(0xffffff)
    label14.setColor(0xff0000)
    label15.setColor(0xff0000)
    label14.setText(str(temp))
    wait_ms(30)
    label14.setColor(0xffffff)
    label15.setColor(0xffffff)
  pass
btnB.wasPressed(buttonB_wasPressed)

def buttonC_wasPressed():
  global modes, temp, state, current_temp, temp_state, distance, last_msg, temp_variable, Warning2, critical_temp, Human, j, beep_return, i
  if modes:
    modes = False
    label2.setColor(0xffffff)
    label13.setColor(0x33cc00)
  else:
    modes = True
    label13.setColor(0xffffff)
    label2.setColor(0x33cc00)
  pass
btnC.wasPressed(buttonC_wasPressed)


wifiCfg.doConnect('cayden', '12345678')
if wifiCfg.wlan_sta.isconnected():
  espnow.add_peer('78:21:84:93:ac:4d', id=1)
  m5mqtt = M5mqtt('f8e49263-8704-43e4-a1b5-9d366e81806d', 'broker.qubitro.com', 1883, 'f8e49263-8704-43e4-a1b5-9d366e81806d', 'Qq67mrTj9AZOi5CfPcEE246GgHeDLPm-6lbupCX6', 300)
  m5mqtt.start()
  modes = True
  distance = 60
  temp = 26
  Add.hide()
  Minus.hide()
  Modes.hide()
  while True:
    critical_temp = temp + 5
    label14.setText(str(temp))
    if modes:
      label2.setColor(0x33cc00)
      label13.setColor(0xffffff)
    else:
      label13.setColor(0x33cc00)
      label2.setColor(0xffffff)
    current_temp = env3_1.temperature
    label10.setText(str(round(current_temp)))
    espnow.add_peer('78:21:84:93:ac:4d', id=1)
    rectangle0.setBgColor(0x000000)
    Warning2 = 0
    label0.setText(str(distance))
    label6.setText(str(pir_0.state))
    label1.setText(str(tof_0.distance))
    Human = pir_0.state
    j = 0
    MQTT()
    wait(1)
    if current_temp > critical_temp:
      temp_warnings()
    elif current_temp > temp and current_temp < critical_temp:
      temp_state = 'Not Optimal'
      label10.setColor(0xff6600)
      label11.setColor(0xff6600)
      wait(1)
      last_msg = 'temp-warn'
      image0.show()
      temp_variable = True
    else:
      temp_state = 'Optimal'
      image0.hide()
      label10.setColor(0xffffff)
      label11.setColor(0xffffff)
      temp_variable = True
    wait(1)
    if temp_variable:
      if (tof_0.distance) < distance and Human == 0:
        wait(1)
        espnow.send(id=1, data=str('close door'))
        last_msg = 'close door'
        label8.setText(str(last_msg))
        wait(2)
      elif (tof_0.distance) < distance and Human == 1:
        espnow.send(id=1, data=str('open door'))
        label8.setText(str(last_msg))
        last_msg = 'open door'
        beep_return = True
        wait(1)
        for count in range(3):
          MQTT()
          wait(1)
          espnow.send(id=1, data=str('open door'))
          label8.setText(str(last_msg))
          last_msg = 'open door'
          j = (j if isinstance(j, Number) else 0) + 1
          for i in range(1, 11):
            label1.setText(str(tof_0.distance))
            label6.setText(str(pir_0.state))
            label7.setText(str(i))
            wait(1)
          Human = pir_0.state
          if Human == 0:
            beep_return = False
            espnow.send(id=1, data=str('close door'))
            last_msg = 'close door'
            label8.setText(str(last_msg))
            wait(2)
            break
          elif (tof_0.distance) < distance:
            label1.setText(str(tof_0.distance))
            wait(1)
            espnow.send(id=1, data=str('beep'))
            last_msg = 'beep'
            label8.setText(str(last_msg))
            beep_return = True
            if j == 1:
              Warning2 = 1
              rectangle0.setBgColor(0x33ff33)
            elif j == 2:
              Warning2 = 2
              rectangle0.setBgColor(0xffcc66)
            else:
              Warning2 = 3
              rectangle0.setBgColor(0xff0000)
            wait(1)
            MQTT()
          elif (tof_0.distance) >= distance:
            label1.setText(str(tof_0.distance))
            beep_return = False
            espnow.send(id=1, data=str('close door'))
            last_msg = 'close door'
            label8.setText(str(last_msg))
            wait(1)
            break
        label7.setText('0')
        if beep_return:
          wait(2)
          espnow.send(id=1, data=str('sound fazbear'))
          last_msg = 'sound fazbear'
          label8.setText(str(last_msg))
          beep_return = False
          wait(12)
          espnow.send(id=1, data=str('close door'))
          last_msg = 'close door'
          label8.setText(str(last_msg))
          wait(1)
      if last_msg != 'close image' or last_msg != 'temp-warn':
        wait(2)
        espnow.send(id=1, data=str('close image'))
        last_msg = 'close image'
        label8.setText(str(last_msg))
    wait_ms(2)
```
