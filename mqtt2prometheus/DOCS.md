# Home Assistant Community Add-on: MQTT2Prometheus

MQTT2Prometheus is an exportes that translates MQTT topics to Prometheus metrics.
The core design is that clients send arbitrary JSON messages on the topics. The translation between the MQTT representation and Prometheus metrics is configured in the mqtt2prometheus exporter since we often can not change the IoT devices sending the messages. Clients can push metrics via MQTT to an MQTT Broker. This exporter subscribes to the broker and expose the received messages as prometheus metrics.

![Overview Diagram](https://github.com/hikhvar/mqtt2prometheus/blob/master/docs/overview.drawio.svg)

[Read MQTT2Prometheus's documentation](https://github.com/hikhvar/mqtt2prometheus)

## Installation

The installation of this add-on is pretty straightforward and not different in
comparison to installing any other Home Assistant add-on.

1. Go to the "Settings > Add-ons" panel in Home Assistant.
2. Click on the "Add-on store" at the bottom of the page.
3. Click on the three dots on the top and select "Repository".
4. Add this repository: https://github.com/christian-vdz/hassio-mqtt2prometheus-addon
5. Search for the "MQTT2Prometheus" add-on in the Supervisor add-on store an
   install it.
6. Configure the addon with your MQTT server IP, credentials and base topic
7. Start the "MQTT2Prometheus" add-on.
8. Click the "OPEN WEB UI" button to open MQTT2Prometheus.

## Configuration

On configuration tab you will find the following settings:

| Setting | Description | Default | Mandatory |
| --- | --- | --- | --- |
| mqtt_server | IP address of your MQTT Server | "127.0.0.1" | Yes |
| mqtt_user | Your MQTT user | "mqtt" | Yes |
| mqtt_password | Your MQTT user's password | "" | Yes |
| mqtt_base_topic | Your MQTT base topic | "zigbee2mqtt" | Yes|

You can also configure the listen port for MQTT2Prometheus's web socket (default 9641).

## Changelog & Releases

This repository keeps a change log using [GitHub's releases][releases]
functionality. The format of the log is based on
[Keep a Changelog][keepchangelog].

Releases are based on [Semantic Versioning][semver], and use the format
of `MAJOR.MINOR.PATCH`. In a nutshell, the version will be incremented
based on the following:

- `MAJOR`: Incompatible or major changes.
- `MINOR`: Backwards-compatible new features and enhancements.
- `PATCH`: Backwards-compatible bugfixes and package updates.

## Support

Got questions?

You have several options to get them answered:

- Join the [Reddit subreddit][reddit] in [/r/homeassistant][reddit]

You could also [open an issue here][issue] GitHub.

## Authors & contributors

The original setup of this repository is by [Christian VDZ][christian-vdz].

For a full list of all authors and contributors,
check [the contributor's page][contributors].

## License

MIT License

Copyright (c) 2019-2020 Christian VDZ

Permission is hereby granted, free of charge, to any person obtaining a copy
of this software and associated documentation files (the "Software"), to deal
in the Software without restriction, including without limitation the rights
to use, copy, modify, merge, publish, distribute, sublicense, and/or sell
copies of the Software, and to permit persons to whom the Software is
furnished to do so, subject to the following conditions:

The above copyright notice and this permission notice shall be included in all
copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR
IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY,
FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE
AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER
LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM,
OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN THE
SOFTWARE.

[addon-badge]: https://my.home-assistant.io/badges/supervisor_addon.svg
[addon]: https://my.home-assistant.io/redirect/supervisor_addon/?addon=a0d7b954_uptime-kuma&repository_url=https%3A%2F%2Fgithub.com%2Fhassio-addons%2Frepository
[contributors]: https://github.com/christian-vdz/hassio-mqtt2prometheus-addon/graphs/contributors
[christian-vdz]: https://github.com/christian-vdz
[issue]: https://github.com/christian-vdz/hassio-mqtt2prometheus-addon/issues
[reddit]: https://reddit.com/r/homeassistant
[releases]: https://github.com/christian-vdz/hassio-mqtt2prometheus-addon/releases
[semver]: https://semver.org/spec/v2.0.0.html
