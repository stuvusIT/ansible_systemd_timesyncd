# systemd-timesyncd

This role sets the timezone and configures and enables systemd-timesyncd.

## Requirements

systemd with timesyncd compiled in

## Role Variables

| Name                          | Default/Required      | Description                                         |
|-------------------------------|:---------------------:|-----------------------------------------------------|
| `timesync_timezone`           | `Etc/UTC`             | Timezone to set (relative to `/usr/share/zoneinfo`) |
| `timesync_ntp_hosts`          |                       | Array of NTP hosts                                  |
| `timesync_fallback_ntp_hosts` | `{0..3}.pool.ntp.org` | Array of fallback NTP hosts                         |

## Dependencies

None

## Example Playbook

```yml
- hosts: all
  roles:
  - systemd-timesyncd
    timesync_timezone: Europe/Berlin
    timesync_ntp_hosts:
      - some.ntp.host
      - another.ntp.host
```

## License

This work is licensed under a [Creative Commons Attribution-ShareAlike 4.0 International License](http://creativecommons.org/licenses/by-sa/4.0/).

## Author Information

- [Janne Heß](https://github.com/dasJ)
