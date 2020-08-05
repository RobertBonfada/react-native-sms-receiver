# react-native-sms-receiver
A package that creates a broadcast receiver of SMS

```html
<style>.bmc-button img{height: 34px !important;width: 35px !important;margin-bottom: 1px !important;box-shadow: none !important;border: none !important;vertical-align: middle !important;}.bmc-button{padding: 7px 15px 7px 10px !important;line-height: 35px !important;height:51px !important;text-decoration: none !important;display:inline-flex !important;color:#ffffff !important;background-color:#FF813F !important;border-radius: 8px !important;border: 1px solid transparent !important;font-size: 24px !important;letter-spacing:0.6px !important;box-shadow: 0px 1px 2px rgba(190, 190, 190, 0.5) !important;-webkit-box-shadow: 0px 1px 2px 2px rgba(190, 190, 190, 0.5) !important;margin: 0 auto !important;font-family:'Cookie', cursive !important;-webkit-box-sizing: border-box !important;box-sizing: border-box !important;}.bmc-button:hover, .bmc-button:active, .bmc-button:focus {-webkit-box-shadow: 0px 1px 2px 2px rgba(190, 190, 190, 0.5) !important;text-decoration: none !important;box-shadow: 0px 1px 2px 2px rgba(190, 190, 190, 0.5) !important;opacity: 0.85 !important;color:#ffffff !important;}</style><link href="https://fonts.googleapis.com/css?family=Cookie" rel="stylesheet"><a class="bmc-button" target="_blank" href="https://www.buymeacoffee.com/robertbonfada"><span style="margin-left:5px;font-size:24px !important;">Buy me a coffee</span></a>
```

## Installation 🚀 
```bash
#yarn
yarn add react-native-sms-receiver

#npm
npm install react-native-sms-receiver
```

Then, import with:

```js
import { requestReadSMSPermission, startReadSMS} from 'react-native-sms-receiver/Receiver';
```

## Usage

Example:

```js
import React, { useEffect } from "react";
import { Text, View } from "react-native";
import { requestReadSMSPermission, startReadSMS} from 'react-native-sms-receiver/Receiver';

export default function App() {
  const startReadingMessages = async () => {
    const hasPermission = await requestReadSMSPermission();
    if(hasPermission) {
      startReadSMS((status: any, sms: any, error: any) => {
        if (status == "success") {
          console.log("Great 🤠 !! you have received new sms:", sms);
        }
      });
    }
  }

  useEffect(() => {
    startReadingMessages();
  }, [])

  return (
    <View>
      <Text>🛸</Text>
    </View>
  );
}
```
