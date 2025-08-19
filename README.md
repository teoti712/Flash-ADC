# Flash ADC 3-bit Simulation (Cadence Virtuoso)

## 1. Abstract

### 1.1 Introduction to Flash ADC
- Flash ADC uses multiple opamps to compare the input signal with reference levels.  
- Two common encoder architectures:
  - **Flash ADC using Priority encoder** (more widely used):
 <img width="493" height="608" alt="image" src="https://github.com/user-attachments/assets/f986f70f-7c28-4414-8d01-353c366606aa" />

  
  - **Flash ADC using Standard encoder + XNOR gates** (less common):
 <img width="614" height="646" alt="image" src="https://github.com/user-attachments/assets/80c12b1f-1264-4643-a7e7-da235a9bb3ae" />

    

### 1.2 Operational Amplifier (Op-amp)  
  <img width="1303" height="664" alt="Opamp Schematic" src="https://github.com/user-attachments/assets/7fb30286-88e7-4f0c-b03d-edfc1dd03cdc" />
  <p align="center"><i>Schematic of opamp view</i></p> 

   <img width="981" height="615" alt="Transient response of opamp" src="https://github.com/user-attachments/assets/adca8c8f-9526-4799-8ade-3cfb394c9c26" />
   <p align="center"><i>Output of opamp</i></p> 


### 1.3 Encoder
- **Standard Encoder**
  
  <img width="633" height="401" alt="image" src="https://github.com/user-attachments/assets/b661e8c4-2bdc-4b2c-adba-092221391458" />

  - Waveform.  
  - Delay.  
  - Power.  

- **Priority Encoder**

  <img width="2561" height="1400" alt="prioritencoder" src="https://github.com/user-attachments/assets/60e371fe-3c6f-487f-89f0-2ae80f1bc44c" />
  <p align="center"><i>Transistor-level schematic, you can zoom in for better view</i></p> 


  <img width="1036" height="770" alt="image" src="https://github.com/user-attachments/assets/ffb5cc00-5848-4641-8a2b-82ea31efa4ed" />
  <p align="center"><i>Equivalent gate-level circuit</i></p> 

  - Waveform.  
  - Delay.  
  - Power.  

### 1.4 Resistor Ladder
- Used to generate reference voltages (**Vref**) for the comparators in the Flash ADC.  

---

## 2. Simulation in Cadence Virtuoso

### 2.1 Simulation Results
- Output waveforms obtained from simulation:  

📷 **Op-amp waveform**  
![Opamp waveform](results/opamp_waveform.png)  

📷 **Standard Encoder waveform**  
![Encoder waveform](results/encoder_normal.png)  

📷 **Priority Encoder waveform**  
![Priority encoder waveform](results/encoder_priority.png)  

### 2.2 Delay and Power Analysis
- **Delay:**  
  - When **Vref increases → delay decreases** In CMOS circuits, a higher gate voltage increases the switching speed, which results in shorter propagation delay.
- **Power consumption:**  
  - Measured and compared between standard and priority encoders.  

---

