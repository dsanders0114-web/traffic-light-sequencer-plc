# traffic-light-sequencer-plc
Allen-Bradley Studio 5000 traffic light sequencer using TON, TOF, and one-shot logic with pedestrian control, maintenance mode, and diagnostics.


# Traffic Light Sequencer (Studio 5000)

## Overview
This project is a PLC-based traffic light controller built in Allen-Bradley Studio 5000 using ladder logic.

It demonstrates:
- State machine sequencing using a step variable (`SeqStep`)
- Timer-based phase control using TON and TOF
- Edge-triggered logic using one-shots (ONS)
- Pedestrian request handling with safe insertion into sequence
- Maintenance flashing yellow mode
- Manual step/test mode
- Fault detection and diagnostic status bits

---

## Features

### Automatic Traffic Control
- North/South and East/West traffic phases
- Green → Yellow → All Red transitions
- Safe timing using TON instructions

### Pedestrian Crossing System
- Pushbutton input captured with ONS
- Request is latched and serviced at safe all-red steps
- Walk signal with automatic reset

### Maintenance Mode
- Flashing yellow override for both directions
- All other outputs disabled
- Implemented using timer-based flashing logic

### Manual Mode
- Step-by-step sequence advancement
- Useful for testing and commissioning

### Diagnostics
- Detects conflicting green lights
- Detects multiple lamps active per direction
- Detects invalid pedestrian states
- General fault indicator

---

## Sequence Steps

| Step | Description |
|------|------------|
| 10 | North/South Green |
| 20 | North/South Yellow |
| 30 | All Red |
| 35 | Pedestrian Walk |
| 40 | East/West Green |
| 50 | East/West Yellow |
| 60 | All Red |
| 65 | Pedestrian Walk |

---

## Technologies Used

- Allen-Bradley Studio 5000
- Ladder Logic
- TON (Timer On Delay)
- TOF (Timer Off Delay)
- ONS (One-Shot)

---

## How to Run

1. Open `.ACD` file in Studio 5000
2. Put controller in Run Mode (or simulate)
3. Monitor `SeqStep` and outputs
4. Test:
   - Pedestrian pushbutton
   - Maintenance mode
   - Manual step mode

---

## Author

Daryl Sanders  
Field Service Technician | Aspiring Controls/Automation Engineer
