# Trip Speed → Distance by Integration (تحليل الرحلة: السرعة والمسافة بالتكامل)

A self-contained HTML report (Arabic, RTL) analysing a single vehicle trip from the FleetOo
tracking platform. It shows the trip summary, the CAN-based odometer (start/end), a
speed-vs-time graph, and computes the travelled distance as the **area under the speed curve**
(numerical integration, trapezoidal rule).

**Speed source:** the curve and the integral use **GPS speed** (`position_speed`), not CAN speed.
CAN speed (`can_vehicle_speed`) is available on the device and was nearly identical for this trip.

- Device IMEI: `866107088876939` (RUPTELA Smart5) — vehicle حهر 2843
- Trip: 2026-11-17 01:15:31 → 01:24:45 (Asia/Riyadh)
- Result: trapezoidal integral ≈ **3.763 km** vs GPS distance **3.858 km** vs CAN odometer Δ **4.4 km**


## Data

Figures are extracted from the FleetOo production telemetry (ClickHouse) and are embedded
statically in the page — the page makes no network calls except loading the Tajawal web font.
