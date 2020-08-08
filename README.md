# ModernFanControl - An Open Source Fan Control for the Macbook Pro

## Motivation:
### 1. Old and proprietary software
In terms of fan control software for the newer models of Macbook Pros, the options are quite scarce. Right now, the main two are **smcFanControl** and **Macs Fan Control**. The former hasn't been updated consistenly in nearly a decade, and the backend code it uses to write to the SMC is extremely deprecated, while the former is a paid app with very little technical support. The goal here is to open source a modern version of these types of software that can be supported for future updates of macOS. 

### 2. The 1200 problem
Both smcFanControl and Macs Fan control have a minimum fan speed of 1200rpm. This was fine, for the macs prior to 2017. However, in the T2 chipped current models, the fan often idles at 0 until the laptop hits 40C. This is an issue because running the fans at 1200 when they don't need to be on will add unnecessary strain to the fan bearings.  

## Installation:



## Example Usage:
For now, only the `smc.c` has been developed, thanks to [smcFanControl](https://github.com/hholtmann/smcFanControl) and especially [this guy](https://github.com/Blaisorblade), who just provided the first working version in a while. Navigate to the downloaded folder and run the following:
```shell
make

# To get the list of fan keys (will vary by model)
sudo ./smc -l | grep F.Tg

# Set the fans in force mode to control speed 
# Replace the keys with the keys found above
sudo ./smc -k F0Md -w 01
sudo ./smc -k F1Md -w 01

# Set the fan speed to 3000 rpm
sudo ./smc -k F0Tg -p 3000
sudo ./smc -k F1Tg -p 3000

# To stop, return to auto mode 
sudo ./smc -k F0Md -w 00
sudo ./smc -k F1Md -w 00

```

