# autofeeder
Refrigerated Auto Feeder

This is a work in progress to control a six-beaker feeder from a mini-fridge.

## Hardware

* ESP32-C3-DevKit-RUST-1
* 7x 12V DC Peristaltic Pump (5 small, 1 large)
* 6x 12V DC fan modified with permanent magnets
* 6x beakers
* 6x magnetic stir bars
* 13x 12V opto-isolated relays
* 12x 12V potentoimeters

## Software
This controls the hardware using a REST API. The brains are stored on a separate controller.

## API

### GET /health

Returns 200 OK if the device is running.

### POST /dose

Doses from beaker with a given amount of food.

POST body:
```json
{
    "name": "1",
    "spin_time": 5000, // milliseconds
    "wait_time": 5000, // milliseconds
    "dose_time": 5000 // milliseconds
}
```
