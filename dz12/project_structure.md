# Структура тестового проєкту

```text
dz12/
├── PRD.md
├── stand_diagram.png
├── wokwi_link.md
├── wokwi_uc02a.png
├── project_structure.md
├── traceability_matrix.md
├── README.md
├── requirements.txt
├── stand.example.yaml
├── .gitignore
├── procedures/
│   ├── stand_setup.md
│   └── operator_steps.md
├── test_data/
│   ├── test_pattern.png
│   └── expected_qr.txt
├── hil/
│   ├── __init__.py
│   ├── power.py
│   ├── video_stand.py
│   ├── video_capture.py
│   ├── image_analysis.py
│   └── elrs_receiver.py
├── tests/
│   ├── conftest.py
│   ├── test_startup_and_power.py
│   ├── test_esp_binding.py
│   ├── test_thor_channel.py
│   ├── test_elrs_control.py
│   ├── test_video.py
│   └── test_recovery.py
└── results/
    ├── logs/
    ├── measurements/
    ├── frames/
    └── reports/
```
