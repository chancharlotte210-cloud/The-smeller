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
