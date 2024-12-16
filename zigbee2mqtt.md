# Zigbee2MQTT

> For discovering zigbee devices only

[SMLIGHTSLZB-06](https://smlight.tech/manual/slzb-06/guide/installation/)

---

### Chapters:

- [Installation](#Installation:)
- [Usage](#Usage)
- [Multiple Coordinators](#Multiple Coordinators)

---

#### Dependencies:

- [MQTT](mqtt.md)

----

#### Installation:

1. In HomeAssistant go to **Settings > Add-ons >** click **3 buttons (upper right) , Repositories** , add this  `https://github.com/zigbee2mqtt/hassio-zigbee2mqtt` 
2. Now in the **Add-ons** , search for **Zigbee2MQTT** and press **Install**
3. Click on **Configuration** and go to **serial**
4.  For devices like **SMLIGHT SLZB-06** , use the code below and put it in **serial tab**.

```
port: tcp://ipaddress_of_ur_zigbee_coordinator:port
baudrate: 115200
adapter: ember

```

----

#### Usage:

- Go to **Zigbee2MQTT**  and Turn on Search Devices

----

### Multiple Coordinators

Refer to this [Video](https://www.youtube.com/watch?v=QOx733CU1p8) or [Read](https://smlight.tech/manual/slzb-06/guide/multiple-adapters-setup/)

- To setup multiple coordinators go to **Settings > Add-ons > 3 buttons (upper right) > then copy and paste the `https://github.com/zigbee2mqtt/hassio-zigbee2mqtt` ** but **add "/"** in the last part, if needed more then add **"//"**

- In **configuration** of each Zigbee2Mqtt ,change the **data_path** to your liking and  add in the **MQTT**  tab a **base_topic**

  ```yaml
  user: user
  password: user
  base_topic: zigbee2mqtt_2ndfloor
  
  ```

  **EACH CONFIGURATION SHOULD HAVE DIFFERENT BASE_TOPIC **

- Last is to change the port (increments of 1 ) 

