
---
title: Healthify
summary: A Flutter (Material 3) healthcare app with AI-powered assistance, clinic discovery, and appointment booking.
date: 2025-12-21

# Featured image
# Place an image named `featured.jpg/png` in this page's folder and customise its options here.
image:
  caption: 'Image credit: **Me**'

authors:
  - admin
  - Jethro

tags:
  - Flutter
  - Android
  - Firebase
  - Google Gemini
  - OpenStreetMap
  - Material 3
---

{{< toc mobile_only=true is_open=true >}}

<a href="hhttps://github.com/Shockz132/Healthify" style="display:flex;align-items:center;gap:10px;" target="_blank" rel="noopener">
  <img src="https://github.githubassets.com/images/modules/logos_page/GitHub-Mark.png" alt="GitHub Logo" style="width:28px;height:28px;">
  GitHub Repository for Healthify
</a>

---

## **Overview**
**Healthify** is an Android app built with **Flutter (Material 3)** that makes healthcare access more convenient through:
- an **AI Health Assistant** (Google Gemini),
- **clinic discovery** via maps and location services,
- and a streamlined **appointment booking** experience.

Built by **Jethro and I** for our **Mobile Computing Project (Year 3, Computer Engineering Specialisation)**.

---

## **Slides**
<div style="position: relative; width: 100%; height: 0; padding-top: 56.2500%;
 padding-bottom: 0; box-shadow: 0 2px 8px 0 rgba(63,69,81,0.16); margin-top: 1.6em; margin-bottom: 0.9em; overflow: hidden;
 border-radius: 8px; will-change: transform;">
  <iframe loading="lazy" style="position: absolute; width: 100%; height: 100%; top: 0; left: 0; border: none; padding: 0; margin: 0;"
    src="https://www.canva.com/design/DAGvLy6Wqig/CUJ1cLR7Zzk7kO5zAYV-Xw/view?embed" allowfullscreen="allowfullscreen" allow="fullscreen">
  </iframe>
</div>
<a href="https:&#x2F;&#x2F;www.canva.com&#x2F;design&#x2F;DAGvLy6Wqig&#x2F;CUJ1cLR7Zzk7kO5zAYV-Xw&#x2F;view?utm_content=DAGvLy6Wqig&amp;utm_campaign=designshare&amp;utm_medium=embeds&amp;utm_source=link" target="_blank" rel="noopener">Healthify</a> by caydenmtheseira

---

## **Problem**
Finding clinics, understanding what service you need, and booking appointments often requires:
- switching between apps or websites,
- searching unfamiliar clinic details,
- and navigating unclear booking flows.

Healthify consolidates these steps into a single, user-friendly workflow.

---

## **Key Features**
### **🤖 AI Health Assistant (Gemini)**
- Natural chat interface for health-related questions  
- Supports **image uploads** for AI-powered analysis and insights  
- Maintains conversational context for more useful follow-ups  
- Helps infer **booking intent** from user inputs  

### **📅 Appointment Booking**
- Guided booking flow with **service categories**, time selection, and notes  
- Stores bookings and history in **Firebase Firestore**  
- Sends **email confirmations** using Resend API  

**Service Categories**
- Doctor Consultation
- Vaccination
- Screening & Tests
- Nursing Services
- Allied Health
- Dental

### **🗺️ Clinic Discovery & Maps**
- Interactive map built on **OpenStreetMap**
- Finds nearby clinics using **GPS** and distance calculations  
- Clinic cards with quick actions (save / book)  

### **👤 User Accounts & Profiles**
- Authentication via **Firebase Authentication**
- Profile management (e.g., name, age, contact details)  
- Profile pictures uploaded through **Cloudinary**  

---

## **Tech Stack**
- **Frontend**: Flutter 3.6.0+ (Material Design 3)
- **State Management**: Provider
- **Backend**: Firebase Authentication, Firestore
- **AI**: Google Gemini API
- **Maps & Location**: flutter_map, OpenStreetMap, geolocator, Geoapify
- **Email**: Resend API
- **Media**: Cloudinary

---

## **My Role**
I focused on building and integrating core mobile features across UI and functionality:
- Implemented **Material 3 UI theming** and screen layouts
- Built **map and location-based clinic discovery** (markers, distance logic, UI cards)
- Developed **appointment booking** workflows and Firestore integration
- Integrated the **Gemini AI assistant** into the chat experience
- Supported testing, bug-fixing, and performance improvements across the app

---

## **Getting Started**
1) Clone the repository:
```bash
git clone https://github.com/yourusername/Healthify.git
cd Healthify
````

2. Install dependencies:

```bash
flutter pub get
```

3. Create a `.env` file:

```env
GEMINI_API_KEY=your_gemini_api_key_here
GEOAPIFY_API_KEY=your_geoapify_api_key_here
RESEND_API_KEY=your_resend_api_key_here
```

4. Configure Firebase (Authentication + Firestore)

5. Run the app:

```bash
flutter run
```

---

## **Project Structure**

```
lib/
├── models/          # Data models (Clinic, Appointment, User)
├── screens/         # UI screens
│   ├── health_assistant.dart
│   └── make_appointments_screen.dart
├── utilities/       # Helper functions and Firebase calls
├── widgets/         # Reusable UI components
└── main.dart        # Application entry point
```

---

## **Outcome**

Healthify demonstrates a practical integration of **AI**, **maps**, and **secure user management** to deliver a simple, end-to-end healthcare workflow — from asking questions to finding a clinic and booking an appointment.



