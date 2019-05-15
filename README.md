# Lovelace banner card

A fluffy linkable banner with interactive glances to spice up your home dashboards

## Installation

### Installation and tracking with `custom updater` _(Recommended)_

1. Make sure you've the [custom_updater](https://github.com/custom-components/custom_updater) component installed and working.
2. Configure Lovelace to load the card:.

```yaml
resources:
  - url: /customcards/github/nervetattoo/banner-card.js?track=true
    type: module
```

3. Run the service `custom_updater.check_all` or click the "CHECK" button if you use the tracker-card.
4. Refresh the website.

### Installation _(Manual)_

1. Download the `banner-card.js` from the [latest release](https://github.com/nervetattoo/banner-card/releases/latest) and store it in your `configuration/www` folder.
   _Previously you could download the source file from Github but starting from the 0.14 release that is no longer possible. If you try to do so it will crash_
2. Configure Lovelace to load the card:

```yaml
resources:
  - url: /local/simple-thermostat.js?v=1
    type: module
```

## Available configuration options:

| Key     | Type     | Description                                | Example                             |
| ------- | -------- | ------------------------------------------ | ----------------------------------- |
| heading | _string_ | The heading to display. Remember to escape | `heading: "\U0001F6CB Living room"` |
| background | _string_ | A valid CSS color to use as the background | `background: "#EDE7B0"`, `background: red` |
| link | _string_ | A link, to a different view in HA for example | `link: /lovelace/living_room` |
| entities | _array_ | An array of entities to display for glances. Either as strings or as objects | `entities: [binary_sensor.remote_ui]` |
| entities.entity | _string_ | Entity id | `- entity: binary_sensor.remote_ui` |
| entities.unit | _string|false_ | Override the automatic unit | `unit: My unit` |
| entities.name | _string_ | Override the automatic usage of friendly_name | `name: A sensor` |
| entities.map_state | _object_ | Map state values to resulting text or icons. A string prefixed with mdi: or hass: will yield a rendered icon. | `map_state: <br> home: mdi:home-account <br> not_home: mdi:walk<br> ` |
