# Home Assistant companion for Zepp OS devices
This application allows you to control your Home Assistant devices from your Zepp Watch!

![image](images/banner.png)

### Devices supported
- Mi Band 7
- Amazfit GTR 3 Pro
- Amazfit Cheetah Pro
- Amazfit Active

We are making changes in order to suppport more Zepp devices, if you have one ask for it in our [telegram community](https://t.me/aguacatec_es) 💬



### Preparations
#### Mi Band 7 only
- ~~[Modified Zepp App](https://4pda.to/forum/index.php?showtopic=797981&st=15700#entry122653549) (registration required)~~
- ~~You need to connect Mi Band 7 to Modified Zepp App the same way you would with Zepp Life (google auth is not  supported)~~
- You can use the official Zepp App, but have to create a custom QR code. Follow [this guide](https://habr.com/en/articles/699368/) for the URL of the QR code you have to adapt.
#### General steps
- Download the official Zepp App
- You need to enable [Developer Mode](https://docs.zepp.com/docs/1.0/guides/tools/zepp-app/) in Zepp app
- Build and install the ha-zepp application yourself using the [Zeus CLI](https://docs.zepp.com/docs/1.0/guides/tools/cli/)
- Open the application settings and specify the addresses of Home Assistant, Long-lived access token and select the sensors you want to display on Zepp OS device
#### Home Assistant
- Long-lived access token (you can generate it on your-ha-instance.local/profile page)
- "If you are not using the [`frontend`](https://www.home-assistant.io/integrations/frontend/) in your setup then you need to add the [`api` integration](https://www.home-assistant.io/integrations/api/) to your `configuration.yaml` file."

### About the sensor updates to the Home Assitant REST API
Since it is not possible for the general public to access [Huami's WEB API](https://github.com/zepp-health/rest-api/wiki), I decided to make a background updater within this app to send the wearable sensor data to Home Assistant.
It uses the [alarm](https://docs.zepp.com/docs/1.0/reference/device-app-api/hmApp/alarm/alarmNew/) mechanism, which can open a page even when the device is inactive. When this page is opened, the POST requests are performed towards the HA REST API. However, notifications on the device (e.g. app notifications or the calendar notification) are remained open for a while (if you don't swipe it away), which can block this alarm mechanism from showing the ha-zepp page. If the ha-zepp page is blocked by a notification, you will see that if you swipe it away, the ha-zepp page will appear. If you don't swipe it away, the ZeppOS system eventually will remove all stored pages and notifications to save RAM and be more power efficient. If this ha-zepp page is not openend, ha-zepp is unable to create a new alarm, meaning the background updater will break. Therefore, it's best to `DISABLE ALL SORT OF NOTIFICATIONS` if you want this feature to work properly.
