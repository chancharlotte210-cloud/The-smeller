# The-smeller
  A compact, DIY air quality monitoring system that tracks volatile organic compounds (VOCs) and estimated CO₂ levels in your home or workspace.
	
<img width="256" height="283" alt="Screenshot 2026-06-19 084358" src="https://github.com/user-attachments/assets/0cbc8c69-49a9-4b54-8303-0481cd870002" />

What It Is
  This is a portable air quality monitor built around an ESP32 microcontroller. It uses the Sensirion SGP30 sensor to measure:
  
  TVOC (Total Volatile Organic Compounds) – in parts per billion (ppb)
  
  eCO₂ (equivalent Carbon Dioxide) – in parts per million (ppm)

All readings are displayed in real-time on a 0.96-inch OLED screen. The device also provides a visual quality bar and text-based status (Excellent → Very Poor) so you can instantly understand your air quality at a glance.
<img width="2067" height="2060" alt="IMG_9690" src="https://github.com/user-attachments/assets/90ae2e22-0a97-4653-a984-fc73329c7acb" />
Why I Built It
I was concerned about the air quality in my home office but didn't want to spend $100+ on a commercial monitor. Plus, I am super interested in environmental science. Right now my viggest in the sustainable communities air quality part of it.

Feature	Description
  Real-time monitoring,
  TVOC measurement,
  CO₂ estimation,
  OLED display,
  Visual quality bar,
  Status text:	EXCELLENT, GOOD, MODERATE, POOR, or VERY POOR

Status Indicators
TVOC (ppb)	Status	Color
0 – 249	EXCELLENT	🟢 Green
250 – 499	GOOD	🟢 Green
500 – 999	MODERATE	🟡 Yellow
1000 – 1999	POOR	🟠 Orange
2000+	VERY POOR	🔴 Red

How to Build It:
Install Arduino IDE, add ESP32 board support (URL: https://dl.espressif.com/dl/package_esp32_index.json), and install three libraries: Adafruit SSD1306, Adafruit GFX, and Adafruit SGP30.
Wire the OLED display to the ESP32: VDD→3.3V, VSS→GND, SDA→GPIO21, SCL→GPIO22.
Wire the SGP30 sensor in parallel with the OLED: VCC→3.3V, GND→GND, SDA→GPIO21, SCL→GPIO22 (both sensors share the same I²C pins).
Run the I2C scanner sketch to confirm your ESP32 detects the OLED at 0x3C (or 0x3D) and the SGP30 at 0x58.
Copy the combined code (from the previous reply) into Arduino IDE – it reads both sensors and displays VOC (ppb) and eCO₂ (ppm) on the OLED.
Select your board: Go to Tools → Board → ESP32 Arduino → DOIT ESP32 DEVKIT V1, then select the correct COM port.
Upload the code by clicking the right-arrow button – wait for "Done uploading" in the status bar.
Open the Serial Monitor at 115200 baud to see debug output and verify readings appear every 2 seconds.
Test the monitor: Wait 3–5 minutes for the sensor to stabilize, then try opening a window or spraying a tiny amount of air freshener nearby – you should see VOC levels change.
Add a status indicator (optional) – the code already includes a quality bar and text status (Excellent → Very Poor) on the OLED.

Testing Your Monitor
Place it in a room and wait 3-5 minutes for stabilization

Open a window – you should see VOC levels drop

Spray a tiny amount of air freshener nearby – watch VOCs spike

Close the room – CO₂ will slowly rise
