# Vworld Geocode

This component has been created to be used with Home Assistant.

Vworld geocode is the process of converting device tracker location into a human-readable address in KOREA ONLY.

The sensor will update the address each time the device tracker location changes. If the device tracker is in a zone it will display the zone.

### Installation:

Copy the manifest.json file and place it in <config_dir>/custom_components/vworld_geocode/manifest.json

Copy the sensor.py file and place it in <config_dir>/custom_components/vworld_geocode/sensor.py

### Example entry for configuration.yaml
```
sensor:

  - platform: vworld_geocode
    origin: device_tracker.mobile_phone
```
### Configuration variables:

origin (Required): Tracking can be setup to track entity type device_tracker. The component updates it will use the latest location of that entity and update the sensor.

name (Optional): A name to display on the sensor. The default is “Vworld Geocode"

options (Optional): Select what level of address information you want. Choices are 'street_number', 'street', 'city', 'county', 'state', 'postal_code', 'country' or 'formatted_address'. You can use any combination of these options, separate each option with a comma. The default is “street, city"

display_zone (Optional): Choose to display a zone when in a zone. Choices are 'show' or 'hide'. The default is 'show'

gravatar (Optional): An email address for the device’s owner. You can set up a Gravatar [here.](https://gravatar.com) If provided, it will override `picture` The default is 'none'

api_key (Required): Your application’s API key (get one by following the instructions below). This key identifies your application for purposes of quota management.

You need to register for an API key to use Vworld Geocode. This can be done by following these instructions
* Go to [공간정보오픈플랫폼오픈API](https://www.vworld.kr/dev/v4dv_geocoderguide2_s001.do)
* Create an account
* Request an API key.
* Copy your API key.


### Example with optional entry for configuration.yaml
```
- platform: vworld_geocode
  name: michael
  origin: device_tracker.mobile_phone
  options: street_number, street, city
  display_zone: hide
  gravatar: youremail@address.com
  api_key: XXXX_XXXXX_XXXXX
```
