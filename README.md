
# EV Battery Thermal Management System | MSc Project

## 📌 Motivation
Effective thermal management is **critical for EV battery performance, lifespan, and safety**.  
- Overheating reduces efficiency and can lead to safety issues.  
- Optimized cooling ensures stable operation under all load conditions.  

---

## 📈 Project Overview
This project focuses on designing, modeling, and testing on **battety temperatureof a Li-oin battery with and without cooling with ethyl-glycol and water mix liquid-based thermal management system** for EV battery packs.  

**Key Objectives:**  
1. Model the thermal behavior of a Li-ion battery pack under various load scenarios.  
2. Simulate heat dissipation and coolant flow using MATLAB/Simulink.  
3. Prototype and validate cooling strategies with different coolant conditions.  

---

## 🔧 Tools & Technologies
- **MATLAB/Simulink** – Thermal modeling & simulation  
- **Proteus** – Prototype electronics simulation  
- **Arduino IDE & C** – Microcontroller integration for sensors & data acquisition  
- **Cold Water & Normal Water Tests** – Prototype validation  

---

## 🛠 Modeling & Simulation
- Developed a **liquid-based cooling system model with ethyl-glyol and water mix** in MATLAB/Simulink.  
- Simulated **temperature distribution** across battery cells under different load conditions.  
- Evaluated **heat dissipation efficiency** and **coolant flow rate** for optimization.
  
 <img width="1243" height="696" alt="Screenshot 2026-03-07 150440" src="https://github.com/user-attachments/assets/f5245cbe-aefa-49df-a579-7951ff6ef5fd" />
 
 <img width="1651" height="708" alt="Screenshot 2026-03-07 150451" src="https://github.com/user-attachments/assets/9fa7c7d2-6a1e-40a0-8a4c-7740dd182fac" />

 <img width="1755" height="702" alt="Screenshot 2026-03-07 150502" src="https://github.com/user-attachments/assets/cdb38024-16b6-4ed5-b052-7614ead3f215" />

**Battey pack without cooling**

<img width="1908" height="761" alt="Screenshot 2026-03-08 203230" src="https://github.com/user-attachments/assets/1f5b3cab-3370-47d8-a793-e52f24de5719" />


---


## 🛠 Simulation Results

<img width="754" height="659" alt="Screenshot 2026-03-08 203248" src="https://github.com/user-attachments/assets/bf707f7d-3447-4848-93c7-79c2ef84ac1b" />

<img width="799" height="704" alt="Screenshot 2026-03-07 150530" src="https://github.com/user-attachments/assets/e8dde340-bdc2-483b-97b3-81e3e45a861b" />

 <img width="1800" height="712" alt="Screenshot 2026-03-07 150543" src="https://github.com/user-attachments/assets/e5a182a6-4863-42b2-b26f-0026aade3a15" />

---

## 🖼 Prototype & Testing
- Built a functional prototype of the battery pack cooling system.  
- Tested with:  
  - No cooling (baseline)  
  - Cold water cooling  
  - Normal water cooling  
- Validated simulation results against experimental measurements.

---

## Componets used 
- Arduino Uno 
- TMP 36  
- Battery
- Motor pump to drive the water
- Pipes
- LCD for display
![WhatsApp Image 2026-03-07 at 14 30 01](https://github.com/user-attachments/assets/f5fecf6b-eb1e-40c9-a1eb-689011d03d66)
![WhatsApp Image 2026-03-07 at 14 29 23](https://github.com/user-attachments/assets/b51272dc-caa6-4e5c-aad3-2d14361203f3)
![WhatsApp Image 2026-03-07 at 14 29 40](https://github.com/user-attachments/assets/d7d306e0-2a37-44f3-9d80-33d943e1ab6b)
![WhatsApp Image 2026-02-10 at 07 15 42](https://github.com/user-attachments/assets/1e315a22-76a9-40ba-ac88-8e84e84146b8)

---

## Prototpe Flowchart

## System Without Cooling
<img width="542" height="722" alt="battery temp without cooling" src="https://github.com/user-attachments/assets/8eeb2fa5-a0e7-4e47-a652-d04ff1848122" />

## System With Cooling
<img width="927" height="1544" alt="battery temp with cooling" src="https://github.com/user-attachments/assets/7adea0da-c5bf-4cf4-b504-a5bd9d8c660b" />

---


## 🖼 Prototype & Testing Results
  
<img width="733" height="550" alt="image" src="https://github.com/user-attachments/assets/5efa10c1-e1ae-4c08-a0c8-b40a293bfdce" />
 <img width="709" height="532" alt="image" src="https://github.com/user-attachments/assets/79911326-650d-43fa-86af-33b993c350d8" />
<img width="1000" height="600" alt="image" src="https://github.com/user-attachments/assets/ff18090f-92e9-4fd8-ad95-1d77ef5c167f" />

*Image: EV battery pack prototype with coolant channels and sensors.*

https://github.com/user-attachments/assets/6d847302-2fe0-49b8-ac21-eb34d3653ada

https://github.com/user-attachments/assets/4d01644a-1619-421b-b09d-4b3d05b08a70

*Videos of  EV battery pack prototype with coolant channels and sensors.*

---

## 📊 Key Results / Project Impact

- Conducted an in-depth analysis of temperature variation effects on electric vehicle battery performance and evaluated the effectiveness of an active liquid cooling         system.
- Designed and implemented a cold-plate liquid cooling architecture for EV battery modules to regulate temperature distribution and improve thermal stability.
- Achieved a ~15% reduction in peak battery cell temperature, improving safety, efficiency, and operational reliability of the battery pack.
- Validated the system through comparative testing of different cooling configurations, demonstrating improved thermal performance over conventional water-only cooling       methods.

---

## 🚀 Outcomes & Skills
- EV battery thermal modeling and simulation  
- Liquid cooling system design and prototype testing  
- MATLAB/Simulink and Arduino-based data acquisition  
- Experimental validation of simulation results  

---

## 🚀 Future Scope

- Advanced Thermal Modeling: Use more detailed battery cell thermal models in MATLAB/Simulink for realistic simulations.
- IoT Dashboard Integration: Stream live battery temperatures to a mobile or web dashboard for remote monitoring.
- Multiple Sensor Network: Monitor each battery cell individually for precise thermal management.
- Machine Learning for Predictive Cooling: Predict overheating events and optimize fan control proactively.
- Hardware Implementation: Build a functional prototype with real battery packs, fans, and LCD/IoT display.
- Energy Efficiency Optimization: Develop algorithms to minimize cooling energy while keeping battery temperatures safe.
  
---

## 💻 Codes
#include <LiquidCrystal.h> 
const int rs = 12; // NOTE: Change this if using the Motor Shield from Code 1!
const int en = 11; 
const int d4 = 5;
const int d5 = 4; 
const int d6 = 3;  // NOTE: Change this if using the Motor Shield from Code 1!
const int d7 = 2; 
LiquidCrystal lcd(rs, en, d4, d5, d6, d7); 
float current = 0; 
float temp = 0;    // Changed to float for accurate calculation
float current1 = 0; 
float temp1 = 0;   // Changed to float for accurate calculation
void setup() {   
  lcd.begin(16, 2);   
  Serial.begin(9600);  
  pinMode(6, OUTPUT); 
} 
void loop() {   
  String data = "";   
  
  // ----- Reading Battery 1 -----
  current = analogRead(A2) - 432; 
  current = current * 0.091;  // Fixed the 'l' typo to '1'
  
  // Correct TMP36 Temperature Math (5V Arduino)
  temp = analogRead(A0);  
  temp = (temp * 4.88);       // Convert ADC reading to millivolts
  temp = (temp - 500) / 10.0; // Subtract 500mV offset, then divide by 10mV/degree C
  // ----- Reading Battery 2 -----
  current1 = analogRead(A3) - 434;
  current1 = (current1 * 0.091) / 2.0;  
  
  // Correct TMP36 Temperature Math (5V Arduino)
  temp1 = analogRead(A1);   
  temp1 = (temp1 * 4.88);   
  temp1 = (temp1 - 500) / 10.0; 
  // ----- Printing to LCD -----
  lcd.setCursor(0, 0);  
  lcd.print("B-1 T:");  
  lcd.print((int)temp);    // Cast to int here just to avoid decimal overflow on LCD screen
  lcd.setCursor(9, 0); 
  lcd.print("A:"); 
  lcd.print(current, 1);   // Print with 1 decimal place
  
  lcd.setCursor(0, 1);  
  lcd.print("B-2 T:");  
  lcd.print((int)temp1);  
  lcd.setCursor(9, 1);  
  lcd.print("A:");   
  lcd.print(current1, 1);  
  
  // ----- Motor / Cooling Logic -----
  if(temp > 35) {     
    analogWrite(6, 255);  // Max speed when very hot
  }  
  else if(temp > 32) {     
    analogWrite(6, 200);  // Medium speed when getting hot
  }
  else {
    analogWrite(6, 0);    // TURN OFF the pump when temp is safe (<= 32)
  } 
  // ----- Sending Data to Serial Monitor -----
  // Adding spaces so the data doesn't squish into one giant unreadable number
  data = String(temp) + "," + String(current) + "," + String(temp1) + "," + String(current1);  
  Serial.println(data);   
  
  delay(1000);  
}
