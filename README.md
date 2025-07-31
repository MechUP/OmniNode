# OmniNode

OmniNode is a lightweight, self-hosted server application for managing OPC UA, MQTT, and REST API endpoints via a web interface.

## Prerequisites

* **.NET 8.0 Runtime** installed on your machine.
  Download: [https://dotnet.microsoft.com/download](https://dotnet.microsoft.com/download)
* Windows, Linux, or macOS.
* A modern web browser (Chrome, Edge, Firefox, etc.).

## Installation & Setup

**Download** and extract it to a directory of your choice (e.g., `C:\Software\OmniNode`).

## Running the Server

### Windows (framework-dependent)

1. Launch the server:

   ```bash
   OmniNode.exe
   ```

2. The console will display the listening URLs, for example:

   ```text
       >> OmniNode Server is running at:
       >> https://localhost:5151
       >> http://localhost:5150
   ```

3. Open your browser and navigate to one of the listed URLs (HTTPS is recommended if you have a valid certificate).

### Linux/macOS (framework-dependent)

1. Ensure the .NET 8.0 runtime is installed on your machine. On Debian/Ubuntu:

   ```bash
   wget https://packages.microsoft.com/config/ubuntu/22.04/packages-microsoft-prod.deb
   sudo dpkg -i packages-microsoft-prod.deb
   sudo apt update && sudo apt install -y dotnet-runtime-8.0
   ```

2. Copy your published output (containing `OmniNode.dll`) to the target system, for example:

   ```bash
   scp -r bin/Release/net8.0/linux-x64/publish/ user@linux:/opt/omninode
   ```

3. On the Linux/macOS host, run:

   ```bash
   cd /opt/omninode
   dotnet OmniNode.dll
   ```

4. The console will display the listening URLs as shown above.

## Logging In

By default, there are no users configured. The first time you visit the app, log in with the built-in administrative account:

| Username | Password |
| -------- | -------- |
| `admin`  | `admin`  |

> **Security note**: Be sure to change the default password or disable the built-in account in production.

## Using OmniNode

Once logged in, you can:

1. **Configure and start an OPC UA server**

   * Go to **OPC UA**
   * Specify port, node configuration, etc.
   * Click **Launch Server** to start.

2. **Configure and start an MQTT server**

   * Go to **MQTT**
   * Specify host, port, and topic configurations.
   * Click **Launch Server** to start.

3. **Configure and start a REST API server**

   * Go to **REST API**
   * Enter base URL, port, authentication key, and endpoint definitions.
   * Click **Launch Server** to start.

4. **Monitor Server Status**

   * The dashboard shows the current status and URL of each server.

That’s it—once configured, your servers will be available at the specified ports and endpoints.

## Stopping the Server

* Click the **Stop Server** button on the respective page.
* Or press **Ctrl+C** in the console to shut down all servers and exit.

## Support & Feedback

For questions or to request features, please email: [contact@mechup.net](mailto:contact@mechup.net)

---

© 2025 OmniNode / MechUP. All rights reserved.
