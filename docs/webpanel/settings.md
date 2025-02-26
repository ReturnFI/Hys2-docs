## Settings Page Description

<p align="center">
 <img src="https://github.com/user-attachments/assets/d125f1d9-4d79-4685-bc96-0d5a0eba7422" width="700" height="500">
</p>

---

#### Subscriptions Links

The `Subscriptions` tab includes two sub-tabs:

-   `SingBox` Subscription Link

    To activate the `SingBox` subscription link, you need a domain or subdomain and a free port on your server.

    Enter your domain or subdomain in the `Domain` field, and enter a free port number in the `Port` field. Then, wait a few moments for the required services to be installed and for the message `SingBox started successfully!` to be displayed.

-   `Normal` Subscription Link

    To activate the `Normal` subscription link, you need a domain or subdomain and a free port on your server.

   Enter your domain or subdomain in the `Domain` field, and enter a free port number in the `Port` field. Then, wait a few moments for the required services to be installed and for the message  `Normal subscription started successfully!` to be displayed.

---

### Telegram Bot

<p align="center">
 <img src="https://github.com/user-attachments/assets/3895c879-a1b9-4f91-be28-a0a3c202ec76" width="500" height="250">
</p>

-   To activate the Telegram bot, you need the following:
    -   Create a bot using the `@BotFather` bot and copy the bot token. Enter it in the `API Token` field.
    -   Get your Telegram account's numerical ID using the `@userinfobot` bot and enter it in the `Admin ID` field.

Then, click the `Start` button and wait for the message `Telegram bot started successfully!` to be displayed.

---

### Change Port

<p align="center">
 <img src="https://github.com/user-attachments/assets/9dbcea87-1bf8-4e7f-aa7c-6f1aa2f62c50" width="500" height="250">
</p>

In this section, you can change the port of the main `Hysteria2` service.

This port is for the main `Hysteria2` service, and if changed, users will need to update their configurations.

---

### Change SNI

<p align="center">
 <img src="https://github.com/user-attachments/assets/d827da74-a8cb-4323-aa42-dfbbb599834b" width="500" height="250">
</p>

Using this tab, you can change the `SNI` that you selected during installation.

Be aware that changing the `SNI` will change the `pinSHA256` values in the `config.json` file, and if users get disconnected, they will need to obtain the configuration again.

---

### Change IP

<p align="center">
 <img src="https://github.com/user-attachments/assets/b19f2ca7-23e6-4f9c-b424-1e6c5bc5ce30" width="500" height="250">
</p>

If you are using IP tunneling or floating, you can use this tab to change the `IP` values of your configurations.

-   `IPv4` field: Change the `IPv4` address of the configurations.
-   `IPv6` field: Change the `IPv6` address of the configurations.