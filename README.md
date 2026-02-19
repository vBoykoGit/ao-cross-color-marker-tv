# AO Cross & Color Markers

TradingView Pine Script v6 indicator that places text markers below price bars based on the Awesome Oscillator (AO).

## Signals

- **`0` (Zero Cross)** — AO crossed the zero line between the two most recent closed bars.
- **`C` (Color Change)** — AO bar color changed direction (switched from rising to falling or vice versa).

Both markers are drawn on closed bars only, so they never repaint.

## How to install

1. Open [TradingView](https://www.tradingview.com/) and go to any chart.
2. Click **Pine Editor** at the bottom of the screen.
3. Copy the entire contents of `AO_Cross_Color_Markers.pine` and paste it into the editor.
4. Click **Add to chart**.

## Parameters

| Parameter | Default | Description |
|---|---|---|
| Show Zero Cross (0) | `true` | Enable/disable the `0` marker |
| Show Color Change (C) | `true` | Enable/disable the `C` marker |
| Marker Color | `orange` | Color of both markers |
| Marker Size | `small` | Text size: tiny, small, normal, large, huge |

## How it works

The indicator calculates the Awesome Oscillator internally:

```
AO = SMA(hl2, 5) - SMA(hl2, 34)
```

On each closed bar it checks:

- **Zero cross**: did AO change sign between the previous two closed bars?
- **Color change**: did the AO direction (rising/falling) flip between the previous two closed bars?

When a condition is met, a character (`0` or `C`) is drawn below the corresponding price bar.
