# OmniNode

OmniNode is a lightweight, self-hosted industrial data platform for connecting OPC UA, MQTT, and REST API sources, collecting their data, and viewing it through a unified web interface.

It is designed to provide a simple way to connect industrial systems, store machine and process data, and access that data without deploying a full MES platform.

## Prerequisites

* Windows, Linux, or macOS.
* A modern web browser such as Chrome, Edge, or Firefox.

## Installation & Setup

Download the latest OmniNode release and extract it to a directory of your choice, for example:

```text
C:\Software\OmniNode
```

Latest release:

https://github.com/MechUP/OmniNode/releases/latest

## Running the Server

### Windows

1. Launch OmniNode:

   ```bash
   OmniNode.exe
   ```

2. The console will display the available web interface URLs, for example:

   ```text
   >> OmniNode Server is running at:
   >> https://localhost:5151
   >> http://localhost:5150
   ```

3. Open one of the displayed URLs in your web browser.

> HTTPS is recommended when OmniNode is exposed outside a trusted local network and a valid certificate is configured.

### Linux/macOS

1. Ensure the **.NET 10.0 Runtime** is installed on the target machine.

   Installation instructions for your operating system are available from:

   https://dotnet.microsoft.com/download/dotnet/10.0

2. Copy the published OmniNode files containing `OmniNode.dll` to the target system, for example:

   ```bash
   scp -r bin/Release/net10.0/linux-x64/publish/ user@linux:/opt/omninode
   ```

3. On the Linux/macOS host, navigate to the OmniNode directory:

   ```bash
   cd /opt/omninode
   ```

4. Start OmniNode:

   ```bash
   dotnet OmniNode.dll
   ```

5. The console will display the available web interface URLs.

## Logging In

The first time you start OmniNode, you can log in using the built-in administrative account:

| Username | Password |
| -------- | -------- |
| `admin`  | `admin`  |

> **Security note:** Change the default administrator password before using OmniNode in a production environment.

## Using OmniNode

Once logged in, OmniNode allows you to configure industrial data interfaces and inspect collected data from a single web interface.

### 1. OPC UA

Go to **OPC UA** to configure and start the OPC UA server.

You can:

* Configure the server settings and port.
* Define OPC UA nodes.
* Start and stop the OPC UA server.
* Monitor the current server status.

### 2. MQTT

Go to **MQTT** to configure and start the MQTT server.

You can:

* Configure the MQTT host and port.
* Configure topics.
* Start and stop the MQTT server.
* Monitor the current server status.

### 3. REST API

Go to **REST API** to configure and start the REST API server.

You can:

* Configure the base URL and port.
* Configure authentication settings.
* Define API endpoints.
* Start and stop the REST API server.
* Monitor the current server status.

### 4. Server Status

The dashboard provides an overview of the currently configured services and their status.

This makes it possible to quickly verify whether the OPC UA, MQTT, and REST API services are running and reachable.

### 5. DataViewer

The **DataViewer** provides a unified view of data collected by OmniNode.

You can:

* View stored data from OPC UA, MQTT, and REST API sources in one place.
* Filter data by tag.
* Filter data by date and time range.
* Inspect historical machine and process data.
* Review data without connecting directly to each individual source system.

This allows OmniNode to act as a central data layer between industrial equipment and higher-level applications.

## Typical Architecture

```text
PLC / Machine / Industrial Device
              |
              |
      OPC UA / MQTT / REST
              |
              v
          OmniNode
              |
      +-------+-------+
      |               |
      v               v
 Local Storage     DataViewer
      |
      v
External Systems / Applications
```

OmniNode can therefore be used as a lightweight industrial data platform for collecting, storing, and exposing machine and process data without requiring a full MES implementation.

## Stopping OmniNode

To stop an individual service:

* Open the corresponding OPC UA, MQTT, or REST API page.
* Click **Stop Server**.

To shut down OmniNode completely:

```text
Ctrl+C
```

in the console running the application.

## Support & Feedback

Questions, bug reports, and feature requests are welcome.

Email:

[contact@mechup.net](mailto:contact@mechup.net)

GitHub releases:

https://github.com/MechUP/OmniNode/releases

---

© 2026 OmniNode / MechUP. All rights reserved.
