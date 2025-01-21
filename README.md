# Smart Visitor Entry Management System

## Problem Statement
Currently, security guards at our college main gate manually record incoming vehicle details such as:
- Vehicle Number Plate
- Visitor Name
- Purpose of Visit
- Department
- Phone Number
- Time of Entry

This process is tedious and error-prone, especially during peak times when multiple vehicles arrive simultaneously, causing traffic congestion near the main gate.

## Proposed Solution
To streamline the visitor entry process and eliminate manual efforts, we propose a system that automates data collection and entry into a database to some extent. The guard will:
1. Press a button to initiate the data collection process.
2. Capture the car’s image via a webcam.
3. Speak the visitor's details into a microphone.

The captured data will then be:
1. Processed via APIs for image and audio.
2. Parsed using technologies such as YOLO for number plate detection and OpenAI Whisper for speech-to-text transcription.
3. Stored in a database (MongoDB/SQL) for efficient retrieval and record-keeping.

### System Flow Diagram
![System Flow Diagram](/diagram.png)

## System Overview
The system consists of two main components:
1. **Hardware**
2. **Software**

---

## Hardware
The hardware setup includes:
- **Webcam**: To capture images of incoming vehicles.
- **ESP32 Microcontroller**: Facilitates WiFi connectivity and serial communication.
- **Microphone**: Captures the guard’s voice input.
- **Power Source**: Powers the components.

### Setup Instructions
**(To Be Discussed)**
- Placement and wiring of the webcam, microphone, and ESP32.
- Power requirements and setup for reliable operation.
- Configuring ESP32 for seamless WiFi connectivity to APIs.

---

## Software
The software stack processes the captured data and appends it to a database.

### Components
1. **Microcontroller Logic**
   - Generates a unique serial number for each entry.
   - Sends image and audio data to respective API endpoints.

2. **API Endpoints**
   - **Image Endpoint**: Processes the vehicle image via YOLO to extract the number plate and time.
   - **Audio Endpoint**: Uses OpenAI Whisper to transcribe the guard’s voice input into JSON format containing:
     - Visitor Name
     - Purpose of Visit
     - Department
     - Phone Number

3. **Database**
   - Stores the parsed data (time, number plate, visitor details) for future reference.
   - Options: MongoDB or SQL, based on scalability and usage requirements.

### Setup Instructions
1. Clone the repository and install dependencies.
2. Configure the YOLO model for number plate detection.
3. Integrate OpenAI Whisper for speech-to-text transcription.
4. Set up and connect the database.
5. Test the complete workflow using sample data.

---

## Installation
### Prerequisites
- ESP32 Microcontroller
- Webcam
- Microphone
- Python Environment
- MongoDB/SQL Database
- use this to compress images `https://pngquant.org`

### Steps
1. Flash the ESP32 with the microcontroller logic.
2. Install and configure YOLO model for image processing.
3. Set up OpenAI Whisper for speech transcription.
4. Link APIs to the database.
5. Test the system end-to-end.

---

## Usage
1. Security guard presses a switch to initiate the data capture process.
2. Webcam captures the vehicle’s image.
3. Guard speaks visitor details into the microphone.
4. Image and audio data are sent to APIs and processed.
5. Parsed details are stored in the database.

---

## Future Improvements
- Implement facial recognition for visitor verification. 
- Enable SMS-based visitor verification. 
- Real-time monitoring dashboard for admin users.
- Maintain logs of vehicles still present in University grounds (i.e. maintain an exit log also)  

---

## Contributors
- **Team Members:**
  - Harshit Sharda
  - Kushagra Kumar



