Vertx as a MQTT Service
Clients are Node.js running on Intel Edison's connected via Bluetooth
to TI SensorTag
and
LightBlue Bean

Edison1
ssh root@192.168.3.5
rfkill unblock bluetooth
hciconfig hci0 up
cd ~/git/ti_sensortag_mqtt/
node ir_temperature_cc2650.js NOBLE_HCI_DEVICE_ID=hci0

{"sensorid":"ti_cc2650", "temp":29.6, "time":1485389839744}

Edison2
ssh root@192.168.3.6
rfkill unblock bluetooth
hciconfig hci0 up
cd git/lightbluebean_node
node poller_temp_mqtt.js NOBLE_HCI_DEVICE_ID=hci0

{"sensorid":"lbb_sense", "temp":26.0, "time":1485389121978}