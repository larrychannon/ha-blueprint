# Home Assistant Blueprints

Personal Home Assistant blueprints.

## Philips Hue Dimmer Switch V2

Standalone light controller for the Philips Hue Dimmer Switch V2 (`929002398602` / `RWL022`).

[Import into Home Assistant](https://my.home-assistant.io/redirect/blueprint_import/?blueprint_url=https%3A%2F%2Fraw.githubusercontent.com%2Flarrychannon%2Fha-blueprint%2Fmain%2Fphilips-hue-dimmer-switch-v2%2Fphilips_hue_dimmer_switch_v2.yaml)

Raw blueprint URL:

```text
https://raw.githubusercontent.com/larrychannon/ha-blueprint/main/philips-hue-dimmer-switch-v2/philips_hue_dimmer_switch_v2.yaml
```

Default behavior:

- `On` short press uses primary-light state as the source of truth:
  - if any primary light is on, primary and secondary lights turn off;
  - if all primary lights are off, primary and secondary lights turn on.
- Optional setting lets secondary lights stop following normal primary On and
  brightness controls.
- Optional setting makes lights turn on at 100% when toggled on, instead of
  restoring their previous brightness.
- Brightness up/down short press steps primary and secondary brightness.
- Brightness up/down hold continuously changes primary and secondary brightness
  until release.
- Bottom `Hue` button defaults to no-op, with an option to toggle secondary
  lights only.
- Another Hue option cycles through secondary lights. The selected light flashes
  once, then On and brightness controls affect that selected secondary light
  until the configurable selector timeout expires.
- Hooks, virtual double press, and helper state tracking are intentionally omitted.

The controller device selector is intentionally unfiltered. Home Assistant can
store different manufacturer/model metadata for this remote depending on ZHA,
Zigbee2MQTT, and quirk versions, so filtering can hide the remote from the
dropdown.
