# GPS Smart Vehicle Tracker – Complete Setup & Run Guide

## Project Overview

This project is a Flask-based GPS Smart Vehicle Tracker and Smart Toll System.
It includes:

* Vehicle registration system
* QR code generation for vehicles
* GPS route tracking
* Toll fare calculation
* Travel history storage
* Dashboard pages
* Google Maps integration
* SQLite database support
* Multiple simulation files for GPS tracking

Main technologies used:

* Python
* Flask
* SQLite
* HTML/CSS
* Google Maps API
* QR Code generation
* Razorpay integration

---

# Project Structure

```text
GPS_Smart_Vehicle_Tracker-main/
│
├── app.py                      # Main Flask application
├── app_1.py                    # Alternative app version
├── app_2.py
├── app_3.py
├── dashboard_app.py            # Dashboard related app
├── simulate_tracker.py         # GPS simulation
├── simulate_tracker_1.py
├── simulate_tracker_2.py
├── simulate_tracker3.py
│
├── requirements.txt            # Required Python packages
├── Dockerfile
├── docker-compose.yml
├── trip_log.csv
│
├── instance/
│   └── vehicles.db             # SQLite database
│
├── static/
│   ├── qr/
│   ├── qr_codes/
│   └── images
│
└── templates/
    ├── home.html
    ├── register.html
    ├── dashboard.html
    ├── map.html
    ├── history.html
    └── other HTML pages
```

---

# Software Requirements

Install the following before running the project:

## 1. Install Python

Recommended version:

```text
Python 3.10 or Python 3.11
```

Download:

* Python Official Website

While installing Python:

✔ Check:

```text
Add Python to PATH
```

---

## 2. Install VS Code

Download:

* Visual Studio Code Official Website

Install extensions:

* Python Extension
* Pylance

---

# Step-by-Step Project Setup

## Step 1 – Download the Project

### Option 1: Download ZIP

1. Open GitHub repository
2. Click:

```text
Code → Download ZIP
```

3. Extract the ZIP file

Example location:

```text
Desktop/GPS_Smart_Vehicle_Tracker-main
```

---

### Option 2: Clone Using Git

Open terminal:

```bash
git clone <repository_link>
```

Example:

```bash
git clone https://github.com/username/GPS_Smart_Vehicle_Tracker-main.git
```

---

# Step 2 – Open Project in VS Code

1. Open VS Code
2. Click:

```text
File → Open Folder
```

3. Select:

```text
GPS_Smart_Vehicle_Tracker-main
```

---

# Step 3 – Open Terminal in VS Code

In VS Code:

```text
Terminal → New Terminal
```

OR press:

```text
Ctrl + `
```

---

# Step 4 – Create Virtual Environment

Inside terminal run:

## Windows

```bash
python -m venv venv
```

If python command does not work:

```bash
py -m venv venv
```

This creates:

```text
venv/
```

which stores all project packages separately.

---

# Step 5 – Activate Virtual Environment

## Windows CMD

```bash
venv\Scripts\activate
```

## Windows PowerShell

```powershell
.\venv\Scripts\Activate.ps1
```

After activation you will see:

```text
(venv)
```

before terminal path.

Example:

```text
(venv) C:\Users\Name\Desktop\GPS_Smart_Vehicle_Tracker-main>
```

---

# Step 6 – Install Required Packages

Run:

```bash
pip install -r requirements.txt
```

This installs:

* Flask
* Google Maps API package
* QR code package
* Pillow
* Flask-SocketIO
* Requests
* Razorpay
* MongoDB packages
* Other dependencies

---

# IMPORTANT FIX – Missing Package

The project uses:

```python
from flask_sqlalchemy import SQLAlchemy
```

but `Flask-SQLAlchemy` is NOT present in requirements.txt.

Install it manually:

```bash
pip install flask-sqlalchemy
```

---

# Step 7 – Verify Installation

Run:

```bash
pip list
```

Check important packages:

```text
Flask
Flask-SQLAlchemy
qrcode
Pillow
googlemaps
requests
```

---

# Step 8 – Run the Main Application

Main file:

```text
app.py
```

Run:

```bash
python app.py
```

OR:

```bash
py app.py
```

---

# Step 9 – Open Browser

After running successfully you will see:

```text
Running on http://127.0.0.1:5000
```

Open browser and visit:

```text
http://127.0.0.1:5000
```

---

# Main Routes in the Project

## Home Page

```text
http://127.0.0.1:5000/
```

---

## Vehicle Registration

```text
http://127.0.0.1:5000/register
```

Used to:

* Register vehicle
* Store owner details
* Generate QR code

---

## Vehicle Tracking

Example:

```text
http://127.0.0.1:5000/track/KA01AB1234
```

This:

* Tracks vehicle route
* Calculates distance
* Detects highway route
* Calculates toll fare
* Stores travel history

---

## Vehicle List

```text
http://127.0.0.1:5000/vehicles
```

Displays all registered vehicles.

---

## History Page

```text
http://127.0.0.1:5000/history
```

Displays travel history.

---

# Database Information

Database used:

```text
SQLite
```

Database file:

```text
instance/vehicles.db
```

Tables created:

## RegisteredVehicle

Stores:

* Vehicle number
* Owner name
* Phone number
* Aadhar number
* QR code path

## TravelHistory

Stores:

* Start location
* End location
* Total distance
* Highway distance
* Toll fare
* Timestamp

---

# Google Maps API Setup

The project uses:

```python
googlemaps.Client(key="YOUR_API_KEY")
```

Inside `app.py` an API key is already present.

If API issues occur:

## Create Your Own API Key

1. Open Google Cloud Console
2. Create project
3. Enable:

```text
Maps JavaScript API
Directions API
Geocoding API
```

4. Generate API key
5. Replace inside:

```python
gmaps = googlemaps.Client(key="YOUR_API_KEY")
```

---

# QR Code Generation

QR codes are automatically generated during registration.

Generated QR codes are stored in:

```text
static/qr_codes/
```

Example:

```text
KA01AB1234.png
```

---

# Running GPS Simulation Files

The project contains multiple simulation files:

```text
simulate_tracker.py
simulate_tracker_1.py
simulate_tracker_2.py
simulate_tracker3.py
```

Run example:

```bash
python simulate_tracker.py
```

These files simulate:

* Vehicle movement
* GPS tracking
* Toll route simulation

---

# Running Dashboard Application

Dashboard file:

```text
dashboard_app.py
```

Run:

```bash
python dashboard_app.py
```

Then open browser using displayed URL.

---

# Docker Setup (Optional)

The project includes:

```text
Dockerfile
docker-compose.yml
```

## Install Docker

Download:

* Docker Desktop Official Website

---

## Build Docker Container

Run:

```bash
docker build -t gps-tracker .
```

---

## Run Docker Container

Run:

```bash
docker run -p 5000:5000 gps-tracker
```

Then open:

```text
http://localhost:5000
```

---

# Common Errors and Solutions

## Error 1 – Python Not Recognized

Error:

```text
python is not recognized
```

Solution:

Reinstall Python and check:

```text
Add Python to PATH
```

---

## Error 2 – No Module Named Flask

Solution:

```bash
pip install flask
```

---

## Error 3 – No Module Named flask_sqlalchemy

Solution:

```bash
pip install flask-sqlalchemy
```

---

## Error 4 – Port Already in Use

Solution:

Run using different port:

```python
app.run(port=5001)
```

Then open:

```text
http://127.0.0.1:5001
```

---

## Error 5 – Google Maps API Error

Possible reasons:

* Invalid API key
* API not enabled
* Billing not enabled

Solution:

Enable required APIs in Google Cloud Console.

---

# How the Project Works

## Step-by-Step Flow

### 1. User Registers Vehicle

User enters:

* Vehicle number
* Owner name
* Phone number
* Aadhar number

---

### 2. QR Code Generated

System creates QR code for vehicle.

---

### 3. Route Tracking Starts

System uses:

```text
Google Directions API
```

for finding route.

---

### 4. Highway Detection

Application checks road names:

```python
if any(x in road_name.lower() for x in ["highway", "expressway", "nh", "sh"])
```

---

### 5. Toll Fare Calculation

Formula:

```text
Fare = Highway Distance × 1.2
```

---

### 6. Travel History Stored

Trip data saved in SQLite database.

---

# Commands Summary

## Create Virtual Environment

```bash
python -m venv venv
```

## Activate Virtual Environment

```bash
venv\Scripts\activate
```

## Install Packages

```bash
pip install -r requirements.txt
pip install flask-sqlalchemy
```

## Run Main App

```bash
python app.py
```

## Run Dashboard

```bash
python dashboard_app.py
```

## Run Simulation

```bash
python simulate_tracker.py
```

---

# Recommended Improvements

Some improvements that can be added:

* Real-time GPS tracking
* Live map markers
* User login system
* UPI payment integration
* Admin dashboard
* Vehicle owner authentication
* AI-based traffic analysis
* Automatic toll deduction
* Mobile app support
* Real GPS hardware integration

---

# Final Notes

This project is a good mini-project for:

* Python Flask learning
* GPS-based applications
* Smart Toll Systems
* QR code systems
* Database management
* Google Maps API integration
* Smart transportation projects

It can also be extended into:

* Smart city projects
* IoT-based vehicle tracking
* AI traffic systems
* Automatic toll collection systems
