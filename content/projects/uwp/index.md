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

### **Home Dashboard (MainPage.xaml.cs)**
- Real-time clock with day/date/time and time-aware greeting (Morning / Afternoon / Evening / Night)
- Location-aware weather summary
- Forecast widget with dynamic icons and key metrics (max/min temperature, wind, humidity, precipitation)
- Touch-first widget interactions (drag + transform support via manipulation handlers)

<div class="grid grid-cols-1 sm:grid-cols-1 gap-6 mt-2 mb-6">
  <div class="flex flex-col items-center">
    <img src="Media/MainPage.png" alt="Vantage Hub - Home Dashboard (weather + greeting)" class="w-full h-auto rounded-xl shadow-md" loading="lazy">
    <div class="text-sm text-gray-600 dark:text-gray-300 mt-1">Home dashboard with live weather, greeting, and forecast widget</div>
  </div>
</div>

### **Alarm & Stopwatch (MainPage.xaml.cs)**
- Create, edit, and delete alarms with repeating schedules (weekday selection)
- One-time alarms supported (auto-disabled after expiry)
- Multiple alarm sounds with looping playback
- JSON-based persistence for alarms and user preferences
- Built-in stopwatch module (start / pause / reset)

<div class="grid grid-cols-1 sm:grid-cols-1 gap-6 mt-2 mb-6">
  <div class="flex flex-col items-center">
    <img src="Media/Alarm.png" alt="Vantage Hub - Alarm and Stopwatch Page" class="w-full h-auto rounded-xl shadow-md" loading="lazy">
    <div class="text-sm text-gray-600 dark:text-gray-300 mt-1">Alarm management and stopwatch module</div>
  </div>
</div>

### **MediaHub: Music, Radio, Video (Music.xaml.cs)**
- **Music**: local playback with shuffle/loop, playback controls, progress slider, volume control
- **Radio**: station browser with metadata (e.g., codec/bitrate/votes), live streaming playback
- **Video**: video playback with file picker support and full player controls
- Consistent “card grid” browsing UI for discovery + a focused playback view

<div class="grid grid-cols-1 sm:grid-cols-3 gap-6 mt-2 mb-6">
  <div class="flex flex-col items-center">
    <img src="Media/MediaHub-Music.png" alt="MediaHub - Music library grid" class="w-full h-auto rounded-xl shadow-md" loading="lazy">
    <div class="text-sm text-gray-600 dark:text-gray-300 mt-1">Music: library grid + playback controls</div>
  </div>
  <div class="flex flex-col items-center">
    <img src="Media/MediaHub-Radio.png" alt="MediaHub - Radio station grid" class="w-full h-auto rounded-xl shadow-md" loading="lazy">
    <div class="text-sm text-gray-600 dark:text-gray-300 mt-1">Radio: station grid + live playback</div>
  </div>
  <div class="flex flex-col items-center">
    <img src="Media/MediaHub-Video.png" alt="MediaHub - Video player view" class="w-full h-auto rounded-xl shadow-md" loading="lazy">
    <div class="text-sm text-gray-600 dark:text-gray-300 mt-1">Video: in-app player with controls</div>
  </div>
</div>

<div class="grid grid-cols-1 sm:grid-cols-3 gap-6 mt-2 mb-6">
  <div class="flex flex-col items-center">
    <img src="Media/MediaHub-Music-Expand.png" alt="MediaHub - Music expanded grid view" class="w-full h-auto rounded-xl shadow-md" loading="lazy">
    <div class="text-sm text-gray-600 dark:text-gray-300 mt-1">Music: extended browsing view</div>
  </div>
  <div class="flex flex-col items-center">
    <img src="Media/MediaHub-Radio-Expand.png" alt="MediaHub - Radio expanded grid view" class="w-full h-auto rounded-xl shadow-md" loading="lazy">
    <div class="text-sm text-gray-600 dark:text-gray-300 mt-1">Radio: extended station browsing view</div>
  </div>
  <div class="flex flex-col items-center">
    <img src="Media/MediaHub-Video-Expand.png" alt="MediaHub - Video expanded view" class="w-full h-auto rounded-xl shadow-md" loading="lazy">
    <div class="text-sm text-gray-600 dark:text-gray-300 mt-1">Video: full playback view</div>
  </div>
</div>

### **Doodle + AI Chat (Sketching.xaml.cs)**
- InkCanvas drawing with pen + touch input, including pressure support (when using stylus)
- Pen colour + stroke size controls, eraser mode, clear canvas
- Import background images for tracing and export drawings as PNG
- Gemini-powered chatbot experience with:
  - speech-to-text dictation for message input
  - text-to-speech playback for AI responses
  - copy-to-clipboard for quick reuse
- Hover-to-reveal switch button that swaps the Doodle and Chat panels (grid column swap)

<div class="grid grid-cols-1 sm:grid-cols-1 gap-6 mt-2 mb-6">
  <div class="flex flex-col items-center">
    <img src="Media/Doodle+AI.png" alt="Vantage Hub - Doodle canvas and AI chatbot split view" class="w-full h-auto rounded-xl shadow-md" loading="lazy">
    <div class="text-sm text-gray-600 dark:text-gray-300 mt-1">Split view: digital sketching canvas + AI chatbot</div>
  </div>
</div>

### **App Switcher (Keyboard + Gesture)**
- **Keyboard:** `Ctrl + Space` opens the app switcher; while holding `Ctrl`, press `Space` to cycle; releasing selects (Alt+Tab style).
- **Gesture:** swipe up from the bottom interaction zone to open the app switcher (touch-friendly flow).

---

## **Tech Stack**
- **Framework:** Universal Windows Platform (UWP) with C# and XAML
- **UI Design:** Windows.UI.Xaml with adaptive layouts (touch + desktop)
- **Weather API:** OpenWeatherMap (forecast endpoint)
- **Radio:** station browsing + streaming via a custom radio API client
- **AI Integration:** Google Gemini (generative AI)
- **Speech:** Windows.Media.SpeechRecognition and SpeechSynthesis
- **Inking:** Windows.UI.Input.Inking (InkCanvas)
- **Serialisation:** Newtonsoft.Json for data persistence

---

## **My Role**
Sole developer responsible for:
- End-to-end UWP application architecture and UI/UX design
- Integration of external APIs (weather, radio, generative AI)
- Implementation of alarms (recurring + one-time), sound playback, and stopwatch utilities
- MediaHub development (music, radio streaming, video playback)
- InkCanvas drawing tools + export pipeline
- Accessibility-focused features (speech-to-text + text-to-speech)
- Persistent storage for alarms and preferences

---

## **Quick Start (User Controls)**
- **Switch apps:** `Ctrl + Space` (hold Ctrl, tap Space to cycle, release to select)
- **Touch switcher:** swipe up from the bottom zone to open the app switcher
- **Doodle/Chat layout:** hover to reveal the switch button, then tap to swap panels

---

## **Project Structure**

| Folder/File | Description |
|------------|-------------|
| `MainPage.xaml(.cs)` | Home dashboard, weather, greetings, alarms, and stopwatch module |
| `Music.xaml(.cs)` | MediaHub: music library + player, radio station browser, video playback |
| `Sketching.xaml(.cs)` | InkCanvas doodle tools + AI chatbot (speech + TTS) + panel swap |
| `OpenWeatherMap.cs` | Weather API integration + data models |
| `radio-API.cs` | Radio station retrieval + streaming metadata client |
| `audio/` | Alarm sound files and bundled music tracks |
| `weather_icons/` | Weather condition icon assets |
| `icons/` | UI icons for controls and navigation |
| `musicart/` | Album art assets for bundled tracks |

---

## **Outcome**
This project demonstrates proficiency in:
- **UWP Development:** building a polished multi-page Windows application with touch-first UX
- **API Integration:** consuming live data sources for weather, radio, and AI features
- **Multi-feature Architecture:** coordinating alarms, media playback, AI chat, and inking within a cohesive UI
- **Accessibility:** speech-to-text and text-to-speech for inclusive interaction
- **State Management:** persistent storage, timers, and async flows across multiple modules
