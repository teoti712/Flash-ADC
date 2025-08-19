# Flash ADC 3-bit Simulation (Cadence Virtuoso)

## 1. Abstract

### 1.1 Introduction to Flash ADC
- Flash ADC uses multiple opamps to compare the input signal with reference levels.  
- Two common encoder architectures:  

<p align="center">
  <img width="493" height="608" alt="image" src="https://github.com/user-attachments/assets/f986f70f-7c28-4414-8d01-353c366606aa" />
</p>
<p align="center"><i>Flash ADC using Priority encoder</i></p>  

<p align="center">
  <img width="614" height="646" alt="image" src="https://github.com/user-attachments/assets/80c12b1f-1264-4643-a7e7-da235a9bb3ae" />
</p>
<p align="center"><i>Flash ADC using Standard encoder + XNOR gates</i></p>  

<p align="center">
  <img width="1136" height="219" alt="FlashADC truth table" src="https://github.com/user-attachments/assets/d0b5517f-a892-42dc-a9d4-75fd8a64e278" />
</p>
<p align="center"><i>Expected output of 3 bit Flash ADC</i></p>  
---

### 1.2 Operational Amplifier (Op-amp)  

<p align="center">
  <img width="1303" height="664" alt="Opamp Schematic" src="https://github.com/user-attachments/assets/7fb30286-88e7-4f0c-b03d-edfc1dd03cdc" />
</p>
<p align="center"><i>Schematic of opamp view</i></p>  

<p align="center">
  <img width="981" height="615" alt="Transient response of opamp" src="https://github.com/user-attachments/assets/adca8c8f-9526-4799-8ade-3cfb394c9c26" />
</p>
<p align="center"><i>Output of opamp</i></p>  

---

### 1.3 Encoder
- **Standard Encoder**

<p align="center">
  <img width="750" height="227" alt="image" src="https://github.com/user-attachments/assets/8cdefe2f-61e9-46cb-a998-1e7e1591dc1b" />
</p>
<p align="center"><i>Truth table of 8-to-3 bit Encoder</i></p>  

<p align="center">
  <img width="633" height="401" alt="image" src="https://github.com/user-attachments/assets/b661e8c4-2bdc-4b2c-adba-092221391458" />
</p>
<p align="center"><i>8-to-3 bit Encoder schematic</i></p>  

---

- **Priority Encoder**

<p align="center">
  <img width="441" height="365" alt="image" src="https://github.com/user-attachments/assets/4dc423a6-02c0-40a9-a6c3-bb76f1a10805" />
</p>
<p align="center"><i>Truth table of 8-to-3 bit Priority Encoder</i></p>  

<p align="center">
  <img width="2561" height="1400" alt="prioritencoder" src="https://github.com/user-attachments/assets/60e371fe-3c6f-487f-89f0-2ae80f1bc44c" />
</p>
<p align="center"><i>Transistor-level schematic, zoom in for better view</i></p>  

<p align="center">
  <img width="1036" height="770" alt="image" src="https://github.com/user-attachments/assets/ffb5cc00-5848-4641-8a2b-82ea31efa4ed" />
</p>
<p align="center"><i>Equivalent gate-level circuit</i></p>  

---

### 1.4 Resistor Ladder
- Using voltage divider network to generate reference voltages (**Vref**) for the comparators in the Flash ADC.  

---

## 2. Simulation in Cadence Virtuoso
<p align="center"><img width="1720" height="709" alt="3 bit Flash ADC Schematic" src="https://github.com/user-attachments/assets/d112ff7d-e347-4821-90b0-cd8be91b8348" /></p>

### 2.1 Simulation Results
- Output waveforms obtained from simulation:  

<p align="center">
  <img width="984" height="615" alt="Output waveform" src="https://github.com/user-attachments/assets/64fe3ee4-013d-4858-938a-bb149728f198" />
</p>
<p align="center"><i>Output waveform, Vref = 2V and Vin is an ramping voltage that goes from 0V to 2V</i></p>  


---

### 2.2 Delay and Power Analysis
- **Delay:**  
  - When **Vref increases → delay decreases**.  
  - In CMOS circuits, a higher gate voltage increases the switching speed, which results in shorter propagation delay.  

- **Power consumption:**  
  - Measured and compared between standard and priority encoders.  

---
