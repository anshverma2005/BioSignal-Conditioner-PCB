# BioSignal-Conditioner-PCB
Designed a BioSignal Conditioner PCB for acquiring and processing surface EMG signals using a 220 Hz active bandpass filter and 50 Hz twin-T notch filter to suppress power-line interference. The PCB was designed in Altium Designer, fabricated, assembled, and tested using an Agilent DAQ.


BioSignal Conditioner PCB

A biomedical signal-conditioning PCB designed to acquire and process surface Electromyography (EMG) signals. The project implements an active bandpass filter and a 50 Hz twin-T notch filter to extract useful EMG information while suppressing power-line interference.

The complete circuit was designed in Altium Designer (Student Edition), verified on a breadboard, implemented on a two-layer PCB, fabricated, assembled, and tested using an Agilent Data Acquisition (DAQ) system.

📌 Project Information

Parameter| Details
Project| BioSignal Conditioner PCB
Course| EE381 – Electronic Circuits Laboratory
Application| Biomedical Signal Conditioning
Input Signal| Surface EMG
Design Software| Altium Designer – Student Edition
PCB Type| 2-Layer PCB
DAQ| Agilent Data Acquisition System
PCB Architecture| Arduino Uno Shield Footprint
Group Number| 8
Group Members| Krishna Agrawal, Parv Jain, Ansh Verma, Krish Jain

🎯 Objectives

- Acquire surface EMG signals from a human subject.
- Remove unwanted low/high-frequency components using a bandpass filter.
- Suppress 50 Hz power-line interference using a notch filter.
- Implement the complete signal-conditioning circuit on a compact PCB.
- Verify the circuit first using a breadboard prototype.
- Fabricate and assemble the final PCB.
- Observe the conditioned EMG signal using an Agilent DAQ.

⚙️ Signal Conditioning Stages

The signal-conditioning chain consists primarily of:

EMG Electrode
     │
     ▼
Signal Conditioning / Amplification
     │
     ▼
Active Bandpass Filter
     │
     ▼
50 Hz Twin-T Notch Filter
     │
     ▼
Conditioned EMG Output
     │
     ▼
Agilent DAQ

The bandpass and notch-filter stages were first implemented and verified on a breadboard before transferring the design to the PCB.

🔵 Bandpass Filter

An active bandpass filter was designed for the EMG signal with a center frequency of 220 Hz.

Bandpass Parameters

Parameter| Value
Filter Type| Active Bandpass
Center Frequency| 220 Hz
Prototype| Breadboard → PCB
Application| EMG signal extraction

Component Values

The component values shown in the filter schematic include:

Component| Value
R4| 33 kΩ
R5| 33 kΩ
R6| 15 kΩ
R8| 10 kΩ
R7| 9.1 kΩ
C1| 100 nF
C2| 100 nF
C5| 100 nF
C6| 100 nF
C7| 100 nF

The breadboard frequency response was checked before finalizing the PCB implementation.

🟠 50 Hz Notch Filter

A twin-T active notch filter was cascaded with the bandpass filter to reduce power-line interference.

Notch Filter Parameters

Parameter| Value
Filter Type| Active Twin-T Notch
Notch Frequency| 50 Hz
Purpose| Power-line interference suppression
Configuration| Cascaded with bandpass filter

Component Values

The schematic shows the following values for the notch-filter stage:

Component| Value
R1| 22 kΩ
R3| 2.2 kΩ
C3| 100 nF
C4| 100 nF
C8| 100 nF

The combined filter response was experimentally verified on the breadboard before PCB fabrication.

🧩 PCB Design

The PCB was designed using Altium Designer Student Edition.

The provided BioSig schematic was integrated with:

- Arduino Uno shield footprint
- Filter stages
- Amplifier stages
- Input/output connectors
- Power connections

The schematic was reviewed and verified before PCB layout.

PCB Layout Parameters

Parameter| Specification
PCB Layers| 2 Layers
CAD Software| Altium Designer
Routing| Interactive Router
Signal Routing| Primarily top layer
Ground/Power| Both layers
Design Output| Gerber + NC Drill
Fabrication| PCB manufacturing from generated files

All electrical connections were manually routed using the interactive router. Gerber and NC drill files were subsequently generated for fabrication.

🔧 PCB Fabrication & Assembly

After PCB fabrication, the components were manually populated and soldered.

Assembly Included

- Bandpass-filter resistors
- Notch-filter resistors
- Capacitors
- ICs
- Connector headers
- Other required PCB components

The fabricated board was fully assembled and subsequently tested with the EMG acquisition setup.

🧪 Testing Setup

The experimental setup consisted of:

EMG Probe
    │
    ▼
Forearm / Muscle
    │
    ▼
BioSignal Conditioner PCB
    │
    ▼
Agilent DAQ
    │
    ▼
Real-Time EMG Waveform

The EMG probe was placed on the forearm of the test subject. The subject alternated between a relaxed hand and voluntary hand contraction to generate measurable EMG bursts. The PCB output was connected directly to the Agilent DAQ for real-time observation.

📊 Results

Relaxed Condition

When the subject's hand was relaxed:

- Output remained close to the baseline.
- Noise level was relatively low.
- 50 Hz interference was effectively suppressed by the notch filter.

Muscle Contraction

During voluntary muscle contraction:

- Clear high-amplitude EMG bursts were observed.
- The signals appeared within the designed passband.
- The output demonstrated successful EMG signal conditioning.

These results confirmed the operation of both the bandpass and notch-filter stages.

📈 Key Specifications

Specification| Value
Signal| Surface EMG
Bandpass Center Frequency| 220 Hz
Notch Frequency| 50 Hz
Bandpass Filter| Active
Notch Filter| Active Twin-T
PCB| 2-Layer
Design Tool| Altium Designer
PCB Footprint| Arduino Uno Shield
Output Instrument| Agilent DAQ
Verification| Breadboard + PCB
Fabrication Files| Gerber + NC Drill

🛠️ Tools & Technologies

- Altium Designer
- PCB Schematic Capture
- PCB Layout & Routing
- Gerber File Generation
- NC Drill Generation
- Breadboard Prototyping
- Analog Filter Design
- EMG Signal Acquisition
- PCB Soldering & Assembly
- Agilent DAQ

📁 Suggested Repository Structure

BioSignal-Conditioner-PCB/
│
├── README.md
│
├── Altium/
│   ├── BioSig.SchDoc
│   └── BioSig.PcbDoc
│
├── Gerber/
│   ├── Gerber_Files/
│   └── NC_Drill/
│
├── Schematic/
│   └── BioSignal_Conditioner_Schematic.pdf
│
├── Documentation/
│   └── Project_Report.pdf
│
└── Images/
    ├── Breadboard_Prototype.png
    ├── PCB_Layout.png
    ├── Assembled_PCB.png
    └── DAQ_Output.png

✅ Conclusion

The BioSignal Conditioner PCB successfully demonstrates the complete workflow of a biomedical analog signal-conditioning system, from filter design and breadboard verification to schematic capture, PCB routing, fabrication, assembly, and experimental testing.

The 220 Hz active bandpass filter isolates the intended EMG frequency region, while the 50 Hz twin-T notch filter suppresses mains interference. The final PCB successfully produced observable EMG variations corresponding to voluntary hand contractions on the Agilent DAQ.

👥 Team

Group 8
- ANSH VERMA — 230159
- Krish Jain — 230572
- Krishna Agrawal — 230574
- Parv Jain — 230740
