# EMBERS-HTTP-Publisher
EMBERS HTTP publisher to sent messages using HTTP protocol.

## About
This publisher allows you to create a communication using EMBERS, so that you can sent messages from devices using HTTP protocol to a defined gateway.

## Installation

#### Requirements
Run `pip install -r requirements.txt`;

#### Gateway
The gateway is used in order to receive messages sent from devices. In order to create a new gateway you just need to run the following:

`curl -X POST -d "type=GATEWAY" -d "name=GATEWAY_NAME" http://msg2.embers.citibrain.com/devices` 

This will return the gateway uuid and token, that you will need use as credentials for the constants file present in the EMBERS-Client, available [here](https://github.com/emberscity/EMBERS-Client). Also, you must use the Gateway uuid for the EMBERS-HTTP-Publisher in order to identify the GATEWAY for that will be sent the messages:

`GATEWAY = {
    'uuid': 'GATEWAY_UUID'
}`

#### Device
The devices are used to send messages to a defined gateway. In order to create a new device you just need to run the following:

`curl -X POST -d "type=DEVICE" -d "name=DEVICE_NAME" http://msg2.embers.citibrain.com/devices`

This will return the device uuid and token that you will need to send messages from the device to the gateway. This uuid and token must be used in the constants file as credentials for DEVICE from where the messages will be sent:

`DEVICE = {
    "uuid": "DEVICE_UUID",
    "token": "DEVICE_TOKEN"
}`

#### Run EMBERS-HTTP-Publisher

After creating gateway(s), device(s) and cunfiguring the constants file, you are able to send and receive messages using EMBERS with HTTP protocol. For that, you just need to run the EMBERS-Client, available [here](https://github.com/emberscity/EMBERS-Client), in order to start receiving messages sent from devices. After that, you are able to run the command `python embers_http_publisher.py` to start the EMBERS-HTTP-Publisher to send messages from the devices to the gateway.

## Next Steps

To simplify the devices and gateways creation we are working in the developer dashboard, available [here]( https://developer.embers.city/dashboard), so that you can create devices and gateways in few seconds!

