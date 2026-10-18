# Матриця трасованості вимог

Дії з пультом, телефоном і ручними налаштуваннями обладнання описуються в `procedures/operator_steps.md`.

| Вимога з PRD | Тестовий файл | Тест-функції |
|---|---|---|
| FR-01 — запуск вузлів | `tests/test_startup_and_power.py` | `test_thor_receives_5v`<br>`test_startup_leds_and_oled` |
| FR-02 — налаштування Wi‑Fi та автоматичний зв’язок ESP із пультом | `tests/test_esp_binding.py` | `test_button_opens_wifi_mode`<br>`test_binding_phrase_saved_via_wifi`<br>`test_auto_connection_after_power_on` |
| FR-03 — перемикання каналу Thor з пульта | `tests/test_thor_channel.py` | `test_mismatch_hides_video`<br>`test_match_restores_video` |
| FR-04 — передавання відео через дві пари каналів | `tests/test_video.py` | `test_video_when_both_pairs_match`<br>`test_no_video_if_drone_pair_differs`<br>`test_no_video_if_ground_pair_differs` |
| FR-05 — передавання RC-команд | `tests/test_elrs_control.py` | `test_two_rc_values_reach_test_rx` |
| FR-06 — відновлення після вимкнення | `tests/test_recovery.py` | `test_phrase_persists_after_restart`<br>`test_rc_thor_video_recover` |
| NFR-01 — відео з’являється не пізніше ніж за 10 с | `tests/test_thor_channel.py` | `test_channel_switch_within_10s` |
| NFR-02 — очікуваний результат 20 перемикань | `tests/test_thor_channel.py` | `test_20_channel_switches` |
| NFR-03 — відновлення після кожного з 10 циклів живлення | `tests/test_recovery.py` | `test_10_power_cycles_restore_links` |
| NFR-04 — 5 В і 9 В у межах ±5 % при 22,2 В і 25,2 В на вході | `tests/test_startup_and_power.py` | `test_power_rails_at_two_inputs` |
| NFR-05 — за 10 хв немає втрат відео довших за 2 с | `tests/test_video.py` | `test_no_video_gap_over_2s_in_10min` |
| NFR-06 — 20 RC-команд доходять без пропусків і в правильному порядку | `tests/test_elrs_control.py` | `test_20_rc_changes_in_order` |
| NFR-07 — текст, три кольори та QR читаються на 9 із 10 кадрів | `tests/test_video.py` | `test_text_colors_qr_in_9_of_10_frames` |

Перевірки NFR-04 виконуються для обох ліній живлення при двох значеннях вхідної напруги. Для NFR-07 беруться 10 кадрів, рівномірно розподілених у хвилинному записі, і QR-код порівнюється з `test_data/expected_qr.txt`.