# Introduction
This topology integrates an Access Point (AP) into the original FRRouting (FRR) topology. The AP is connected as follows:

**AP --> enp0s25 --> br0 --> router8:eth3**

# AP Configuration
- **SSID**: Zee123  
- **Password**: Cisco123  
- **IP Address**: 172.22.228.244/24  

# Preparation Steps
Follow these steps to set up your environment:

1. **Connect the AP**  
   Connect the AP's switch side to your workstation's Ethernet interface.

2. **Connect your client**  
   Connect your client device (laptop, mobile phone) to the SSID. Manually set the IP address:
   - **IP Address**: 172.22.228.21/24  
   - **Gateway**: 172.22.228.1  

3. **Create a bridge on your host laptop**  
   Run the following command to create a bridge:
   ```bash
   sudo brctl addbr br0
4. **Connect the Ethernet interface to the bridge
   Use this command to add your Ethernet interface to the bridge:
   ```bash
   sudo brctl addif br0 ens0p25
5. **Add a route to the bridge
   Finally, add the route into the bridge using::
   ```bash
   sudo ip route add 172.22.228.0/24 dev br0

