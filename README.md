# BTM Impedance Tester GUI

A desktop application for automating AC impedance measurements of lithium-ion cells using a Tektronix AFG1022 Function Generator and two Keithley 2110 Digital Multimeters.

The GUI was developed for UBC Solar's Battery Mechanical Team (BTM) to simplify the cell characterization process by automatically detecting connected instruments, performing measurements, logging data, and displaying results in real time.

---

## Features

- Automatic VISA instrument detection
- One-click impedance measurements
- Automatic CSV logging
- Live impedance plot
- Running statistics
- Displays the five most recent measurements
- Standalone Windows executable (no Python installation required)

---

## Download

A pre-built executable is included in this repository.

Simply download and run:

```
BTM_Impedance_Tester.exe
```

---

## Requirements

Before running the application, ensure that:

- NI-VISA is installed.
- The instruments are connected and powered on.
- The instruments appear in NI Measurement & Automation Explorer (NI MAX).

---

## Supported Equipment

- Tektronix AFG1022 Function Generator
- Keithley 2110 Digital Multimeter (Voltage)
- Keithley 2110 Digital Multimeter (Current)

---

## Usage

1. Launch `BTM_Impedance_Tester.exe`.
2. Click **Detect Instruments**.
3. Confirm that all instruments are detected.
4. Enter the Cell ID.
5. Place the cell in the test fixture.
6. Click **Start Test**.

The application will automatically perform the measurement, calculate the impedance, and save the results to a CSV file.

---

## Output

Each completed measurement is automatically logged with:

- Cell ID
- AC Voltage
- AC Current
- Calculated Impedance
- Timestamp

---

## Troubleshooting

**No instruments detected**

- Verify all instruments are connected.
- Confirm NI-VISA is installed.
- Check that the instruments appear in NI MAX.
- Restart the application if necessary.

**Measurement timeout**

- Ensure all instruments are powered on.
- Check the USB connections.
- Restart the affected instrument if communication is lost.

**Unexpected measurements**

- Verify the cell has good contact with the fixture.
- Check all probe connections.
- Ensure the correct instruments were detected.

---

## Author

Deev Shah  
Battery Mechanical Lead  
UBC Solar
