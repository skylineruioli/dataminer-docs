---
uid: Connector_help_Evertz_7x00_General_Platform_-_7746FSHD
---

# Evertz 7x00 General Platform - 7746FSHD

This driver is used to monitor an Evertz 7746FSHD card. The 7746FSHD card is a frame syncronizer.

## About

This driver is automatically generated by driver [Evertz 7x00 General Platform](xref:Connector_help_Evertz_7x00_General_Platform).

### Supported firmware versions

| **Driver Range** | **Device Firmware Version** |
|------------------|-----------------------------|
| 1.0.0.x          | (unknown)                   |

## Installation and configuration

### Creation

The element using this driver is automatically exported from the **Evertz 7x00 General Platform** driver. The configuration of the element must be done in this parent driver.

It's default name will be 7746FSHD.x where x is the slot which the card is attached.

## Usage

### General

This page displays card data and **AFD** information. i.e. **Slot number, card type, card status**, etc.

### Video

This page displays **Video** information: **format, aspect, format detected**, etc.

### Audio

This page displays **Audio** information and also a Channels table: **processing, inversion, delay**, etc.

### Line Blanking

This page displays a table with all **line blanking** information.

### Alarms

This page displays all alarms of this card: **Video, AES, Demux, IntelliGain** and **SCTE**. For each alarm, the **Send Trap** parameter allows you to enable/disable traps for that fault.