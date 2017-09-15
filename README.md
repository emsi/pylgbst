# Python library to interact with LEGO Move Hub

Requires `gattlib` to be installed, currently Python 2.7 only

Best way to start is to look at [demo.py](demo.py) file, and run it.

## Features

- auto-detect and connect for Bluetooth device
- auto-detects devices connected to Hub
- permanent Bluetooth connection server for faster debugging
- angled and timed movement for motors
- LED color change
- sensor data subscribe/unsubscribe
- battery voltage available

## Usage

```python
from pylgbst import MoveHub

hub = MoveHub()
print(hub.get_name())

for device in hub.devices:
    print(device)
```

## Debug Server

```
sudo python -c "from pylgbst.comms import *; import logging; logging.basicConfig(level=logging.DEBUG); DebugServer(BLEConnection().connect()).start()"
```

## Roadmap

- make notifications from pygattlib to quickly get into parallel thread, to avoid segfaults
- support working with push button
- Give nice documentation examples, don't forget to mention logging
- make angled motors to be synchronous by default => 3-state status
- make sure unit tests cover all important code

## Links

- https://github.com/JorgePe/BOOSTreveng - source of protocol knowledge
- https://github.com/RealTimeWeb/blockpy
- https://ru.wikipedia.org/wiki/App_Inventor
- https://en.wikipedia.org/wiki/Blockly

