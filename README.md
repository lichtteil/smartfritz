# smartfritz

Node module to communicate with a AVM FritzBox and FRITZ!DECT 200 (smart home hardware) providing the following functions:

- Get the session ID (getSessionID)
- Get the switch (FRITZ!DECT 200) State (getSwitchState)
- Set the switch (FRITZ!DECT 200) ON (setSwitchOn)
- Set the switch (FRITZ!DECT 200) OFF (setSwitchOff)
- Get the switch (FRITZ!DECT 200) Power (getSwitchPower)
- Get the switch (FRITZ!DECT 200) Energy (getSwitchEnergy)
- Get the switch (FRITZ!DECT 200) List (getSwitchList)
- Get the phone list (getPhoneList)
- Set the guest wlan (setGuestWLan)
- Get the guest wlan settings (getGuestWLan)

correction of package.json with main for "out of the box" function.

For AVM FRITZ!DECT 200  control you need to know your Actuator identification number (AIN)

## Install

```bash
npm install smartfritz
```

## How to use

Get the session ID:
```js
var fritz = require('smartfritz');

fritz.getSessionID("user", "password", function(sid){
    console.log(sid);
});
```

Get the switch Power (FRITZ!DECT 200):
```js
var fritz = require('smartfritz');

fritz.getSwitchPower(sid, aid, function(sid){
    console.log(sid);
});
```

Get the switch Energy (FRITZ!DECT 200):
```js
var fritz = require('smartfritz');

fritz.getSwitchEnergy(sid, aid, function(sid){
    console.log(sid);
});
```

Get the switch State (DECT200):
```js
var fritz = require('smartfritz');

fritz.getSwitchState(sid, aid, function(sid){
    console.log(sid);
});
```

Set the switch State ON (DECT200):
```js
var fritz = require('smartfritz');

fritz.setSwitchOn(sid, aid, function(sid){
    console.log(sid);
});
```

Set the switch State OFF (DECT200):
```js
var fritz = require('smartfritz');

fritz.setSwitchOff(sid, aid, function(sid){
    console.log(sid);
});
```

Get the phone list:
```js
var fritz = require('smartfritz');

fritz.getPhoneList(sid,function(calls){
    console.log(calls);
});

```

Enable or disable guest wlan:
```js
var fritz = require('smartfritz');

fritz.setGuestWLan(sid, true, function(enabled){
    console.log("Guest WLan Enabled: "+enabled);
});
```

Get guest wlan settings:
```js
var fritz = require('smartfritz');

fritz.getGuestWLan(sid, function(settings){
    console.log(settings);
});
```

## AHA-HTTP Interface

AHA - Avm Home Interface

https://fritz.box/webservices/homeautoswitch.lua?ain=<ain>&switchcmd=<cmd>&sid=<sid>

AHA-HTTP-Interface document 
http://avm.de/fileadmin/user_upload/Global/Service/Schnittstellen/AHA-HTTP-Interface.pdf

## Thanks to and based on Code from:

steffen.timm for the basic communication function
thk4711 for the FRITZ!DECT 200
AVM for providing the good AHA-HTTP-Interface document 

