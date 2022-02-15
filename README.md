# github-entity-row

Show GitHub repository sensor data on entity rows in Home Assistant's Lovelace UI

[![GH-release](https://img.shields.io/github/v/release/benct/lovelace-github-entity-row.svg?style=flat-square)](https://github.com/benct/lovelace-github-entity-row/releases)
[![GH-downloads](https://img.shields.io/github/downloads/benct/lovelace-github-entity-row/total?style=flat-square)](https://github.com/benct/lovelace-github-entity-row/releases)
[![GH-last-commit](https://img.shields.io/github/last-commit/benct/lovelace-github-entity-row.svg?style=flat-square)](https://github.com/benct/lovelace-github-entity-row/commits/master)
[![GH-code-size](https://img.shields.io/github/languages/code-size/benct/lovelace-github-entity-row.svg?color=red&style=flat-square)](https://github.com/benct/lovelace-github-entity-row)
[![hacs_badge](https://img.shields.io/badge/HACS-Default-orange.svg?style=flat-square)](https://github.com/hacs)

**NOTE:** This is not a standalone lovelace card, but a row element for
the [entities](https://www.home-assistant.io/lovelace/entities/) card.

## Installation

Add [github-entity-row.js](https://raw.githubusercontent.com/benct/lovelace-github-entity-row/master/github-entity-row.js)
to your `<config>/www/` folder and add the following to the `configuration.yaml` file:

```yaml
lovelace:
  resources:
    - url: /local/github-entity-row.js?v=2.0.0
      type: module
```

_OR_ install using [HACS](https://hacs.xyz/) and add this (if in YAML mode):

```yaml
lovelace:
  resources:
    - url: /hacsfiles/lovelace-github-entity-row/github-entity-row.js
      type: module
```

The above configuration can be managed in the Configuration -> Dashboards -> Resources panel when not using YAML mode.

## Configuration

| Name   | Type   | Default         | Description                               |
|--------|--------|-----------------|-------------------------------------------|
| type   | string | **Required**    | `custom:github-entity-row`                |
| user   | string | **Required**    | Your GitHub user name                     |
| repo   | string | **Required**    | Your GitHub repository                    |
| sensor | string | `<user>_<repo>` | Specify a custom sensor entity (optional) |
| name   | string | `repo`          | Override repository name                  |
| icon   | string | `mdi:github`    | Override default entity icon              |

The `user` and `repo` fields need to exactly match your GitHub user and repository names. If you rename the sensor
entity IDs from the GitHub integration, you can specify the updated sensor ID with the `sensor` field (without the
domain and type suffix). For example, if the integration exposes `sensor.custom_sensor_id_latest_release`, you should
specify `custom_sensor_id`.

## Migrate to version 2

The GitHub [integration](https://www.home-assistant.io/integrations/github/) was changed in HA version `2022.2.0` to
include several sensors for each GitHub repository. If you are using the latest HA installation, you need to upgrade to
version `>2.0.0` of this card. The main change is that the `entity` field has been replaced by `user` and `repo`. You
might also need to manually enable the following sensors from your GitHub integration; `Stars`, `Issues`
and `Pull Requests`.

## Example

![github-entity-row](https://raw.githubusercontent.com/benct/lovelace-github-entity-row/master/example.png)

```yaml
type: entities
title: GitHub
entities:
  - type: custom:github-entity-row
    user: benct
    repo: home-assistant-config
    name: HA Config
  - type: custom:github-entity-row
    user: benct
    repo: lovelace-github-entity-row
    icon: mdi:github
  - type: custom:github-entity-row
    user: benct
    repo: lovelace-multiple-entity-row
  - type: custom:github-entity-row
    user: benct
    repo: lovelace-xiaomi-vacuum-card
```

## My cards

[xiaomi-vacuum-card](https://github.com/benct/lovelace-xiaomi-vacuum-card) |
[multiple-entity-row](https://github.com/benct/lovelace-multiple-entity-row) |
[github-entity-row](https://github.com/benct/lovelace-github-entity-row) |
[battery-entity-row](https://github.com/benct/lovelace-battery-entity-row) |
[~~attribute-entity-row~~](https://github.com/benct/lovelace-attribute-entity-row)

[![BMC](https://www.buymeacoffee.com/assets/img/custom_images/white_img.png)](https://www.buymeacoff.ee/benct)
