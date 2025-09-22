# SHPE Robotics Showcase Project!

Using a live camera feed through Raspberry pi to remote control an RC Car!

## Quick Start (on a Pi)
```bash
python3 -m venv .venv
source .venv/bin/activate
pip install -r requirements.txt

# Run control loop (gamepad → serial → Arduino) (EVENTUALY)
python src/pi/pi_control.py

