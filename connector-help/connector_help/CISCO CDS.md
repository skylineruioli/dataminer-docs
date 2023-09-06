---
uid: Connector_help_CISCO_CDS
---

# Cisco CDS

The **Cisco CDS** driver monitors a Cisco Systems manager unit through **SNMP**.

## About

The driver polls relevant information from the device every 10 seconds.

## Installation and Configuration

### Creation

#### SNMP Main Connection

This driver uses a Simple Network Management Protocol (SNMP) connection and requires the following input during element creation:

SNMP CONNECTION:

- **IP address/host**: The polling IPof the device.

SNMP Settings:

- **Port number**: The port of the connected device, by default *161.*
- **Get community** **string**: The community string used when reading values from the device, by default *public.*
- **Set community string**: The community string used when setting values on the device, by default *private.*

## Usage

This driver has three data display pages.

### Health Page

This page displays the **Disk Monitor**, **System Health Monitor** and **Interface Table**, as well as the **Server Master Slave Status**.

### Service Page

This page displays several tables: the **Services Monitor**, **RTSP Client**, **Linux File System Usage**, **Bandwidth Reporting Array** and **Routing Table**. It also displays the number of **Broken Assets**.

### Traps Page

This page displays single-trap parameters containing the information regarding the previous received trap: **Managed Service Architecture**, **Maximum Disk Usage Threshold**, **Maximum Port Loss Threshold**, **Setup IP**, **Control IP**, **Connection Failed**, and **Linux Partition**. You can clear each alarm by pressing the corresponding **Clear Alarm** button.