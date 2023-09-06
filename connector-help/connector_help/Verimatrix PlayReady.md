---
uid: Connector_help_Verimatrix_PlayReady
---

# Verimatrix PlayReady

This driver displays and monitors the configuration and general information of the **Verimatrix PlayReady** **playout server.**

## About

The Verimatrix PlayReady driver retrieves general and configuration information from the device through **SNMP**. It captures traps and displays alarms on important parameters if these occur.

### Ranges of the driver

| **Driver Range** | **Description** | **DCF Integration** | **Cassandra Compliant** |
|------------------|-----------------|---------------------|-------------------------|
| 1.0.0.1          | Initial version | No                  | Yes                     |

### Supported firmware versions

| **Driver Range** | **Device Firmware Version** |
|------------------|-----------------------------|
| 1.0.0.1          | v3.6                        |

## Installation and configuration

### Creation

#### SNMP Main Connection

This driver uses a Simple Network Management Protocol (SNMP) connection and requires the following input during element creation:

SNMP CONNECTION:

- **IP address/host**: The IP address of the device, e.g. *194.206.71.180.*

SNMP Settings:

- **Port number**: The port of the connected device, by default *161*.
- **Get community string**: The community string used when reading values from the device, e.g. *public.*
- **Set community string**: The community string used when setting values on the device, e.g. *private.*

## Usage

### Overview

This page displays **Device Info** and information on the device **Configuration**. Alarm monitoring is possible on the most important parameters.