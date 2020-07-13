# ModernFanControl - An Open Source Fan Control for the Macbook Pro

## Motivation:
### 1. Old and proprietary code
In terms of fan control software for the newer models of Macbook Pros, the options are quite scarce. Right now, the main two are **smcFanControl** and **Macs Fan Control**. The former hasn't been updated consistenly in nearly a decade, and the backend code it uses to write to the SMC is extremely deprecated, while the former is a paid app with very little technical support. The goal here is to open source a modern version of these types of software that can be supported for future updates of macOS. 

### 2. The 1200 problem
Both smcFanControl and Macs Fan control have a minimum fan speed of 1200rpm. This was fine, for the macs prior to 2017. However, in the T2 chipped current models, the fan often idles at 0 until the laptop hits 40C. This is an issue because running the fans at 1200 when they don't need to be on will add unnecessary strain to the fan bearings.  

## Installation:
