# BTM Impedance Tester GUI

## Overview

The BTM Impedance Tester GUI is a Python-based application developed for UBC Solar to automate AC impedance measurements of lithium-ion cells using laboratory test equipment.

The application:
- Automatically detects connected instruments
- Measures AC impedance using two digital multimeters and a function generator
- Displays live measurements
- Logs all results to a CSV file
- Tracks statistics across all tested cells
- Allows testing of thousands of cells with minimal manual input

---

# Supported Equipment

The application currently supports:

- Tektronix AFG1022 Function Generator
- Keithley 2110 Digital Multimeter (Voltage)
- Keithley 2110 Digital Multimeter (Current)

Communication is handled through VISA (USB/GPIB/LAN depending on your setup).

---

# Requirements

Install the following before running the application:

- Python 3.11 or newer
- NI-VISA
- PyVISA

Python packages:

```bash
pip install pyvisa pyvisa-py numpy pandas matplotlib customtkinter
```

---

# Installing NI-VISA

Download and install NI-VISA from National Instruments.

After installation, verify that your instruments appear in:

```
NI MAX (Measurement & Automation Explorer)
```

If the instruments are visible there, the GUI should detect them automatically.

---

# Connecting Instruments

Connect:

- Tektronix AFG1022
- Keithley 2110 #1
- Keithley 2110 #2

using USB.

Power on all instruments before launching the application.

---

# Starting the Application

Run:

```bash
python impedance_gui.py
```

or launch the compiled executable if provided.

The GUI will automatically search for connected VISA instruments.

---

# Instrument Detection

Press:

```
Detect Instruments
```

The GUI will automatically assign:

- Function Generator
- Voltage DMM
- Current DMM

No manual VISA address entry is required.

---

# Running a Measurement

1. Enter the Cell ID.
2. Insert the cell into the fixture.
3. Verify good electrical contact.
4. Press:

```
Start Test
```

The application will:

- Configure the function generator
- Measure AC voltage
- Measure AC current
- Calculate impedance
- Display the result
- Save the measurement automatically

---

# Saved Data

Each completed test is appended to a CSV file.

Typical columns include:

| Column | Description |
|---------|-------------|
| Cell ID | User-entered cell number |
| Voltage | Measured AC voltage |
| Current | Measured AC current |
| Impedance | Calculated cell impedance |
| Timestamp | Date and time of measurement |

---

# Statistics

The GUI continuously updates:

- Number of tested cells
- Mean impedance
- Minimum impedance
- Maximum impedance
- Standard deviation

These statistics update automatically after every measurement.

---

# Recent Measurements

The interface displays the five most recent impedance measurements for quick verification during testing.

---

# Graph

A live plot displays the impedance values of all tested cells.

This allows users to quickly identify:

- Outliers
- Measurement drift
- Unexpected trends

---

# Typical Workflow

1. Power on all instruments.
2. Launch the GUI.
3. Detect instruments.
4. Insert a cell.
5. Enter the Cell ID.
6. Press **Start Test**.
7. Replace the cell.
8. Repeat.

---

# Troubleshooting

## No instruments detected

- Verify USB connections.
- Ensure NI-VISA is installed.
- Check that instruments appear in NI MAX.
- Restart the application.

---

## VISA Timeout

Possible causes:

- Instrument not responding
- Incorrect instrument mode
- Loose USB connection

Restart the affected instrument and try again.

---

## Measurement returns zero

Check:

- Cell contact pressure
- Probe connections
- Function generator output
- DMM configuration

---

## CSV file not created

Ensure the application has write permission for the output folder.

---

# Safety

- Never short a lithium-ion cell.
- Verify correct polarity before connecting.
- Use appropriate PPE when required.
- Disconnect the fixture before modifying wiring.
- Inspect leads regularly for damage.

---

# Developed For

UBC Solar

Battery Mechanical Team (BTM)

For automated impedance testing of lithium-ion cells used in battery module assembly.
