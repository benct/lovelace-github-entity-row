# github-entity-row
Show GitHub repository sensor data on entity rows in Home Assistant's Lovelace UI

[![GH-release](https://img.shields.io/github/v/release/benct/lovelace-github-entity-row.svg?style=flat-square)](https://github.com/benct/lovelace-github-entity-row/releases)
[![GH-downloads](https://img.shields.io/github/downloads/benct/lovelace-github-entity-row/total?style=flat-square)](https://github.com/benct/lovelace-github-entity-row/releases)
[![GH-last-commit](https://img.shields.io/github/last-commit/benct/lovelace-github-entity-row.svg?style=flat-square)](https://github.com/benct/lovelace-github-entity-row/commits/master)
[![GH-code-size](https://img.shields.io/github/languages/code-size/benct/lovelace-github-entity-row.svg?color=red&style=flat-square)](https://github.com/benct/lovelace-github-entity-row)
[![hacs_badge](https://img.shields.io/badge/HACS-Default-orange.svg?style=flat-square)](https://github.com/hacs)

**NOTE:** This is not a standalone lovelace card, but a row element for the [entities](https://www.home-assistant.io/lovelace/entities/) card.

## Installation

Add [github-entity-row.js](https://raw.githubusercontent.com/benct/lovelace-github-entity-row/master/github-entity-row.js)
to your `<config>/www/` folder and add the following to the `configuration.yaml` file:
```yaml
lovelace:
  resources:
    - url: /local/github-entity-row.js?v=1.0.0
      type: module
```

_OR_ install using [HACS](https://hacs.xyz/) and add this (if in YAML mode):
```yaml
lovelace:
  resources:
    - url: /hacsfiles/lovelace-github-entity-row/github-entity-row.js
      type: module
```

The above configuration can be managed directly in the Configuration -> Lovelace Dashboards -> Resources panel when not using YAML mode,
or added by clicking the "Add to lovelace" button on the HACS dashboard after installing the plugin.

## Configuration

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

Usage with [auto-entities](https://github.com/thomasloven/lovelace-auto-entities) card:
```yaml
type: custom:auto-entities
card:
  type: entities
filter:
  include:
    - entity_id: sensor.github*   # or use other matchers
      options:
        type: custom:github-entity-row
        <github-entity-row options>
```

## My cards

[xiaomi-vacuum-card](https://github.com/benct/lovelace-xiaomi-vacuum-card) |
[multiple-entity-row](https://github.com/benct/lovelace-multiple-entity-row) |
[github-entity-row](https://github.com/benct/lovelace-github-entity-row) |
[battery-entity-row](https://github.com/benct/lovelace-battery-entity-row) |
[~~attribute-entity-row~~](https://github.com/benct/lovelace-attribute-entity-row)

[![BMC](https://www.buymeacoffee.com/assets/img/custom_images/white_img.png)](https://www.buymeacoff.ee/benct)
