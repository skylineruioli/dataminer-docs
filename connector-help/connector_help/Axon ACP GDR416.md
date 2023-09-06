---
uid: Connector_help_Axon_ACP_GDR416
---

# Axon ACP GDR416

The GDR416 is a 4K, 3 Gb/s, HD and SD 4 input distribution amplifier with 4 reclocked outputs per channel.

The **Axon ACP GDR416** driver can be used to display and configure information related to this device.

## About

This driver can be automatically generated by the driver **Axon ACP**.

There are different possibilities available for **alarm monitoring** and **trending**.

### Version Info

| **Range** | **Key Features**             | **Based on** | **System Impact** |
|-----------|------------------------------|--------------|-------------------|
| 1.0.0.x   | Initial version \[SLC Main\] | \-           | \-                |

### Product Info

| **Range** | **Supported Firmware** |
|-----------|------------------------|
| 1.0.0.x   | 0100, 0200, 0300       |

### System Info

| **Range** | **DCF Integration** | **Cassandra Compliant** | **Linked Components** | **Exported Components** |
|-----------|---------------------|-------------------------|-----------------------|-------------------------|
| 1.0.0.x   | Yes                 | Yes                     | \-                    | \-                      |

## Installation and configuration

### Creation

The element using this driver can be automatically created by the parent element using the **Axon ACP** driver, but it can also be a standalone element.

### Connections

#### Serial Main Connection

This driver uses a serial connection and requires the following input during element creation:

SERIAL CONNECTION:

- Interface connection:

- **IP address/host**: The polling IP or URL of the destination.
  - **Bus address**: The bus address of the device, being the slot number of the card.

#### Serial Broadcast Connection

This driver uses a serial connection and requires the following input during element creation:

SERIAL CONNECTION:

- Interface connection:

- **IP address/host**: The polling IP or URL of the destination.
  - **Bus address**: The bus address of the device.

## Usage

This element has the following data pages:

- **General**: This page displays general information about the card: **Card Name**, **Card Description**, **SW Revision**, **HW Revision**, etc.
- **SFP**
- **Status**
- **Settings**
- **HDMI**
- **Alarm Priority**: This page displays the event messages of the card, i.e. special messages generated asynchronously on the card.

## DataMiner Connectivity Framework

The Axon ACP protocol supports the usage of DCF and can only be used on a DMA with **8.5.4** as the minimum version.

DCF can also be implemented through the DataMiner DCF user interface and through DataMiner Third Party protocols (for instance a manager).

### Interfaces

#### Physical Interfaces

- **SDI Input A**: A single fixed interface of type **input**.
- **SDI Input B**: A single fixed interface of type **input**.
- **SDI Input C**: A single fixed interface of type **input**.
- **SDI Input D**: A single fixed interface of type **input**.
- **SDI Output A1**: A single fixed interface of type **output**.
- **SDI Output A2**: A single fixed interface of type **output**.
- **SDI Output A3**: A single fixed interface of type **output**.
- **SDI Output A4**: A single fixed interface of type **output**.
- **SDI Output B1**: A single fixed interface of type **output**.
- **SDI Output B2**: A single fixed interface of type **output**.
- **SDI Output B3**: A single fixed interface of type **output**.
- **SDI Output B4**: A single fixed interface of type **output**.
- **SDI Output C1**: A single fixed interface of type **output**.
- **SDI Output C2**: A single fixed interface of type **output**.
- **SDI Output C3**: A single fixed interface of type **output**.
- **SDI Output C4**: A single fixed interface of type **output**.
- **SDI Output D1**: A single fixed interface of type **output**.
- **SDI Output D2**: A single fixed interface of type **output**.
- **SDI Output D3**: A single fixed interface of type **output**.
- **SDI Output D4**: A single fixed interface of type **output**.

#### Virtual Interfaces

- **Reclocker A**: A single fixed interface of type **inout**.
- **Reclocker B**: A single fixed interface of type **inout**.
- **Reclocker C**: A single fixed interface of type **inout**.
- **Reclocker D**: A single fixed interface of type **inout**.

### Connections

#### Internal Connections

When a DVE child element is created, the following connections are established:

- Between **SDI Input A** and **Reclocker A**.
- Between **Reclocker A** and **SDI Output A1**.
- Between **Reclocker A** and **SDI Output A2**.
- Between **Reclocker A** and **SDI Output A3**.
- Between **Reclocker A** and **SDI Output A4**.
- Between **SDI Input B** and **Reclocker B**.
- Between **Reclocker B** and **SDI Output B1**.
- Between **Reclocker B** and **SDI Output B2**.
- Between **Reclocker B** and **SDI Output B3**.
- Between **Reclocker B** and **SDI Output B4**.
- Between **SDI Input C** and **Reclocker C**.
- Between **Reclocker C** and **SDI Output C1**.
- Between **Reclocker C** and **SDI Output C2**.
- Between **Reclocker C** and **SDI Output C3**.
- Between **Reclocker C** and **SDI Output C4**.
- Between **SDI Input D** and **Reclocker D**.
- Between **Reclocker D** and **SDI Output D1**.
- Between **Reclocker D** and **SDI Output D2**.
- Between **Reclocker D** and **SDI Output D3**.
- Between **Reclocker D** and **SDI Output D4**.