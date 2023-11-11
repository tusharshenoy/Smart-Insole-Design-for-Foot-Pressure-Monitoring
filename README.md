# Foot-Pressure-Monitoring-System

### Title: Smart Insole Design for Foot Pressure Monitoring
### 1. Abstract
   The project `"Smart Insole Design for Foot Pressure Monitoring"` introduces an innovative and cost-effective system designed to continuously monitor foot pressure using `capacitive sensors` embedded within an insole. Foot pressure monitoring is crucial for diagnosing conditions like diabetic neuropathy, plantar fasciitis, and peripheral vascular diseases. Existing monitoring techniques are limited in their capacity for prolonged use and can be costly, hindering widespread adoption.

The proposed system utilizes an array of capacitive sensors made from copper foil, enabling real-time monitoring of foot pressure. These sensors are strategically arranged across the insole to cover critical areas susceptible to deformities, facilitating the detection and analysis of pressure distribution. Data collected from these sensors is processed using a `Raspberry Pi Pico microprocessor`, which applies an algorithm to determine pressure distribution, identify potential deformity-prone areas, and transmit the findings to a monitoring device.

Experimental testing involved a group of volunteers, providing insights into foot pressure characteristics among individuals with different foot conditions. The system displayed the ability to visualize foot pressure variations through a color-coded map, indicating areas of high, moderate, and low pressure.

The project's novel approach using affordable, capacitive sensors in a wearable insole, along with the ability to process and visualize pressure data in real-time, distinguishes it from existing monitoring systems. The documentation includes detailed descriptions of sensor selection, arrangement, data processing, experimental results, and a comparative analysis with similar existing models. Additionally, the documentation aims to provide a basis for further enhancements and improvements to the system.

### 2. Introduction
#### Introduction to Foot Pressure Monitoring
Foot pressure monitoring plays a crucial role in `evaluating foot health`, providing significant insights into `gait kinematics`, `ground reaction forces`, and identifying various foot conditions. It is essential for medical diagnostics, enabling differentiation between normal and pathological foot conditions. This monitoring method is pivotal in diagnosing and tracking medical conditions such as `diabetic neuropathy`, `plantar fasciitis`, and `peripheral vascular diseases`. Early detection is vital for effective treatment, making foot pressure monitoring a valuable tool in this context.

### Importance and Applications
The significance of foot pressure monitoring extends to various beneficiaries and applications. It aids in diagnosing foot deformities and prevents diabetic ulcers, benefiting individuals with existing foot conditions. It plays a critical role in the proactive management of diabetic patients, minimizing the risk of ulcers and amputations. Athletes use it to optimize performance and prevent injuries. Healthcare professionals benefit from enhanced diagnostic capabilities, and researchers contribute to advancements in gait analysis and foot function. Overall, foot pressure monitoring addresses specific conditions while also contributing to overall foot health and performance optimization.

### Current Technologies and Limitations
Present technologies for foot pressure monitoring include in-shoe pressure sensors, pressure mats, and force plates using various sensors like `Force Sensing Resistors (FSRs)`, `Capacitive Sensors`, and `Piezoelectric Sensors`. However, these techniques have limitations concerning prolonged daily use and cost, hindering their widespread adoption. Existing systems often involve complex procedures, making them less suitable for continuous and affordable monitoring.

### Purpose and Innovation of the Proposed System
The proposed system introduces an innovative, affordable solution using an insole embedded with an array of capacitive sensors specifically designed for `continuous foot pressure monitoring`. It addresses the limitations of current systems by providing real-time, dynamic monitoring of foot pressure in individuals. The system comprises capacitive sensors made from `copper foil`, strategically arranged across the insole to cover crucial foot areas susceptible to deformities. By using a Raspberry Pi Pico microprocessor, the system processes and analyzes the gathered data, enabling early warnings regarding changes in foot pressure for individuals at high risk of medical conditions. The innovation lies in the cost-effectiveness, real-time monitoring capability, and wearability of the proposed insole system.

### 3. Methodology
### Overview of the System Blocks (Sensor Array, Microprocessor, Monitoring Device)
The proposed smart footwear system comprises three main blocks:
- **Sensor Array:** Utilizes an array of capacitive sensors made from copper foil strategically arranged on the insole. It covers various foot areas prone to deformities, enabling continuous monitoring of foot pressure.
- **Microprocessor:** Employs a Raspberry Pi Pico for data processing and analysis. It reads the data from the sensor array via an analogue multiplexer, processes the information using suitable algorithms, and transmits the processed data for monitoring.
- **Monitoring Device:** This device (e.g., a laptop or mobile phone) is used to monitor and display the analyzed foot pressure data obtained from the microprocessor.

  ![image](https://github.com/tusharshenoy/Foot-Pressure-Monitoring-System/assets/107348474/3b816d16-2383-4992-9aa1-4db95ad47b91)


### Detailed Description of Sensor Selection
The proposed pressure sensor uses a `capacitive sensing mechanism designed with thin copper foil` due to its `conductive properties` and availability. The active plate, responsible for sensing changes in capacitance, is divided into `16 individual circular segments`, `ensuring precise measurements` and `reducing interference from adjacent regions`. These segments are `strategically positioned` across the insole to cover the `heels, toes, and mid-foot regions`. A `reference/common plate` and a `dielectric layer` made of plastic foam separate the active plates, providing a baseline capacitance and compensating for environmental factors influencing measurements.

![image](https://github.com/tusharshenoy/Foot-Pressure-Monitoring-System/assets/107348474/f7354964-6f3b-4cce-9a23-50a62dc7570f) ![image](https://github.com/tusharshenoy/Foot-Pressure-Monitoring-System/assets/107348474/a254e41c-274d-4f23-bbee-dbfb93d87a03)

#### Structure of sensors:aluminium  


![image](https://github.com/tusharshenoy/Foot-Pressure-Monitoring-System/assets/107348474/4626baa0-7a36-4019-a793-c397fee1d854) ![image](https://github.com/tusharshenoy/Foot-Pressure-Monitoring-System/assets/107348474/17b2d083-1763-49ce-86ed-ca0dee5d7139)

#### Structure of sensors:copper

### Sensor Arrangement on the Insole
The sensors are strategically placed on the insole to cover critical areas prone to foot deformities. Six sensors cover the heel, six cover the toes, and four cover the mid-foot area. The sensor arrangement involves connecting all active plates to the Raspberry Pi Pico through a 16-pin analogue multiplexer, allowing the microprocessor to read the analogue voltage at the respective active plates.

![image](https://github.com/tusharshenoy/Foot-Pressure-Monitoring-System/assets/107348474/48b90966-e726-4ac2-91e1-d628ac82a976)

#### Arrangement of the sensors on a sheet of polyethylene foam

![image](https://github.com/tusharshenoy/Foot-Pressure-Monitoring-System/assets/107348474/735acc45-9f77-456d-9a38-3a42a02b224d)

#### The setup of the prototype

![image](https://github.com/tusharshenoy/Foot-Pressure-Monitoring-System/assets/107348474/037a046c-ffea-4bdc-b73d-0343db23120a) 
#### Result of 10 test subjects 

![image](https://github.com/tusharshenoy/Foot-Pressure-Monitoring-System/assets/107348474/96cd76d0-fc15-4002-adfb-94bd3311a3db)
#### Healthy foot vs Deformed foot

### Data Processing Workflow
The `Raspberry Pi Pico` reads the voltage from each sensor through the `analogue multiplexer` and processes the data. It collects voltage readings `128 times` within 2 seconds, discarding initial and final readings to avoid noise. A `filtering algorithm` calculates the average of the remaining 64 values for each sensor. This process is repeated 10 times to obtain a 16x10 matrix. The resulting average values enhance accuracy. The processed data is visualized and transmitted to a monitoring device for real-time analysis.

This systematic approach of sensor selection, arrangement, and data processing ensures comprehensive foot pressure monitoring, enabling early detection and continuous surveillance of foot conditions.

![image](https://github.com/tusharshenoy/Foot-Pressure-Monitoring-System/assets/107348474/02ce5ddd-3638-47b4-8a3a-f454c7f4a07a)

#### Plot of voltages obtained from the respective sensors

![image](https://github.com/tusharshenoy/Foot-Pressure-Monitoring-System/assets/107348474/04e4cbd6-2b4d-4d0a-98a0-56e5f0bdf03f)

#### The setup of the prototype

### 4. Experimental Results
  ### Details of Testing with Volunteer Participants
The prototype underwent testing involving `10 volunteers aged between 19 and 45`, weighing between `50Kgs and 72Kgs`. The experimental tests involved `recording the corresponding voltage readings per sensor from these participants`. This data collection enabled observations regarding foot pressure characteristics among individuals with diverse foot conditions.

| Foot Status       | No. of Subjects | Average Age (years) | Average Weight (Kgs) |
|-------------------|-----------------|---------------------|-----------------------|
| Normal            | 6               | 19                  | 66                    |
| Pes Planus        | 3               | 30                  | 72                    |
| Pes Cavus         | 1               | 19                  | 61                    |
| Metatarsus Varus  | 1               | 39                  | 67                    |


![image](https://github.com/tusharshenoy/Foot-Pressure-Monitoring-System/assets/107348474/d3fd1d92-5133-473c-8107-6faf458b9637)

#### Colour map of the normal foot

### Characteristics of Test Subjects
The participants included individuals with different foot statuses, such as:
- Normal foot: 6 subjects, average age 19 years, average weight 66 Kgs
- Pes Planus (flat foot): 3 subjects, average age 30 years, average weight 72 Kgs
- Pes Cavus (high arch foot): 1 subject, age 19 years, weight 61 Kgs
- Metatarsus Varus: 1 subject, age 39 years, weight 67 Kgs

### Visualization and Interpretation of Results
The collected data from the volunteer participants allowed the observation of foot deformities and pressure variations. The voltage readings plotted for each participant from the 16 sensors showed distinct patterns. Individuals with different foot conditions exhibited varied pressure distributions across the sensors. For instance, a typical foot applied less pressure on certain sensors, indicating specific foot areas experiencing lower pressure. Conversely, individuals with flat feet applied more uniform pressure across all sensors. Additionally, a volunteer with a foot deformity showed reduced pressure readings on specific sensors, indicating uneven pressure distribution on the foot.

The system's ability to visualize and interpret pressure distribution patterns among individuals with various foot conditions highlights its potential for diagnostic and analytical purposes, enabling the identification and analysis of foot irregularities and pressure variations.

### 5. Comparison with Existing Models
   ### Comparison Table: Proposed System vs. Existing Models

| **Author, Year**              | **Type of Sensor**                    | **Cost** | **Mode of Communication**    | **Findings** |
|-------------------------------|---------------------------------------|----------|------------------------------|--------------|
| Payal S. Malvade         | FSR, Flexiforce sensor A201           | Not specified | Microcontroller via Bluetooth module | Signal processing through a microcontroller and transmission via Bluetooth. |
| Kyoungchul Kong         | GCF                                   | Not specified | FPGA via LAN cable | Utilized fuzzy logic algorithm to monitor abnormalities. |
| Kin Fuai Yong            | Fabric                                | Not specified | Arduino via Bluetooth | Improved spatial details regarding pressure distribution and activity tracking. |
| Dongran Wang             | Copper/ Carbon black electrode         | $50      | Bluetooth                    | Demonstrated high accuracy using a random forest classifier. |
| A. Jordan chan            | FSR                                   | $12      | Arduino                      | Consistent performance in measuring static plantar pressure. |
| Hongsheng Zhu             | Resistive pressure sensors            | Not specified | HD64180 8-bit microprocessor | Consistent gathering of raw pressure data for 7 minutes at 20 Hz per channel. |
| Jasim Ahmed Ali AL-Baghdadi  | Wearable force sensor mat (Resistive) | AUD $15,000 | External Computer System | Capable of acquiring high-quality pressure data. |
| Proposed System               | Thin copper foil capacitive sensor    | $8.40    | Raspberry Pi PICO via LAN/Bluetooth | Continuous monitoring of foot pressure through capacitive sensor array. |

### Key Advantages and Innovations

The proposed system utilizing thin copper foil capacitive sensors stands out with several key advantages and innovations compared to existing models:
- **Cost-Effective:** The system employs affordable materials and components, making it significantly cost-effective compared to other models, enabling broader accessibility.
- **Continuous Monitoring:** Offers real-time and continuous monitoring of foot pressure through the capacitive sensor array, enabling early warnings for changes in foot pressure.
- **Wearable and Practical:** Integrates sensors into an insole, allowing for practical use in various environments and activities.
- **Efficient Processing:** Uses a Raspberry Pi PICO for efficient data processing and analysis, ensuring accurate and rapid interpretation of foot pressure data.

These key advantages and innovations distinguish the proposed system, making it a practical, cost-effective, and efficient solution for continuous foot pressure monitoring compared to existing models in the field.

### 6. Conclusion
   ### Summary of the Project and Its Achievements

The project "Smart Insole Design for Foot Pressure Monitoring" introduces an innovative and cost-effective solution for continuous foot pressure monitoring. By employing a system composed of an insole embedded with a network of capacitive sensors and a Raspberry Pi PICO microprocessor, the project achieved several significant milestones:

- **Innovation in Foot Pressure Monitoring:** The project introduced a `novel method utilizing affordable materials`, such as `thin copper foil capacitive sensors` strategically placed within an insole, offering real-time and continuous foot pressure monitoring.

- **Effective Data Processing and Visualization:** Through the use of the `Raspberry Pi PICO`, the system efficiently processes sensor data, providing `accurate` and `timely analysis`, leading to `visual representations` of foot pressure distribution.

- **Testing and Observations:** The system underwent extensive testing with volunteer participants, which allowed for the observation of distinct foot pressure patterns among individuals with various foot conditions. This provided valuable insights into interpreting pressure variations and foot deformities.

### Future Enhancements and Possibilities

The project offers several avenues for future improvements and expansions:

- **Increased Sensor Count:** Enhancing the sensor array by increasing the count to `32 sensors` could provide more `detailed foot pressure data`, catering to a wider range of foot sizes and conditions.

- **Reduced System Size:** Reducing the overall size of the system could enable its use for individuals with smaller feet, such as children, extending its applicability.

- **Material Enhancement:** Exploring alternative materials or sensor designs to `improve conductivity`, `capacitance`, and `pressure sensitivity` could enhance the `system's accuracy` and efficiency.

- **Optimized Microprocessor:** Experimenting with different` microprocessors` could lead to `improved processing speeds` and more `efficient data analysis`.

- **Mobile Application Development:** Creating a dedicated mobile application for data visualization and interpretation could enhance user accessibility and convenience.

These future enhancements and possibilities aim to further refine the system's capabilities, making it more versatile, accurate, and user-friendly, thereby extending its utility in various applications and environments.
