# LED-BLINK
# 💡 Experiment 01 – Interfacing a Digital Output (LED) with ARM Development Board

### 🎯 **Aim**
To interface a digital output (LED) to an ARM development board and write a blink code.

---

### ⚙️ **Components Required**
- STM32CubeIDE  
- NUCLEO ARM Development Board  

---

### 🧠 **Theory**

**ARM (Advanced RISC Machine)** is a 32-bit processor architecture developed by ARM Holdings. It is widely used in embedded systems and SoC (System-on-Chip) products. Many semiconductor companies like Samsung, Atmel, and Texas Instruments license ARM architecture to design their own SoCs.
### 🧩 **What is an ARM7 Processor?**
The **ARM7 processor** is commonly used in embedded system applications. It provides a balance between the classic ARM architecture and the newer Cortex series, offering an excellent platform for both hardware and software development.
### 🔍 **LPC2148 Microcontroller**
The **LPC2148**, developed by NXP Semiconductors (Philips), is a 16/32-bit ARM7-based microcontroller featuring a wide range of peripherals.
#### **Key Features**
- 16/32-bit ARM7TDMI-S core in LQFP64 package  
- On-chip **Flash memory**: 32 KB – 512 KB  
- On-chip **SRAM**: 8 KB – 40 KB  
- **ISP/IAP** via on-chip bootloader  
- **Embedded ICE-RT** and **Real Monitor** for real-time debugging  
- **USB 2.0** full-speed device controller with 2 KB endpoint RAM  
- **10-bit ADC** (6 or 14 channels, 2.44 μs conversion time)  
- **10-bit DAC** for analog output  
- **Timers:** Two 32-bit timers, watchdog, and PWM unit  
- **RTC** with 32 kHz clock input  
- **UARTs (2x), I²C (2x)** up to 400 kbit/s  
- **5V-tolerant GPIOs**, 21 external interrupt pins  
- **Max CPU Clock:** 60 MHz using on-chip PLL (lock time 100 µs)  
- **Crystal Frequency:** 1 MHz – 25 MHz  
- **Power modes:** Idle and Power-down with peripheral clock scaling  

---

### 🧭 **Procedure**

1. Open **STM32CubeIDE**.
   <img width="1920" height="1200" alt="Screenshot (66)" src="https://github.com/user-attachments/assets/8c5034fd-aeb1-49e8-b241-7ebecbed6e9d" />


2. Click **File → New STM32 Project**.
   <img width="1920" height="1200" alt="Screenshot (67)" src="https://github.com/user-attachments/assets/6b0d3cc2-c48e-4ef4-9ff9-f97155bfbc66" />

3. Select the **target microcontroller** or board and click **Next**.
  <img width="738" height="651" alt="Screenshot 2025-10-29 233753" src="https://github.com/user-attachments/assets/9633638b-6b2b-40f3-ba22-a967b4db314d" />


4. Name the project.
   <img width="960" height="692" alt="Screenshot 2025-10-29 234554" src="https://github.com/user-attachments/assets/16a3d3f1-0424-4c94-bd9e-3535606cd5e0" />

5. The corresponding `.ioc` file will be generated automatically.
  <img width="1919" height="1130" alt="Screenshot 2025-10-27 205504" src="https://github.com/user-attachments/assets/3704ab54-744b-4431-8c8e-e3e50f25c9f8" />

6. Configure the pins as **GPIO (Input/Output)**, **USART**, etc. as needed.
   <img width="1918" height="1199" alt="Screenshot 2025-10-29 233539" src="https://github.com/user-attachments/assets/726cae0d-41a5-4381-9b44-7c1f5ac3cc4a" />

7. Save the configuration (`Ctrl + S`) – the base C program will be generated automatically.
   <img width="1919" height="1130" alt="Screenshot 2025-10-27 205504" src="https://github.com/user-attachments/assets/4144d2d4-40de-4934-a24f-aff94e0d8de3" />

8. Edit the generated main program as required.
   <img width="1000" height="551" alt="Screenshot 2025-10-29 233359" src="https://github.com/user-attachments/assets/8b0fa3da-bb86-4891-814a-9dfca5e98312" />
<img width="1919" height="1198" alt="Screenshot 2025-10-29 233611" src="https://github.com/user-attachments/assets/f72d6939-6c81-44de-9ada-5efe2af10de6" />


9. Click **Project → Build All**.
   <img width="1917" height="1199" alt="Screenshot 2025-10-29 233953" src="https://github.com/user-attachments/assets/7bee22e6-8551-4258-9786-b7f6f8ad4b6f" />

10. Link the **HEX file** using the post-build process.
    <img width="1240" height="529" alt="Screenshot 2025-10-27 210155" src="https://github.com/user-attachments/assets/cb98d306-3a07-4286-ac4f-44b6e2b016b8" />

11. Click **Debug** and connect the **STM Nucleo Board**.
   <img width="1917" height="1199" alt="Screenshot 2025-10-29 233953" src="https://github.com/user-attachments/assets/ab3b1f60-7415-47ba-9c20-3d06a7298542" />


13. Click **Run** to execute the program.
    
---

### 💻 **Program**


```c
#include "main.h"

void SystemClock_Config(void);
static void MX_GPIO_Init(void);

int main(void)
{
    HAL_Init();
    SystemClock_Config();
    MX_GPIO_Init();

    while (1)
    {
        HAL_GPIO_WritePin(GPIOA, GPIO_PIN_5, GPIO_PIN_RESET);
        HAL_Delay(1000);
        HAL_GPIO_WritePin(GPIOA, GPIO_PIN_5, GPIO_PIN_SET);
        HAL_Delay(1000);
    }
}
```
---
### OUTPUT
CASE 1: LED ON 
![WhatsApp Image 2025-10-29 at 23 59 49_fc4fbd39](https://github.com/user-attachments/assets/46bfe003-2340-4c4c-8321-99ad101e6216)

CASE 2: LED OFF
<img width="670" height="307" alt="Screenshot 2025-10-29 234651" src="https://github.com/user-attachments/assets/51ec65f1-feca-43e9-bfee-8d0963ccf22e" />

---
### RESULT
Interfacing a digital output with ARM microcontroller is executed and the results are verified.
