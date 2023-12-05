**ESB-BLE-Timeslot**

Overview
********
This example shows how to run the BLE and ESB protocols concurrently using the MPSL interface (previously known as the timeslot interface). 
The example runs a basic Bluetooth peripheral based on the peripheral_lbs sample, and uses MPSL to request timeslots when the Bluetooth stack is idle during which ESB communication can be scheduled. 
The example can run ESB in either PTX or PRX mode, and is compatible with the standard ESB PTX/PRX samples.  

Requirements
************

- nRF Connect SDK v2.5.0
- nRF5340 development kit
- ptx and prx build for nrf5340 netcore, the peripheral_lbs_app build for nrf5340 app core.
- A conflict between the ESB library and MPSL, since they are both configured to use the SWI0 interrupt in the nRF5340. In order to fix this it is necessary to change esb_peripherals.h, and modify the SW0 to SW3. 