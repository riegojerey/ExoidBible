# Frigate

> Thou shall pray, lul (*/ω\*)

[Frigate Official Documentation](https://docs.frigate.video/)

---

## Chapters

- [Installation](#installation)
- [Frigate Entities](#frigate-entities)
- [Configuration YAML for Frigate](#configuration-yaml-for-frigate)
- [Mask and Zone in Frigate](#mask-and-zone-in-frigate)

---

## Dependencies

- [MQTT](mqtt.md)

---

## Installation

### Home Assistant Add-On

1. Go to **Settings > Add-ons > Add-On Store**.
2. Click the three dots in the upper-right corner and select **Repositories**.
3. Add the following repository: `https://github.com/blakeblackshear/frigate-hass-addons`.
4. After adding the repository, search for **Frigate** and click **Install**.

---

## Frigate Entities

> This is needed for entities to show up. Redo the MQTT integration if entities are not available.

1. Go to **Settings > Devices & Services > Add Integration**.
2. Search for **Frigate** and follow the setup process.

---

## Configuration YAML for Frigate

```yaml
mqtt:
  host:                 
  topic_prefix: frigate
  user:                 
  password:             

ffmpeg:
  hwaccel_args: auto

detectors:
  ov:
    type: openvino
    device: GPU

model:
  width: 300
  height: 300
  input_tensor: nhwc
  input_pixel_format: bgr
  path: /openvino-model/ssdlite_mobilenet_v2.xml
  labelmap_path: /openvino-model/coco_91cl_bkgr.txt

record:
  enabled: true
  retain:
    days: 7
    mode: motion
  events:
    retain:
      default: 5
      mode: motion

snapshots:
  enabled: true
  retain:
    default: 5

objects:
  track:
    - person
    - car

cameras:
  Carport01:  # Name the camera
    enabled: true
    ffmpeg:
      inputs:
        - path: rtsp://user:pass@ip_add_camera:port/cam/realmonitor?channel=1&subtype=0&unicast=true&proto=Onvif
          roles:
            - detect
    detect:
      enabled: true
      width: 1280
      height: 720
    zones: {}

  Carport02:  # Name the camera
    enabled: true
    ffmpeg:
      inputs:
        - path: rtsp://user:pass@ip_add_camera:port/cam/realmonitor?channel=1&subtype=0&unicast=true&proto=Onvif
          roles:
            - detect
    detect:
      enabled: true
      width: 1280
      height: 720
    zones: {}

  Outdoor:  # Name the camera
    enabled: true
    ffmpeg:
      inputs:
        - path: rtsp://user:pass@ip_add_camera:port/cam/realmonitor?channel=1&subtype=0&unicast=true&proto=Onvif
          roles:
            - detect
    detect:
      enabled: true
      width: 1280
      height: 720
    zones: {}

version: 0.14
```

---

## Mask and Zone in Frigate

| Description             | Links                                                        |
| ----------------------- | ------------------------------------------------------------ |
| Mask Full Documentation | [Masks Documentation](https://docs.frigate.video/configuration/masks/) |
| Zone Full Documentation | [Zones Documentation](https://docs.frigate.video/configuration/zones/) |

1. Click **Frigate** in the sidebar.
2. Click the **gear icon**.
3. Open **Settings**.
4. Navigate to **Masks and Zones**.

---
