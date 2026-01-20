
---
title: Healthify
summary: A Flutter (Material 3) healthcare app with AI-powered assistance, clinic discovery, and appointment booking.
date: 2025-08-14

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

<a href="https://github.com/Cayden2606/Healthify" style="display:flex;align-items:center;gap:10px;" target="_blank" rel="noopener">
  <img src="https://github.githubassets.com/images/modules/logos_page/GitHub-Mark.png" alt="GitHub Logo" style="width:28px;height:28px;">
  GitHub Repository for Healthify
</a>

---

## **Overview**
**Healthify** is a comprehensive Flutter healthcare application that makes healthcare accessible, intelligent, and user-friendly. Built with **Material Design 3**, the app provides:
- **AI-powered health assistance** using Google Gemini 2.0 Flash
- **Interactive clinic discovery** via OpenStreetMap and GPS location services
- **Smart appointment booking** with email notifications
- **Personal health management** features tailored for Singapore

> **📚 School Project Disclaimer**  
> This is a mock concept application developed by **Jethro and I** as part of our **EGE312 Mobile Computing Project (Year 3, Computer Engineering Specialisation)**. No actual clinic bookings or medical appointments are made through this app. All features are for demonstration and educational purposes only.

Your health and wellness journey starts here.

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

### **🤖 AI Health Assistant (Google Gemini 2.0 Flash)**
- **Natural chat interface** for intelligent health conversations
- **Image analysis** — upload medical images for AI-powered insights
- **Markdown support** with rich text formatting (code blocks, lists, tables, blockquotes)
- **Appointment intent detection** — AI extracts booking intent and suggests appropriate services
- **Conversational memory** — maintains context throughout discussions
- **AI shortcuts** — quick access buttons for Symptoms, Medicines, and Wellness tips

### **📅 Smart Appointment Management**
- **Step-by-step booking flow** with service selection, date/time picker, and clinic selection
- **AI-assisted booking** — Gemini suggests appropriate appointment types based on conversations
- **Full CRUD operations** — create, view, edit, and cancel appointments
- **Status tracking** — automatic status updates (upcoming → passed) based on time
- **Email notifications** — confirmation emails sent via Resend API
- **Comprehensive service categories**:
  - **Doctor Consultation** (General, Chronic Conditions, Family Planning, Specialist Referral)
  - **Vaccination** (Adult, Child, COVID-19, Flu, Travel)
  - **Screening & Tests** (Cervical Cancer, Diabetic Eye, Mammogram, Blood Pressure, Cholesterol)
  - **Nursing Services** (Wound Dressing, Injection, Health Education, Postnatal Care)
  - **Allied Health** (Nutritionist, Physiotherapy, Medical Social Service, Financial Counselling)
  - **Dental** (Cleaning, Check-up, Fluoride Treatment, X-Ray)

### **🗺️ Interactive Clinic Discovery**
- **Flutter Map integration** with OpenStreetMap tiles for interactive clinic locator
- **Geoapify API** integration fetching healthcare clinics across Singapore
- **Multiple search options**:
  - By Region (Central, Northwest, Southwest, Northeast, Southeast)
  - By Distance (5km radius from current location)
  - Saved Clinics (personal favorites)
  - Open Status (currently operating clinics)
- **Real-time GPS** with accurate location services using Geolocator
- **Opening hours parser** with intelligent OSM format parsing
- **Distance calculation** using Haversine formula for accuracy
- **Draggable bottom sheet** with smooth clinic list UI

### **👤 User Profile & Personalization**
- **Comprehensive profile management** — name, contact, age, gender, email
- **Profile pictures** — Cloudinary integration for image upload and hosting
- **International phone input** with country code selector and validation
- **Theme customization**:
  - Dark/Light mode toggle with persistence
  - 15+ color palette options for theme personalization
- **Language support** — English (currently supported)
- **Firebase sync** — all preferences stored and synced across devices

### **🚶 Health Tracking**
- **Real-time step counter** using pedometer integration
- **Activity permissions** for Android activity recognition
- **Daily goals** with visual progress tracking

### **🎨 Onboarding Experience**
- **4-page introduction** — Welcome, AI Assistant, Find & Connect, Get Started
- **Shared preferences** — remembers first-time users
- **Animated transitions** with smooth page indicators and navigation  

---

## **Tech Stack**

| Category | Technology |
|----------|------------|
| **Framework** | Flutter 3.6.0+ / Dart ^3.6.0 |
| **UI Design** | Material Design 3 with custom theming, Product Sans typography |
| **Backend** | Firebase (Authentication, Firestore) |
| **State Management** | Provider + StatefulWidget patterns |
| **AI Integration** | Google Gemini 2.0 Flash via `flutter_gemini` |
| **Chat UI** | Dash Chat 2, Flutter Markdown |
| **Maps** | Flutter Map + OpenStreetMap tiles |
| **Location Services** | Geolocator, Geoapify Places API |
| **Image Storage** | Cloudinary (profile pictures) |
| **Email Service** | Resend API |
| **Health Tracking** | Pedometer, Permission Handler |
| **UI/UX Libraries** | Community Material Icons, Font Awesome Flutter, Flutter SVG |

### **Key Dependencies**
- **Core**: `flutter_gemini`, `dash_chat_2`, `flutter_markdown`
- **Firebase Suite**: `firebase_core`, `firebase_auth`, `firebase_ui_auth`, `cloud_firestore`
- **Location & Maps**: `flutter_map`, `geolocator`, `latlong2`
- **UI Libraries**: `provider`, `community_material_icon`, `font_awesome_flutter`, `flutter_svg`
- **User Input**: `phone_input`, `image_picker`
- **Utilities**: `http`, `flutter_dotenv`, `url_launcher`, `shared_preferences`, `resend`

---

## **My Role**

As a co-developer, I was responsible for designing and implementing core features across the entire application stack:

### **AI Integration**
- Integrated **Google Gemini 2.0 Flash** API for health conversations
- Implemented system prompt engineering for healthcare context
- Built JSON-structured appointment intent extraction from conversations
- Developed conversational history management (last 6 messages context)
- Created image analysis feature with `textAndImage` API
- Added real-time typing animations during AI responses

### **Location & Maps**
- Built **interactive clinic discovery** system with Flutter Map and OpenStreetMap
- Integrated **Geoapify Places API** for fetching healthcare facilities across Singapore
- Implemented **real-time GPS tracking** with permission handling
- Developed **Haversine formula** for accurate distance calculations
- Created region-based and radius-based clinic search functionality (5km default)
- Built background clinic caching to Firestore for performance

### **Appointment System**
- Designed and implemented **multi-step booking flow** (Category → Service → Date → Time → Info)
- Built **full CRUD operations** for appointment management
- Implemented **AI-assisted booking** with pre-fill from conversations
- Created automatic status transition system (upcoming → passed)
- Integrated **Resend API** for email confirmations
- Developed Firestore batched writes for efficient data operations

### **UI/UX & Theming**
- Implemented **Material Design 3** color scheme with seed colors
- Built **custom theme system** with 15 curated color palettes
- Developed dark/light mode toggle with Firebase persistence
- Created HSL color manipulation for dark mode variations
- Integrated **Product Sans** custom typography
- Built onboarding flow with animated transitions

### **Additional Contributions**
- Set up Firebase Authentication and Firestore database architecture
- Implemented Cloudinary integration for profile picture uploads
- Built comprehensive user profile management system
- Performed testing, bug-fixing, and performance optimization across the app

---

## **Technical Implementation Highlights**

### **AI Health Assistant Architecture**
The health assistant leverages **Google Gemini 2.0 Flash** for intelligent health guidance through:
- **System prompt engineering** tailored for healthcare context and appropriate medical disclaimers
- **JSON-structured appointment intent extraction** to parse user requests into actionable booking data
- **Conversational history management** maintaining the last 6 messages for context continuity
- **Real-time typing animation** during AI response generation for better UX
- **Image analysis with `textAndImage` API** for medical image interpretation
- **Automatic nearest clinic detection** for seamless booking flow

### **Location Services & Mapping**
- **Real-time GPS tracking** with comprehensive permission handling
- **Distance calculation using the Haversine formula** for accurate clinic proximity
- **Region-based clinic search** mapped to Singapore's Community Development Council (CDC) regions
- **Radius-based search** with configurable 5km default range
- **Background clinic caching to Firestore** for improved performance and offline support
- **OSM opening hours format parser** for accurate "open now" filtering

### **Appointment Booking System**
- **Multi-step wizard UI** guiding users through: Category → Service → Date → Time → Info
- **Pre-fill from AI conversation** or existing appointment for editing
- **Edit and reschedule functionality** for upcoming appointments
- **Automatic status transition** based on appointment date/time
- **Firestore batched writes** for atomic multi-document operations
- **Resend API integration** for professional email notifications

### **Dynamic Theme System**
- **Material Design 3 color scheme seeding** for consistent, modern UI
- **HSL color manipulation** for harmonious dark mode variations
- **Per-user theme persistence** in Firestore for cross-device sync
- **15 curated pastel color options** providing visual variety
- **Custom Product Sans typography** throughout the app

### **Firebase Data Structure**

The app uses three main Firestore collections:

**`appUsers`** — User profiles with preferences
```json
{
  "userid": "firebase-uid",
  "name": "John",
  "nameLast": "Doe",
  "email": "john@example.com",
  "contact": "+65 9123 4567",
  "age": "25",
  "gender": "Male",
  "profilePic": "https://cloudinary.com/...",
  "darkMode": false,
  "colorSeed": 4290190335,
  "savedClinics": ["place_id_1", "place_id_2"]
}
```

**`appointments`** — Appointment records
```json
{
  "userId": "firebase-uid",
  "placeId": "clinic-place-id",
  "appointmentDateTime": "Timestamp",
  "serviceCategory": "Doctor Consultation",
  "serviceType": "General Consultation",
  "status": "upcoming",
  "additionalInfo": "",
  "createdAt": "Timestamp"
}
```

**`clinics`** — Cached clinic data from Geoapify
```json
{
  "properties": {
    "name": "Clinic Name",
    "place_id": "geoapify-place-id",
    "address_line2": "Address",
    "opening_hours": "Mo-Fr 09:00-18:00",
    "contact": { "phone": "+65...", "email": "..." },
    "facilities": { "wheelchair": true }
  },
  "geometry": { "coordinates": [103.8, 1.3] }
}
```

---

## **API Keys & Services**

The application integrates with multiple third-party services:

| Service | Purpose | Get Key |
|---------|---------|---------|
| **Google Gemini** | AI chat & image analysis | [AI Studio](https://aistudio.google.com/) |
| **Geoapify** | Clinic location data | [Geoapify](https://www.geoapify.com/) |
| **Resend** | Email notifications | [Resend](https://resend.com/) |
| **Cloudinary** | Profile image hosting | [Cloudinary](https://cloudinary.com/) |
| **Firebase** | Authentication & Database | [Firebase Console](https://console.firebase.google.com/) |

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
CLOUDINARY_CLOUD_NAME=your_cloudinary_cloud_name
CLOUDINARY_UPLOAD_PRESET=your_cloudinary_upload_preset
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
├── main.dart                    # App entry point, theme configuration, routes
├── firebase_options.dart        # Firebase configuration
│
├── models/                      # Data models
│   ├── app_user.dart           # User profile with theme preferences
│   ├── appointment.dart        # Appointment with clinic reference
│   ├── appointment_data.dart   # Service categories and time slots
│   ├── clinic.dart             # Clinic with Geoapify JSON parsing
│   ├── gemini_appointment.dart # AI-extracted appointment intent
│   ├── opening_hours.dart      # OSM opening hours parser
│   ├── settings_item.dart      # Settings list item model
│   └── theme_colors.dart       # Available theme color palette
│
├── screens/                     # UI screens
│   ├── appointments_screen.dart    # View/manage appointments
│   ├── clinics_screen.dart         # Map + clinic discovery
│   ├── health_assistant.dart       # AI chat interface
│   ├── home.dart                   # Dashboard with steps, shortcuts
│   ├── login_screen.dart           # Firebase authentication
│   ├── make_appointments_screen.dart # Booking workflow
│   ├── onboarding_screen.dart      # First-time user intro
│   ├── settings.dart               # App settings & profile
│   └── update_app_user_screen.dart # Profile editor
│
├── utilities/                   # Backend services
│   ├── firebase_calls.dart     # Firestore CRUD, auth, themes
│   ├── geoapify_calls.dart     # Clinic API integration
│   └── status_bar_utils.dart   # System UI styling
│
└── widgets/                     # Reusable components
    ├── bottom_navigation_bar.dart
    ├── appointments/           # Appointment list widgets
    ├── clinics/               # Map, search bar, dialogs
    ├── home/                  # App bar, search, steps card, schedule
    └── make_appointments/     # Booking flow components
```

---

## **Outcome**

Healthify demonstrates a practical integration of **AI**, **maps**, and **secure user management** to deliver a simple, end-to-end healthcare workflow — from asking questions to finding a clinic and booking an appointment.

---

## **Screenshots** 📱

<div style="text-align: center;">
  <img src="screenshots/app_icon.png" alt="App Icon" style="width: 120px; border-radius: 24px;">
</div>

### **Onboarding**
<div style="display: flex; flex-wrap: wrap; justify-content: center; gap: 10px;">
  <img src="screenshots/introScreen1.png" alt="Intro 1" style="flex: 1 1 150px; max-width: 200px;">
  <img src="screenshots/introScreen2.png" alt="Intro 2" style="flex: 1 1 150px; max-width: 200px;">
  <img src="screenshots/introScreen3.png" alt="Intro 3" style="flex: 1 1 150px; max-width: 200px;">
  <img src="screenshots/introScreen4.png" alt="Intro 4" style="flex: 1 1 150px; max-width: 200px;">
</div>

### **Authentication & Home**
<div style="display: flex; flex-wrap: wrap; justify-content: center; gap: 10px;">
  <img src="screenshots/loginscreen.PNG" alt="Login" style="flex: 1 1 150px; max-width: 200px;">
  <img src="screenshots/HomeScreen.PNG" alt="Home" style="flex: 1 1 150px; max-width: 200px;">
  <img src="screenshots/lightpurpleHome.PNG" alt="Home Light Purple Theme" style="flex: 1 1 150px; max-width: 200px;">
  <img src="screenshots/DarkRedishHome.PNG" alt="Home Dark Reddish Theme" style="flex: 1 1 150px; max-width: 200px;">
</div>

### **AI Health Assistant**
<div style="display: flex; flex-wrap: wrap; justify-content: center; gap: 15px;">
  <img src="screenshots/AIChat.PNG" alt="AI Chat" style="flex: 1 1 250px; max-width: 300px;">
  <img src="screenshots/AIChatWithPicture.PNG" alt="AI Image Analysis" style="flex: 1 1 250px; max-width: 300px;">
</div>

### **Clinic Discovery**
<div style="display: flex; flex-wrap: wrap; justify-content: center; gap: 10px;">
  <img src="screenshots/ClinicMapRegions.PNG" alt="Regions" style="flex: 1 1 150px; max-width: 200px;">
  <img src="screenshots/ClinicsMapNearby.png" alt="Nearby" style="flex: 1 1 150px; max-width: 200px;">
  <img src="screenshots/ClinicMapSaved.PNG" alt="Saved" style="flex: 1 1 150px; max-width: 200px;">
  <img src="screenshots/ClinicMapOpen.PNG" alt="Open" style="flex: 1 1 150px; max-width: 200px;">
</div>

### **Appointment Booking**
<div style="display: flex; flex-wrap: wrap; justify-content: center; gap: 10px;">
  <img src="screenshots/makeAppointmentScreen1.png" alt="Select Category" style="flex: 1 1 150px; max-width: 200px;">
  <img src="screenshots/makeAppointmentScreen2.png" alt="Select Service" style="flex: 1 1 150px; max-width: 200px;">
  <img src="screenshots/makeAppointmentScreen3.png" alt="Select Date" style="flex: 1 1 150px; max-width: 200px;">
  <img src="screenshots/makeAppointmentScreen4.png" alt="Select Time" style="flex: 1 1 150px; max-width: 200px;">
</div>

### **Appointments Management**
<div style="display: flex; flex-wrap: wrap; justify-content: center; gap: 10px;">
  <img src="screenshots/UpcomingAppointment.png" alt="Upcoming" style="flex: 1 1 120px; max-width: 180px;">
  <img src="screenshots/ViewLocationOfAppointmentOnGoogleMapsOrHealthify.PNG" alt="Location" style="flex: 1 1 120px; max-width: 180px;">
  <img src="screenshots/EditUpcommingAppointment.PNG" alt="Edit Appointment" style="flex: 1 1 120px; max-width: 180px;">
  <img src="screenshots/PassedAppointment.png" alt="Passed" style="flex: 1 1 120px; max-width: 180px;">
  <img src="screenshots/EmailNotficationResend.png" alt="Email Notification" style="flex: 1 1 120px; max-width: 180px;">
</div>

### **Settings & Profile**
<div style="display: flex; flex-wrap: wrap; justify-content: center; gap: 15px;">
  <img src="screenshots/SettingsPage.png" alt="Settings" style="flex: 1 1 200px; max-width: 220px;">
  <img src="screenshots/SettingsPageDarkMode.png" alt="Dark Mode" style="flex: 1 1 200px; max-width: 220px;">
  <img src="screenshots/SettingsPageThemesOptions.png" alt="Themes" style="flex: 1 1 200px; max-width: 220px;">
</div>

### **User Profile**
<div style="display: flex; flex-wrap: wrap; justify-content: center; gap: 15px;">
  <img src="screenshots/UpdateUserProfilePage.png" alt="Profile" style="flex: 1 1 250px; max-width: 300px;">
  <img src="screenshots/UpdateUserPhoneNumber.png" alt="Phone Input" style="flex: 1 1 250px; max-width: 300px;">
</div>

---
