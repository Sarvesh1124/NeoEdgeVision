# NeoEdgeVision  
Android (Kotlin + C++ OpenCV) and Web (TypeScript) Platform

---

## Overview
NeoEdgeVision is a cross-platform project integrating:
- Android (Kotlin + C++ + OpenCV) for real-time edge vision processing using JNI.
- Web (TypeScript + HTML + CSS) viewer for visualizing live video input.

This project demonstrates JNI-based native processing pipelines in Android and a lightweight TypeScript front-end for visualization.  
Developed as part of a Software Engineering Intern (R&D) Assignment.

---

## Features Implemented

### Android App
- Built using Kotlin with JNI (C++) backend.
- Integrated OpenCV 4.8.0 Android SDK.
- Processes frames using native C++ OpenCV (Gaussian blur applied to camera frames).
- JNI bridge between Kotlin and C++ for real-time communication.
- Logcat output verification for native call flow.

### Web Viewer
- Developed using TypeScript, HTML, and CSS.
- Streams live webcam feed in the browser.
- Responsive UI styled with CSS.

---

## Project Architecture

### Android Processing Flow
Kotlin (MainActivity, NativeBridge)
↓
JNI Bridge
↓
C++ (native-lib.cpp)
↓
OpenCV Processing


### Web Flow
TypeScript → HTML5 Video Element → Camera Stream → User Display

## Setup Instructions

### Android (Kotlin + C++)
#### Prerequisites
- Android Studio (latest version)
- SDK, NDK, and CMake installed  
  (Configure via: File → Project Structure → SDK Location)
- OpenCV Android SDK (v4.8.0) extracted at:

- C:/OpenCV-4.8.0-android-sdk/

- 
#### Folder Structure
app/
├── src/
│ ├── main/
│ │ ├── java/com/neo/edgevision/
│ │ │ ├── MainActivity.kt
│ │ │ └── NativeBridge.kt
│ │ ├── cpp/
│ │ │ ├── CMakeLists.txt
│ │ │ └── native-lib.cpp
│ │ └── res/layout/activity_main.xml
│ └── AndroidManifest.xml
└── build.gradle.kts


#### Build Steps
1. Open the project in Android Studio.
2. Click **Build → Make Project**.
3. Connect an Android device and click **Run**.
4. Open **Logcat** and search for:
JNI bridge called. Frame processed successfully with OpenCV!


#### Notes
- Update the OpenCV path in `CMakeLists.txt` if the SDK is in a different location.
- Ensure the following libraries are loaded:
```kotlin
System.loadLibrary("native-lib")
System.loadLibrary("opencv_java4")

Web (TypeScript + HTML)
web/
 ├── index.html
 ├── style.css
 └── script.ts

Run Instructions
Open index.html in a browser.
Allow camera access when prompted.
The live webcam video stream will appear.

Technologies Used
Component	        Technology
Android         	Kotlin, C++, JNI, OpenCV
Web	              TypeScript, HTML, CSS
Build             Tools	Gradle, CMake
IDE	              Android Studio

Commit History (Development Process)
Commit Message	                              Description
init: setup Android project structure    	Base Android project created
feat: add JNI bridge	                    Added NativeBridge.kt and native C++ connection
feat: add OpenCV processing	              Implemented Gaussian blur frame operation
feat: add TypeScript web viewer	          Added web/ folder for browser-side viewer
docs: add README + architecture details	  Documented setup and architecture
docs: add screenshots	                    Added demo images

Expected Log Output
I/NeoEdgeVision: JNI bridge called. Frame size: 640x480
I/NeoEdgeVision: Frame processed successfully with OpenCV!
I/NeoEdgeVision: MainActivity initialized successfully

Author
Sarvesh Prakashkokatnur
Software Engineering Intern (R&D) — NeoEdgeVision Submission

License
This repository is for educational and evaluation purposes only.
© 2025 NeoEdgeVision — Research & Development Assignment Submission.


