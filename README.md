
# EV Battery Thermal Management System | MSc Project

## 📌 Motivation
Effective thermal management is **critical for EV battery performance, lifespan, and safety**.  
- Overheating reduces efficiency and can lead to safety issues.  
- Optimized cooling ensures stable operation under all load conditions.  

---

## 📈 Project Overview
This project focuses on designing, modeling, and testing a **liquid-based thermal management system** for EV battery packs.  

**Key Objectives:**  
1. Model the thermal behavior of a battery pack under various load scenarios.  
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
- Developed a **liquid-based cooling system model** in MATLAB/Simulink.  
- Simulated **temperature distribution** across battery cells under different load conditions.  
- Evaluated **heat dissipation efficiency** and **coolant flow rate** for optimization.  

---

## 🖼 Prototype & Testing
- Built a functional prototype of the battery pack cooling system.  
- Tested with:  
  - No cooling (baseline)  
  - Cold water cooling  
  - Normal water cooling  
- Validated simulation results against experimental measurements.  
<img width="733" height="550" alt="image" src="https://github.com/user-attachments/assets/5efa10c1-e1ae-4c08-a0c8-b40a293bfdce" />
 <img width="709" height="532" alt="image" src="https://github.com/user-attachments/assets/79911326-650d-43fa-86af-33b993c350d8" />
<img width="1000" height="600" alt="image" src="https://github.com/user-attachments/assets/ff18090f-92e9-4fd8-ad95-1d77ef5c167f" />

*Image: EV battery pack prototype with coolant channels and sensors.*

*Videos of  EV battery pack prototype with coolant channels and sensors.*

https://github.com/user-attachments/assets/6d847302-2fe0-49b8-ac21-eb34d3653ada

https://github.com/user-attachments/assets/4d01644a-1619-421b-b09d-4b3d05b08a70


---

## 📊 Results & Key Findings
- Cold water significantly reduces battery temperature rise compared to normal water or no cooling.  
- Simulations closely match prototype data, validating model accuracy.  
- Optimized coolant flow and channel layout improves thermal uniformity across cells.  

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
