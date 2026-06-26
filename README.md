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

- `On` short press toggles the selected lights.
- Brightness up/down short press steps brightness.
- Brightness up/down hold continuously changes brightness until release.
- Bottom `Hue` button defaults to no-op so it can be assigned to a custom purpose.
- Hooks, virtual double press, and helper state tracking are intentionally omitted.

The controller device selector is intentionally unfiltered. Home Assistant can
store different manufacturer/model metadata for this remote depending on ZHA,
Zigbee2MQTT, and quirk versions, so filtering can hide the remote from the
dropdown.
