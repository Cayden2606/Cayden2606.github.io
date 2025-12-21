---
title: Vantage Hub
summary: A feature-rich Windows UWP smart hub application integrating live weather, alarm management, music and radio streaming, an AI chatbot, and a digital sketching canvas.
date: 2024-12-21

image:
  caption: 'Image credit: **Cayden**'

authors:
  - admin

tags:
  - C#
  - UWP
  - XAML
  - AI Integration
  - API Integration
  - Desktop App
---

{{< toc mobile_only=true is_open=true >}}

<a href="https://github.com/Cayden2606/Vantage-Hub" style="display:flex;align-items:center;gap:10px;" target="_blank" rel="noopener">
  <img src="https://github.githubassets.com/images/modules/logos_page/GitHub-Mark.png" alt="GitHub Logo" style="width:28px;height:28px;">
  GitHub Repository
</a>

---

## **Overview**
Vantage Hub is a multi-functional Windows UWP desktop application designed to serve as a personal smart hub. It combines essential daily utilities—weather forecasting, alarm management, media playback, AI-assisted chat, and digital sketching—into a unified, modern interface optimised for both touch and desktop interaction.

---

## **Problem**
Users often juggle multiple standalone apps for weather, alarms, music, and productivity tools, resulting in a fragmented desktop experience. Vantage Hub consolidates these core features into a single cohesive application that provides quick access to everyday utilities, reducing cognitive load and improving workflow efficiency.

---

## **Key Features**

### **Home Dashboard**
- Real-time weather display with a 5-day forecast using geolocation
- Dynamic weather icons for various conditions (clear, cloudy, rain, thunderstorms)
- Time-aware greeting messages (Good Morning / Afternoon / Evening / Night)
- Customisable greeting text with persistent storage

### **Alarm System**
- Create, edit, and delete alarms with repeating schedules
- Support for one-time and recurring alarms (by weekday)
- Multiple alarm sound options with looping playback
- Automatic disabling of expired one-time alarms
- JSON-based persistent storage

### **Media Player**
- Local music playback with shuffle and loop modes
- Live radio streaming via the Radio Browser API (Singapore stations)
- Video playback with file picker support
- Media progress slider, volume control, and mute functionality
- Album art and station metadata display

### **AI Chatbot**
- Integration with Google Gemini 2.0 Flash API for conversational AI
- Copy-to-clipboard functionality for AI responses
- Text-to-speech (TTS) output for AI replies
- Voice input via Windows Speech Recognition

### **Digital Sketching Canvas**
- Ink canvas with pressure sensitivity support
- Customisable pen colour and stroke size
- Eraser tool and clear canvas functionality
- Import background images for tracing
- Export drawings as PNG images
- Swappable panel layout between chatbot and canvas

### **App Switcher**
- Keyboard shortcut navigation (`Ctrl + Space`) between pages
- Touch-enabled swipe gestures for multi-app switching
- Acrylic blur effects for modern UI aesthetics

---

## **Tech Stack**
- **Framework:** Universal Windows Platform (UWP) with C# and XAML
- **UI Design:** Windows.UI.Xaml with Acrylic effects, custom styling, and adaptive layouts
- **Weather API:** OpenWeatherMap (5-day forecast endpoint)
- **Radio API:** Radio Browser public API
- **AI Integration:** Google Gemini 2.0 Flash generative AI API
- **Speech:** Windows.Media.SpeechRecognition and SpeechSynthesis
- **Inking:** Windows.UI.Input.Inking for pen and touch sketching
- **Serialisation:** Newtonsoft.Json for alarm and API data handling

---

## **My Role**
Sole developer responsible for:
- End-to-end UWP application architecture and UI/UX design
- Integration of multiple external APIs (OpenWeatherMap, Radio Browser, Google Gemini)
- Implementation of alarm scheduling, media playback, and inking features
- Development of accessibility features including voice input and text-to-speech
- Persistent data management for alarms and user preferences

---

## **Project Structure**

| Folder/File | Description |
|------------|-------------|
| `MainPage.xaml(.cs)` | Home dashboard with weather, greeting, and alarm widgets |
| `Music.xaml(.cs)` | Music, radio, and video playback interface |
| `Sketching.xaml(.cs)` | AI chatbot and digital sketching canvas |
| `OpenWeatherMap.cs` | Weather API integration and data models |
| `radio-API.cs` | Radio Browser API client and data models |
| `audio/` | Alarm sound files and bundled music tracks |
| `weather_icons/` | SVG icons for weather conditions |
| `icons/` | UI icons for controls and app switcher |
| `musicart/` | Album cover images for bundled music |

---

## **Outcome**
This project demonstrates proficiency in:
- **UWP Development:** Building a polished Windows application using Fluent Design principles
- **API Integration:** Consuming RESTful APIs for weather, radio streaming, and generative AI
- **Multi-feature Architecture:** Coordinating alarms, media playback, AI chat, and inking within a single cohesive application
- **Accessibility:** Implementing speech-to-text and text-to-speech for inclusive user interaction
- **State Management:** Managing persistent data storage, timers, and asynchronous API calls
