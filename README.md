I designed a working simple STM32 devboard to learn how to use KiCad and design my own PCBs

MCU is a genuine STM32F103C8T6. I'll upload an STM32CubeIDE project soon, planning to also put an libopenCM3 project here. For the programming you'll need a standard ST-LINK programmer (A fake one might be working just fine). The PCB exposes a programming interface with SWD, CLK, +3V3 and GND and BOOT0 with Breakers. 

For the programming

    st-flash write firmware.bin 0x08000000 
    
works fine for me

![top](https://github.com/user-attachments/assets/e19aae01-03c7-4d29-b51e-54648cb7e8de)
![stm32_board.jpg](https://github.com/zeppel13/stm32f103-bluepill/blob/main/stm32_board.jpg)

![screenshot_1726694269](https://github.com/user-attachments/assets/e5d516eb-f842-4bdd-8c65-febf3918eaec)


![screenshot_1726694248](https://github.com/user-attachments/assets/96cd7314-0e7c-44ab-a03c-a56d2d821ed3)

![screenshot_1726694252](https://github.com/user-attachments/assets/f730eb22-93fc-4c08-8184-211b553492ba)


### Goals of the Project
✅ **Learn to use KiCAD**  
✅ Complete all necessary steps to manufacture the board and proceed with prototypes  
✅ Create a Blue Pill-compatible board with a genuine STM32F103 (no clones like GD32, PY32, etc.)  
✅ Provide a base for future MCU PCB design  
✅ Ensure the PCB fits on a breadboard  
✅ Pay special attention to the routing of high-frequency signals: proper differential pairs for USB, a good ground plane, and always low-impedance return paths  
✅ Make it work  

---

### Non-Goals
- Using the newest or best features. STM32F103 might seem a bit outdated compared to newer STM32 offerings. A brand-name Micro USB-B connector will be used — no USB-C.  
- Power optimization (e.g., removing LEDs, using a more efficient voltage supply, or selecting a low-power MCU).  
- Price optimization. The plan is to build a small batch, not large quantities.  

---

### Errata
- The **BOOTP** header in the silkscreen should be **BOOT0**. I confused the technical jargon of Cortex boot modes with DHCP/BOOTP and didn’t realize the mistake until after producing the samples.  
- The SMD switch for BOOT0 was replaced with a pinout that can be configured with jumpers (HI/LOW).  
