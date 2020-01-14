# github-entity-row
Show GitHub repository sensor data on entity rows in Home Assistant's Lovelace UI

[![GH-release](https://img.shields.io/badge/version-1.0.0-red.svg?style=flat-square)](https://raw.githubusercontent.com/benct/lovelace-github-entity-row/master/github-entity-row.js)
[![GH-last-commit](https://img.shields.io/github/last-commit/benct/lovelace-github-entity-row.svg?style=flat-square)](https://github.com/benct/lovelace-github-entity-row/commits/master)
[![GH-code-size](https://img.shields.io/github/languages/code-size/benct/lovelace-github-entity-row.svg?style=flat-square)](https://github.com/benct/lovelace-github-entity-row)
[![hacs_badge](https://img.shields.io/badge/HACS-Default-orange.svg)](https://github.com/custom-components/hacs)

## Setup

Add [github-entity-row.js](https://raw.githubusercontent.com/benct/lovelace-github-entity-row/master/github-entity-row.js)
to your `<config>/www/` folder. Add the following to your `ui-lovelace.yaml` file:
```yaml
resources:
  - url: /local/github-entity-row.js?v=1.0.0
    type: module
```

OR install using [HACS](https://hacs.xyz/) and add this instead:
```yaml
resources:
  - url: /community_plugin/lovelace-github-entity-row/github-entity-row.js
    type: module
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
[multiple-entity-row](https://github.com/benct/lovelace-multiple-entity-row) |
[github-entity-row](https://github.com/benct/lovelace-github-entity-row) |
[~~attribute-entity-row~~](https://github.com/benct/lovelace-attribute-entity-row)

[![BMC](https://www.buymeacoffee.com/assets/img/custom_images/white_img.png)](https://www.buymeacoff.ee/benct)
