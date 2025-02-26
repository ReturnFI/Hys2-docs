# Advanced Menu

---

<p align="center">

<img src="https://github.com/user-attachments/assets/417cc9ce-d460-46c0-8e2f-0b163af41b29" width="700" height="400">
</p>

## Description
---

### 1. Install TCP Brutal

**What is TCP Brutal?**

TCP Brutal is a congestion control algorithm for the TCP protocol.  In simpler terms, it attempts to increase data transfer speeds on TCP networks, especially in situations with limited or unstable bandwidth.  It achieves this by intelligently managing the amount of data sent at any given time.

*   **Note:** Congestion control algorithms are crucial for network performance.  TCP Brutal is likely a less common, potentially more aggressive algorithm compared to standard ones like Cubic or Reno.  It's important to understand the potential impact on network stability before deploying this.  It might be beneficial in high-latency or lossy networks.

---

### 2. Install WARP

**What is WARP?**

WARP is a service provided by Cloudflare that uses the WireGuard protocol to create a secure and fast tunnel between your server and the internet. Simply put, WARP adds an extra layer of security to your connection and routes your internet traffic through Cloudflare's servers.

*   **Note:** This leverages WireGuard, a modern, high-performance VPN protocol.  The key benefit here is routing through Cloudflare's network, which can offer performance and security advantages (DDoS protection, potentially faster routing). It acts as a VPN, masking the user's original IP.

---

### 3. Configure WARP

This option has a submenu:

```
--------------------------------
Current WARP Configuration:
All traffic: Inactive
Popular sites (Google, Netflix, etc.): Inactive
Domestic sites (geosite:ir, geoip:ir): Inactive
Block adult content: Inactive
--------------------------------
Configure WARP Options:
1. Use WARP for all traffic
2. Use WARP for popular sites
3. Use WARP for domestic sites
4. Block adult content
5. WARP (Plus) Profile
6. WARP (Normal) Profile
7. WARP Status Profile
8. Change IP address
0. Cancel
Select an option:
```

*   **First Section:** Displays the current WARP configuration.
*   **Option 1:** Route all traffic through WARP. (Full VPN mode)
*   **Option 2:** Route traffic for popular sites (e.g., Google, ChatGPT, Netflix) through WARP. (Selective routing)
*   **Option 3:** Route traffic for domestic (Iranian) sites through WARP. (Geo-specific routing - important for bypassing potential local restrictions)
    *   **Developer Note:** `geosite:ir` and `geoip:ir` likely refer to lists of Iranian websites and IP addresses, respectively.  This suggests the script uses GeoIP/Geosite databases for routing decisions.
*   **Option 4:** Block adult content. (Content filtering)
*   **Option 5:** Switch to a WARP Plus profile.
    *   Requires a WARP Plus key. (This implies a paid tier with potentially better performance or features.)
*   **Option 6:** Switch to a normal (free) WARP profile.
*   **Option 7:** Display WARP profile information and the WARP IP address.
*   **Option 8:** Change the WARP IP address. (Likely rotates to a new Cloudflare IP.)

---

### 4. Uninstall WARP

Selecting this option will remove WARP and its configuration from the server.

---

### 5. Telegram Bot

This option has a submenu:

```
1. Start Telegram bot service
2. Stop Telegram bot service
0. Back
```

*   **Option 1:** Activate the Telegram bot.
    *   To activate the bot, you need to create a bot using `@BotFather` and obtain a bot token.
    *   Use `@userinfobot` to get the numerical ID of your Telegram account.
    *   If you have multiple accounts or admins, you can use a comma (`,`) to enter multiple numerical IDs.

    Example:

    ```
    Enter the Telegram bot token: 9517664116:ABDcYVBVKJHUJCasVjwXtPyQw_eQW9bCl0
    Enter the admin IDs (comma-separated): 1562023210,1871475213
    ```

    *   **Note:** This integrates Telegram bot functionality, likely for remote control, monitoring, or notifications related to the Hysteria server.  The token is the bot's API key, and the admin IDs control who can interact with the bot.

*   **Option 2:** Remove the Telegram bot.

---

### 6. SingBox SubLink

This option has the following submenu:

```
1. Start Singbox service
2. Stop Singbox service
0. Back
```

* **Option 1:** Activate the SingBox subscription link.
    * Requires a domain or subdomain to activate the subscription link.
    * Allows you to choose a port for activating the subscription link.
* **Option 2:** Deactivate the subscription and remove the certificate files related to the domain.

**Note:** This feature uses the `certbot` service to obtain an SSL certificate for the domain.

---

### 7. Normal-SUB SubLink

This option has the following submenu:

```
1. Start Normal-Sub service
2. Stop Normal-Sub service
0. Back
```

*   **Option 1:** Activate the normal subscription link.
    *   Requires a domain or subdomain to activate the subscription link.
    *   Allows you to choose a port for activating the subscription link.

*   **Option 2:** Deactivate the subscription and remove the certificate files related to the domain.

**Note:** This feature uses the `certbot` service to obtain an SSL certificate for the domain.

---

### 8. Web Panel

After selecting this option, the following submenu will be displayed:

```
Services Status:
hysteria-webpanel.service: Inactive
hysteria-caddy.service: Inactive

1. Start WebPanel service
2. Stop WebPanel service
3. Get WebPanel URL
4. Show API Token
0. Back
```

*   **Services Status:** Indicates whether the web panel services are active or inactive.

**Note:** The web panel uses the `caddy` service. If you have other services like `nginx` or `apache`, the web panel may encounter issues.

*   **Note:**  This is a crucial point.  `caddy`, `nginx`, and `apache` are all web servers, and they often conflict if they try to use the same ports (usually 80 and 443).  This warns the user to avoid conflicts.

1.  **Start WebPanel service:**

    After selecting this option, you will be prompted for the following values, in order:

    *   **Enter the domain name for the SSL certificate:**

        Enter your domain or subdomain name without `https://`.

    *   **Enter the port number for the service:**

        After entering the domain, you will be asked for the port number to run the web panel service.

        Use non-standard and unused ports, for example, `8443`.

    *   **Enter the admin username:**

        Enter the administrator username.

    *   **Enter the admin password:**

        Enter a password for the administrator (use a strong password).

    Then, wait a few minutes for the necessary packages and services to be installed. Finally, the panel login address will be displayed as follows:

    ```
    Hysteria web panel is now running.
    The service is accessible on: https://example.com:8443/8b3dc8o7w4d5djg77t85r7c84e8assvc/
    ```
    * **Note:** The random string at the end of the URL (`8b3dc8o7w4d5djg77t85r7c84e8assvc/`) is likely a security measure to prevent unauthorized access to the panel. It's a good practice.

2.  **Stop WebPanel service:**

    After selecting this option, the web panel service will be deactivated and removed.

3.  **Get WebPanel URL:**

    If needed, you can get the panel login address with this option.

4.  **Show API Token:**

    If you want to use the API designed for the panel, you need to authenticate using a token.

    This option displays the API token for your panel.

    *   **Note:**  Having an API is excellent for automation and integration with other systems.  Token-based authentication is standard practice for API security.

---

### 9. Change Port (Hysteria2)

After selecting this option, you will be prompted for a new port.

This port is for the main `Hysteria2` service, and if changed, users need to update their configurations.

*   **Note:**  This is the core port that Hysteria2 listens on for client connections.  Changing it requires client-side updates.

---

### 10. Change SNI (Hysteria2)

Using this option, you can change the `SNI` you selected during installation.

Be aware that changing the `SNI` will change the `pinSHA256` values in the `config.json` file, and if users are disconnected, they need to get the configuration again.

*   **Note:**  SNI (Server Name Indication) is used in TLS to allow a server to present multiple certificates on the same IP address and port.  Changing the SNI affects the TLS handshake.  `pinSHA256` is likely a certificate pinning mechanism, adding an extra layer of security by verifying the server's certificate against a known hash.

---

### 11. Manage OBFS

This option has the following submenu:

```
1. Remove Obfs
2. Generating new Obfs
0. Back
```

*   **Option 1. Remove Obfs:** Removes the `obfs` section from the `config.json` file.  Some software does not support `obfs`.

    **Note:** It is recommended not to remove `obfs`.

    ```json
      "obfs": {
        "type": "salamander",
        "salamander": {
          "password": "qyZE9t4VpqgblQCBtbjIBjdFByEe3AIK"
        }
      }
    ```

    *   **Note:**  `obfs` stands for obfuscation.  This is a technique to make the VPN traffic look like something else (in this case, "salamander" is likely a specific obfuscation method) to evade detection by firewalls or DPI (Deep Packet Inspection).  The password is used in the obfuscation process.

*   **Option 2. Generating new Obfs:** Activate and regenerate `obfs`.

    **Note:** If you remove `obfs` and reactivate it, the values in the `password` section will change, and users need to get the configuration again.

---

### 12. Change IPs (4-6)

If you are using IP tunneling or floating, you can use this option to change the `IP` values of your configurations.

This option has the following submenu:

```
1. Change IP4
2. Change IP6
0. Back
```

*   **Option 1:** Change the IPv4 address in the configurations.
*   **Option 2:** Change the IPv6 address in the configurations.

*   **Note:** This allows for updating the IP addresses used for tunneling, which is essential if the server's IP changes or if you're using a floating IP setup.

---

### 13. Update geo Files

`geo` files are used for better routing and traffic control.

This option has the following submenu:

```
Configure Geo Update Options:
1. Update Iran Geo Files
2. Update China Geo Files
3. Update Russia Geo Files
4. Check Current Geo Files
0. Cancel
```

*   **Option 1:** Updates `geoip.dat` and `geosite.dat` using the [`Chocolate4U`](https://github.com/Chocolate4U/Iran-v2ray-rules) project.
*   **Option 2:** Updates `geoip.dat` and `geosite.dat` using the [`Loyalsoldier`](https://github.com/Loyalsoldier/) project. This project is for GeoIP/Geosite data for Chinese websites and is not useful for Iran.
*   **Option 3:** Updates `geoip.dat` and `geosite.dat` using the [`runetfreedom`](https://github.com/runetfreedom/) project. This project is for GeoIP/Geosite data for Russian websites and is not useful for Iran.
*   **Option 4:** Displays the size and last modified date and time of the `geo` files.

*   **Note:**  This is crucial for geo-based routing.  `geoip.dat` and `geosite.dat` are commonly used files (likely in MaxMind's format) that contain IP address to location mappings and domain to country mappings, respectively.  The different projects provide curated lists for specific regions. Keeping these files updated is important for accurate routing.

---

### 14. Manage Masquerade

One of Hysteria's key strengths in resisting censorship is its ability to pretend to be standard HTTP/3 traffic. This means that not only are packets seen as HTTP/3 by intermediary equipment, but the server also responds to HTTP requests like a normal web server. However, this means that your server must actually serve content to appear legitimate to potential censors.

**Note:** We use the proxy method, which acts as a reverse proxy and serves content from another website.

This option has a submenu:

```
1. Enable Masquerade
2. Remove Masquerade
0. Back
```
* **Option 1:** Enable masquerade.
  - You need the domain of a site, like the SNI you are using, for activation.
* **Option 2:** Disable masquerade.

*   **Note:** This is a sophisticated anti-censorship technique.  By acting as a reverse proxy, Hysteria makes its traffic look like regular web browsing to a legitimate website.  This makes it very difficult for censors to block without also blocking the masqueraded website.

---

### 15. Restart Hysteria2

Using this option, you can restart the Hysteria2 service.

The difference between this option and the direct command `systemctl restart hysteria-server.service` is in collecting the last-minute traffic of users before restarting.

If you use the `systemctl restart hysteria-server.service` command, the user's instantaneous traffic is not saved, and it is better to restart the service from within the menu.

*   **Note:** This highlights a crucial detail: the script's restart function likely handles graceful shutdown and data persistence (saving traffic statistics) better than a raw `systemctl` command.

---

### 16. Update Core (Hysteria2)

After running this option, the `Hysteria2` core will be updated to the latest version.

---

### 17. Uninstall Script (Hysteria2)

After selecting this option, all services and files related to the script and core will be removed.
