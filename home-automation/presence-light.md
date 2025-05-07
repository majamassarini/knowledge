# Presence Light automation

## States
The possible states for the new automation are the following:
  - On
  - Off
  - Forced On
  - Forced Off

## Default state
By default the light appliance is in an off state.

## Managed events
The appliance automation reacts to the following events:
  - Forced with values On, Off, Not
  - Presence with values On, Off
### Events and states
The appliance automation will react to events in the following way:
  - Forced On:
    * from Off to Forced On state
    * from Forced Off to Off state
      (if Presence Off in last received events)
    * from Forced Off to On state
      (if Presence On in last received events)
  - Forced Off:
    * from On to Forced Off state
    * from Forced On to Off state
      (if Presence Off in last received events)
    * from Forced On to On state
      (if Presence On in last received events)
  - Forced Not:
    * from Forced On to Off state
      (if Presence Off in last received events)
    * from Forced On to On state
      (if Presence On in last received events)
  - Presence On
    * from Off to On state
  - Presence Off
    * from On to Off state

## Other events
The Presence Light automation can also receive the following events:
  - Brightness for Forced On state, with values from 0 lux to 100 lux
  - Brightness for On state, with values from 0 lux to 100 lux
  - Hue for Forced On state, with values from 0° to 360°
  - Hue for On state, with values from 0° to 360°