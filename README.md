![icon](https://github.com/user-attachments/assets/e4436ac8-8583-4e6c-8258-eb4b96afbb59)![new_i](https://github.com/user-attachments/assets/edd27307-21e2-41c6-9b98-edfc4efd3f77)

![cropped-Adups-768x174-1](https://github.com/user-attachments/assets/a0f9d6c0-a7ee-4ef0-9a35-be00e9983659)
`com.adups.fota`


Another branch of iot version [com.abupdate.fota_demo_iot](https://github.com/harojpgyy/Get_Adups_FOTA/tree/abupdate.fota_demo_iot)


### Depends on the following properties

 
  * 
    ````
    ro_fota_oem（OEM code）
    ro_fota_device（Device Model）
    ro_product_locale（language)
    ro_fota_version（system version)
    ````
 You can use this adb command to get
       
       
    adb shell getprop
### Get Started
The script requires Python environment and tbm13-utils package, you can install it using pip

 ```
pip install tbm13-utils
 ```
Running scripts using Python3
```
python3 ota.py
 ```
 ![Script output when update is found](Examples.jpg)


 * According to the  `ro_fota_version ` attribute, the server provides ota.zip to upgrade from the current device version to the latest version（It may be an incremental package or a complete package）
   
* If your   `ro_fota_version `  is too old or does not exist, the server will most likely not return updates because the manufacturer has stopped supporting the device.
* To patch images, extract the OTA zip and use [imgpatchtools tools](https://github.com/erfanoabdi/imgpatchtools).

### Off topic: According to laboratory research, “adups” collect a large amount of user privacy indiscriminately
* Send encrypted cell site ID, MCC, MNC, IMEI, IMSI, MAC address, SIM serial number, phone number, and other device data to the server every 24 hours
* dc_app_flow.json – the order in which the user uses their applicaNons  
dc_msg_key.json - all text message send or received by the device with Nmestamps  
DcApp.json - list of applicaNons installed on the device  
DcAppOp.json - AppOps data (granted and denied permission)  
DcMobileStatus.json - minimal device diagnosNc data  
DcRootInfo.json - file lisNng of /system/bin and /system/xbin directories  
DcTellMessage.json - the user’s call log and text metadata with Nmestamps  
dc_browser_his.json - the user’s browser history
* Exploit vulnerabilities to escalate privileges and further obtain device information
* ........

You can choose to disable com.adups.fota, which keeps sending requests to the server and reduces battery life.
