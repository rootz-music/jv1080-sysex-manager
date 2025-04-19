# JV-1080 SysEx Manager

This toolkit provides a modular system for communicating with the Roland JV-1080 synthesizer using SysEx messages. You can use it to switch modes, control patch settings, send parameter changes, and more.

## 💾 Structure

```
jv1080-sysex-manager/
├── README.md
├── requirements.txt
├── RolandSysExManager.py
├── Roland_JV1080.ini
├── utils/
│   └── patch_database.json        # Optional
├── scripts/
│   ├── SwitchModes.py
│   ├── MidiCommTest.py
│   ├── JV_TempPatchMode.py
│   ├── MonosynthModule.py
│   ├── TempTestBeta.py
│   └── SysexTest.py
└── examples/
    └── sysex_templates/
```

## 🧠 Usage

```python
from RolandSysExManager import RolandSysExManager

manager = RolandSysExManager("Roland_JV1080.ini")
port = manager.select_midi_port()
manager.send_sysex("Temp Patch Tone1", "CutoffFrequency", 85, port)
```

## 📦 Requirements

- Python 3.10+
- `mido`
- `python-rtmidi`

## 🛠 Recommended Setup

```bash
pip install -r requirements.txt
```

## 🎛️ Modules

| Script               | Function                                      |
|----------------------|-----------------------------------------------|
| `SwitchModes.py`     | Switch between Patch and Performance modes    |
| `JV_TempPatchMode.py`| Send MSB/LSB/Program changes for patches      |
| `MonosynthModule.py` | Modify waveform, filter, and ADSR parameters |
| `MidiCommTest.py`    | Bank/Program MIDI test tool                   |
| `TempTestBeta.py`    | Fully interactive tone editor via CLI         |
| `SysexTest.py`       | Minimal tester for one SysEx parameter        |

