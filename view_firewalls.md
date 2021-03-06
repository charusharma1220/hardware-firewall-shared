---

copyright:
  years: 2017
lastupdated: "2018-11-12"

---

{:shortdesc: .shortdesc}
{:new_window: target="_blank"}
{:codeblock: .codeblock}
{:pre: .pre}
{:screen: .screen}
{:tip: .tip}
{:download: .download}

# View your Firewalls 

You can identify the firewalls in use on an account and their associated VLANs, as well as identify unprotected VLANs and plan the deployment of a firewall solution.

## Firewall Overview by VLAN

To get an overview of firewalls on your system, as well as initiate basic management, navigate to **Network > IP Management > VLANs** in the [Customer Portal ![External link icon](../../icons/launch-glyph.svg "External link icon")](https://control.softlayer.com/){: new_window}.

**NOTE:** To view only public VLANS, click on the **Filter** drop down and enter ``fcr`` for **Primary Router**. 

Each row represents a VLAN in your infrastructure.  IBM Cloud populates the **VLAN NUMBER** and **PRIMARY ROUTER** information automatically indicating the true VLAN number and the router that it is configured on. Use the **NAME** field to define a recognizable name. 

The **GATEWAY/FIREWALL** column contains details about which hardware firewall protection is in place, for example:

**Add Firewall** indicates that there are no firewalls in place for servers on this VLAN.

**Individually Protected Servers** indicates that one or more servers is utilizing a Hardware Firewall (Shared) and that there is not a Hardware Firewall (Dedicated), FortiGate Security Appliance, or Network Gateway in place. VLAN firewalls and network gateways are not able to be placed on a VLAN that has individually protected servers.

**Firewall-vlanXXXX.networklayer.com** indicates that there is a Hardware Firewall (Dedicated) or FortiGate Security Appliance in place. Only one VLAN firewall or Network Gateway can be associated with a VLAN, but a server can be protected on the public VLAN by a VLAN firewall and associated on the private network with a Network Gateway.

**GatewayName** indicates the VLAN is associated with that Network Gateway.

## Individually Protected Servers View

On the VLANs screen, identify a row with **Individually Protected Servers** in the **Gateway/Firewall** column and click on the associated VLAN number link. This will display the details for the VLAN including the associated devices.

From here, you can click on each device and review whether a firewall is in place for that particular Server.

Once you have clicked on a device, scroll to the bottom of the Configuration tab. You will see **Firewall** in the addons section with **Installed** or **Not Installed** for the status. **Not Installed** indicates that no firewall is in place for this device. **Installed** indicates that a firewall is in place and you will have a **Firewall** tab available on the device where you can manage the firewall configuration.

## Dedicated Firewall View

On the VLANs screen, identify a row with **Firewall-vlanXXXX.networklayer.com** in the **Gateway/Firewall** column and click on that firewall. You are presented with either a Hardware Firewall (Dedicated) or a FortiGate Security Appliance. The device details include the associated Router, VLAN, and IPv4/IPv6 Subnets, the devices associated with that VLAN, and the controls for routing traffic through or around the firewall.

**FortiGate Security Appliance** devices will have the management IP, username, and password.  Management is completed through the management GUI or SSH-based console.

## Network Gateway View

On the VLANs screen, identify a row with the **Gateway/Firewall** column populated by a Network Gateway device name and click on that network gateway. You are then taken to the interface displaying associated frontend (FCR) and backend (BCR) VLANs and Network Gateway management options.
