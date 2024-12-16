# Dahua Integration

> Be water, my friend ~ Bruce Lee

---

## Overview

This guide provides instructions for integrating Dahua cameras with Home Assistant using the Dahua Integration.

---

## Chapters

- [Installation](#installation)
- [Setup](#setup)

---

## Dependencies

To install and use the Dahua Integration, you will need the following:

- [HACS](https://hacs.xyz/) (Home Assistant Community Store)

---

## Installation

To enable live streaming, ensure you include the following in your `configuration.yaml` file:

```yaml
ffmpeg:
```

Refer to the [FFmpeg](https://www.home-assistant.io/integrations/ffmpeg/) and [Stream](https://www.home-assistant.io/integrations/stream/) integrations for more details.

To install the Dahua Integration using [HACS](https://hacs.xyz/):

1. Open HACS in the Home Assistant menu.
2. Click on **Integrations**.
3. Click the **Explore & Add Repositories** button.
4. Search for **Dahua**.
5. Click **Install This Repository in HACS**.
6. Restart Home Assistant.
7. Configure the camera:
   - Navigate to **Configuration** -> **Integrations**.
   - Click the **Add Integration** button.
   - Search for **Dahua** and follow the configuration steps.

---

## Setup

Once the integration is added through HACS and available in the Home Assistant Integrations menu, follow these steps:

1. In the Home Assistant sidebar, click **Configuration**.
2. Click **Integrations**.
3. Click **Add Integration**.
4. Search for **Dahua** and select it.
5. Enter the required details:
   - **Username**: Your camera's username.
   - **Password**: Your camera's password.
   - **Address**: The IP address of your camera.
   - **Port**: The camera's HTTP port (default is `80`).
   - **RTSP Port**: The camera's RTSP port (default is `554`). This enables live streaming in Home Assistant.
   - **Events**: Select which motion or alarm events to monitor. If no events are selected, the integration will not maintain a connection to the camera.

   > Note: If specific events are missing, you can request them to be added by opening an issue in the [Dahua GitHub repository](https://github.com/rroller/dahua).

6. Save the settings and complete the setup.

---

## Notes

- By default, all streams will be added, even if not enabled in the camera. You can remove unwanted streams from the Home Assistant interface.
- For live streaming and event monitoring, ensure your camera is configured correctly and is on a stable network.

---

Your Dahua Integration is now ready to use! For additional support, refer to the [official documentation](https://github.com/rroller/dahua).
