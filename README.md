# github-entity-row
GitHub repository sensor data on entity rows in Home Assistant's Lovelace UI

[![GH-release](https://img.shields.io/badge/version-1.0.0-red.svg?style=flat-square)](https://raw.githubusercontent.com/benct/lovelace-github-entity-row/master/github-entity-row.js)
[![GH-last-commit](https://img.shields.io/github/last-commit/benct/lovelace-github-entity-row.svg?style=flat-square)](https://github.com/benct/lovelace-github-entity-row/commits/master)
[![GH-code-size](https://img.shields.io/github/languages/code-size/benct/lovelace-github-entity-row.svg?style=flat-square)](https://github.com/benct/lovelace-github-entity-row)

## Setup

Add [github-entity-row.js](https://raw.githubusercontent.com/benct/lovelace-github-entity-row/master/github-entity-row.js) to your `<config>/www/` folder. Add the following to your `ui-lovelace.yaml` file:

```yaml
resources:
  - url: /local/github-entity-row.js?v=1.0.0
    type: js
```

### *(Optional)* Add to custom updater

1. Make sure you have the [custom_updater](https://github.com/custom-components/custom_updater) component installed and working.

2. Add a new reference under `card_urls` in your `custom_updater` configuration in `configuration.yaml`.

```yaml
custom_updater:
  card_urls:
    - https://raw.githubusercontent.com/benct/lovelace-github-entity-row/master/tracker.json
```

## Options

| Name | Type | Default | Description
| ---- | ---- | ------- | -----------
| type | string | **Required** | `custom:github-entity-row`
| entity | string | **Required** | `sensor.my_github_repository`
| name | string | `friendly_name` | Override entity friendly name
| icon | string | `mdi:github-circle` | Override default entity icon

## Example

![github-entity-row](https://raw.githubusercontent.com/benct/lovelace-github-entity-row/master/example.png)

```yaml
type: entities
title: GitHub
entities:
  - type: custom:github-entity-row
    entity: sensor.home_assistant_config
  - type: custom:github-entity-row
    entity: sensor.lovelace_github_entity_row
  - type: custom:github-entity-row
    entity: sensor.lovelace_xiaomi_vacuum_card
```

## My cards

[xiaomi-vacuum-card](https://github.com/benct/lovelace-xiaomi-vacuum-card) | 
[github-entity-row](https://github.com/benct/lovelace-github-entity-row) | 
[multiple-entity-row](https://github.com/benct/lovelace-multiple-entity-row) | 
[attribute-entity-row](https://github.com/benct/lovelace-attribute-entity-row)

[![BMC](https://www.buymeacoffee.com/assets/img/custom_images/white_img.png)](https://www.buymeacoff.ee/benct)
