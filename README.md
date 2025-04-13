# 🏠 Smart Kitchen Monitoring System  
**IoT-Based Safety Solution using ESP32**  

<div align="center">
  <img src="https://img.shields.io/badge/Microcontroller-ESP32-blue?logo=espressif">
  <img src="https://img.shields.io/badge/Protocol-IoT-green">
  <img src="https://img.shields.io/badge/Dashboard-ThingsBoard-yellow">
  <img src="https://img.shields.io/badge/Safety-Critical-red">
</div>

---

## 🎯 Objective  
Develop an intelligent kitchen monitoring system that:  
✅ Detects hazardous gas leaks, extreme temperatures, and humidity  
✅ Provides dual monitoring (local + remote) via ESP-Dash and ThingsBoard  
✅ Automatically cuts power to appliances during emergencies  
✅ Alerts users through multi-channel notifications  

---

## 📋 Project Description  
This ESP32-based system revolutionizes kitchen safety through:  

- **Real-time Monitoring**  
  - Tracks temperature (DHT11), humidity, and gas levels (MQ-135)  
  - Dual dashboard interfaces (local ESP-Dash + cloud ThingsBoard)  

- **Automated Safety Protocols**  
  - Triggers buzzer alarms when thresholds are exceeded  
  - Activates relay to disconnect appliances automatically  

- **Remote Accessibility**  
  - Local access via ESP-Dash (no internet required)  
  - Global monitoring through ThingsBoard cloud  

---

## 🛠️ Methodology  

### Hardware Components  
| Component | Purpose |  
|-----------|---------|  
| NodeMCU ESP32 | Main controller & WiFi interface |  
| DHT11 Sensor | Temperature/Humidity monitoring |  
| MQ-135 | Gas leak detection |  
| OLED Display | Local data visualization |  
| Relay Module | Appliance control |  
| Buzzer | Audible alarms |  

### Software Stack  
- **ESP-IDF** for firmware development  
- **ThingsBoard** for cloud analytics  
- **ESP-Dash** for local web interface  

---

## 🖼️ System Visualizations  

### 1. Circuit Design (Using EasyEDA Software)  
<div align="center">
  <img src="https://github.com/Deshan-Lokuge01/IoT-based-Kitchen-Monitoring-System/raw/main/Schemetic_Diagram.jpg" width="700" alt="Schematic Diagram">
</div>  

### 2. Physical Implementation  
<div align="center">
  <img src="https://github.com/Deshan-Lokuge01/IoT-based-Kitchen-Monitoring-System/raw/main/Full%20Fuctional%20System.jpg" width="700" alt="Deployed System">
</div>  

### 3. ESP-Dash Interface  
<div align="center">
  
  ![ESP-Dash](https://github.com/Deshan-Lokuge01/IoT-based-Kitchen-Monitoring-System/blob/main/ESP_dash_Dashboard_ASP_Device_act_as_Wifi.jpg)
</div>  

### 4. Cloud Monitoring (Udsing ThingsBoard Dashboard)  
<div align="center">
  <img src="https://github.com/Deshan-Lokuge01/IoT-based-Kitchen-Monitoring-System/raw/main/Web_Based_Monitoring_usingThingsBoard_Dashboard.jpg" width="700" alt="Cloud Dashboard">
</div>  

### 5. Complete System Working Overview  
<div align="center">
  <img src="https://github.com/Deshan-Lokuge01/IoT-based-Kitchen-Monitoring-System/raw/main/All_together.jpg" width="700" alt="Full System">
</div>  

---

## ⚙️ Working Principle  
1. **Sensor Data Acquisition**  
   - ESP32 polls DHT11 (temperature/humidity) and MQ-135 (gas) every 2 seconds  

2. **Threshold Analysis**  
   ```cpp
   if(gas_ppm > SAFE_LIMIT || temp > MAX_TEMP) {
     trigger_alarm();
     cut_power(); 
   }
