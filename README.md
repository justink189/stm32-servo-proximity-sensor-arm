STM32 High-Speed Dual-Servo Ultrasonic Scanner & Proximity Radar


An advanced embedded systems project built on STM32CubeIDE using native C and hardware abstraction layers (HAL). This project implements an automated, high-speed dual-servo scanning pan/tilt mechanism combined with an HC-SR04 ultrasonic sensor, a 4-bit parallel 16x2 LCD for live telemetry, and a gated active buzzer security alert system.
🚀 Key Features
High-Speed Aggressive Sweeping: Custom-tuned servo sweep parameters configured for rapid target acquisition (60 
∘
  pan step, 45 
∘
  tilt step, with a tight 2ms delay loop).
Real-Time Distance Radar: Continuous distance calculation using an HC-SR04 ultrasonic sensor interfaced with precise microsecond timing.
Gated Proximity Alert: An active buzzer safety feature that remains completely silent during normal scans and triggers instantly only when an object breaches the strict 0–25 cm range.
Local Telemetry Display: Real-time system status and distance values streamed directly to a 4-bit parallel 16x2 LCD screen.
pin_m_pinout Pinout & Hardware Configuration
Component	Sub-Component / Function	STM32 Pin Assignment
Pan Servo	TIM2 Channel 1 (PWM)	PA0
Tilt Servo	TIM2 Channel 2 (PWM)	PA1
HC-SR04 Sensor	Trigger Pin	PA9
HC-SR04 Sensor	Echo Pin	PC7
Active Buzzer	Positive Terminal (+)	PA4 (A2)
Active Buzzer	Negative Terminal (-)	GND
16x2 LCD Display	Register Select (RS)	PA10
16x2 LCD Display	Enable (E)	PB3
16x2 LCD Display	Data Line D4	PB5
16x2 LCD Display	Data Line D5	PB4
16x2 LCD Display	Data Line D6	PB10
16x2 LCD Display	Data Line D7	PA8
🛠️ Technical Specifications & Architecture
Microcontroller: STM32 (ARM Cortex-M based development board)
IDE & Toolchain: STM32CubeIDE with STM32CubeMX Peripheral Configuration
PWM Generation: Utilizes TIM2 (Channels 1 and 2) configured to output standard servo control signals (50Hz frequency base with dynamic pulse-width modulation).
Proximity Threshold Logic:
State={ 
Alarm Active (Buzzer ON),
Silent (Buzzer OFF),
​	
  
if 0 cm≤Distance≤25 cm
otherwise
​	
 
📂 Project Structure
Plaintext
stm32-pan-tilt-scanner/
├── Core/
│   ├── Inc/          # Header files (main.h, lcd.h, etc.)
│   └── Src/          # Source files (main.c, stm32_hal_msp.c, etc.)
├── Drivers/          # STM32 HAL and CMSIS drivers
├── .gitignore        # Ignored build and binary files
└── README.md         # Project documentation
💻 Getting Started
Prerequisites
STM32CubeIDE installed on your macOS/Windows/Linux machine.
An ST-Link programmer or USB connection to your STM32 development board.
Installation & Flashing
Clone or Download this repository to your local machine.
Open STM32CubeIDE and select File > Import > Existing Projects into Workspace.
Browse to the folder containing this repository and click Finish.
Build the project (Ctrl+B or hammer icon) to ensure all dependencies compile cleanly.
Connect your STM32 board via USB, click Run > Run Debug, and flash the binary onto the MCU.
