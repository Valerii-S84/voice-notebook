# Voice Notebook for Construction and Renovation Professionals

![App Logo](logo.png)

## Overview
This application is a **voice-based notebook** built with **MIT App Inventor**, created specifically for workers in construction and renovation.  
It allows quick and hands-free recording of:
- Completed work  
- Required materials  
- On-site notes  

All notes are stored locally on the device and organized by **ID**, **date**, and **time** for quick reference.  

---

## Main Features

### Screen1 – Main Recording Screen
![Record Button](record-button.png) ![View Button](view-button.png)  

- **Language Selection** – Choose the speech recognition language from a dropdown list.  
- **Persistent Settings** – The selected language and saved records remain after restarting the app (TinyDB storage).  
- **Voice Recording** – Tap the "Record" button to start speech recognition.  
- **Automatic Saving** – Each note is saved with an auto-incremented ID, date, and time.  
- **Navigation to Records** – "View" button opens Screen2 with all saved notes.  

**Purpose:** Designed for workers to quickly document work progress, materials, or other important notes directly via voice input.  

---

### Screen2 – Records Management Screen
![App Screenshot](app-interface.jpg)  

- **List View** – Displays all saved notes with date, time, and content.  
- **Delete Option** – Remove selected notes from both the list and TinyDB storage.  
- **Back Navigation** – Return to the main recording screen.  

**Purpose:** Provides an organized overview of recorded notes, making it easy to track work, materials, and tasks.  

---

## Technical Implementation

### Global Variables
- **language_codes** – Stores available languages and their codes.  
- **recordsList** – Stores all recorded entries.  
- **recordIdCouter** – Auto-increment counter for records.  
- **selected_language_code** – Stores the selected speech recognition language.  

### Screen1 – Blocks Description
1. **Initialization**
   - Load language list into Spinner.  
   - Request microphone access.  
   - Retrieve saved records and settings from TinyDB.  

2. **Language Selection (Spinner1.AfterSelecting)**
   - Updates `selected_language_code` and stores it in TinyDB.  

3. **Recording (Button_Record.Click)**
   - Starts speech recognition with the selected language.  

4. **Speech Recognizer Result**
   - Increments record ID.  
   - Saves note with ID, date, time, and recognized text.  
   - Updates TinyDB storage.  

5. **Navigation**
   - "View" button → Opens Screen2.  
   - On returning from Screen2 → Reloads records from TinyDB.  

### Screen2 – Blocks Description
1. **Initialization**
   - Loads saved records from TinyDB.  
   - Calls `updateListView` to display them.  

2. **updateListView Procedure**
   - Generates a display-friendly list from stored records.  
   - Updates ListView1 with the data.  

3. **Deleting Records (Button_Delete.Click)**
   - Removes selected record from the list.  
   - Updates TinyDB storage.  

4. **Navigation**
   - "Back" button closes the screen.  

---

## How It Works – User Flow

1. **Select Language**  
   - Open the app, choose your preferred recognition language from the dropdown.  

2. **Record a Note**  
   - Tap **Record**, speak your note (e.g., “Installed drywall in living room, need 5 more sheets”).  

3. **Automatic Saving**  
   - The app automatically assigns an ID, date, and time, and saves it.  

4. **View Notes**  
   - Tap **View** to open Screen2 and see all recorded notes.  

5. **Delete Notes**  
   - In Screen2, select a note and tap **Delete** to remove it.  

---

## Technology Used
- **MIT App Inventor** – No-code development platform for building Android apps.  
- **TinyDB** – Local storage for settings and records.  
- **SpeechRecognizer** – Converts voice input to text.  
- **Clock** – Generates current date and time for records.  

---

## Example Use Cases
- **On-site material tracking** – “Need 15 tiles, white grout, and silicone.”  
- **Work log** – “Finished plumbing in kitchen, tested water pressure.”  
- **Task reminders** – “Call supplier for cement delivery.”  

---

## Download
- **[APK file](VoiceNotebook.apk)** – ready to install on Android.  
- **[AIA file](VoiceNotebook.aia)** – source code for MIT App Inventor.  

---

## License
MIT License or any license you prefer.
