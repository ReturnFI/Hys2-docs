# Telegram Bot

## Activation Tutorial

You can activate the Telegram bot by following the instructions in this [link](https://returnfi.github.io/Hys2-docs/menu/advance-menu/#5-telegram-bot).

After activation, go to your Telegram and `start` the bot.

Once the bot is started, the menu will be displayed:

<p align="center">

<img src="https://github.com/user-attachments/assets/6dc5fc29-0dbb-4729-9757-dca4388c0404" width="300" height="500">
</p>

----

## Add User

After clicking the `Add User` button, you will be prompted for the following values, in order:

### 1. Enter Username

Choose a username for the user.  Use only letters and numbers.

*   **Developer Note:** This restriction is likely for simplicity and to avoid issues with special characters in filenames or database entries.

### 2. Enter traffic limit (GB)

Enter the user's traffic limit in gigabytes (numbers only).

Example: `30`

### 3. Enter expiration days

Enter the number of days the user's account will be valid.

Example: `30`

After completion, the `qrcode` and `URI` for the user's `IPv4` configuration will be sent.

**Note:** At any stage, you can use the `Cancel` and `Back` buttons to cancel the process or go back.

----

## Show User

After selecting the `Show User` option, you will be asked for the user's username.

After entering the correct username, the user's information will be displayed in a message containing a `qrcode`, `URI`, total usage, and 8 buttons.

### Buttons

#### 1. Reset User

Using this button, all of the user's information will be reset. If the volume and time have expired, it will be updated again, and the user will be able to use their configuration.

*   **Developer Note:** This is essentially a "renew" function, resetting both traffic and expiration date.

#### 2. IPv6-URI

The `URI` and `qrcode` for the `IPv6` configuration will be displayed in a message.

#### 3. Edit Username

After selecting this option, you will be prompted for a new username, and you can change the user's username.

*   **Note:** Changing the username will invalidate the user's configuration.
* **Developer Note**: Important that config is tied to the username.

#### 4. Edit Traffic Limit

Using this option, you can change the user's traffic limit.

After selecting, you will be prompted for the new traffic amount. Enter a numerical value.

The calculation is based on gigabytes.

#### 5. Edit Expiration Days

Using this option, you can change the number of days the user's account is valid. After selecting, you will be prompted for the new value.

#### 6. Renew Password

After selecting this option, a new password will be generated for the user.

*   **Note:** Changing the password will invalidate the user's configuration.
* **Developer Note**: Important that config is tied to the password.

#### 7. Renew Creation Date

This option updates the user's activation date.  This is different from the `Edit Expiration Days` button.

For example, you created the user on `17/12/2024`, and if you set `30` days for the user as `Expiration Days`, the user will expire on `17/01/2025`.

This option updates the user's creation date to the current day.

For example, if your user has run out of days and time but still has some volume remaining, you can use this option to update the creation date to the current day, and the user can use their configuration again with the same remaining volume but with an updated time and day value.

*   **Developer Note:** This is a crucial distinction.  `Edit Expiration Days` sets the *duration* of validity.  `Renew Creation Date` resets the *starting point* of that duration, effectively extending the validity period without changing the length of the period.  This is very useful for giving users more time without increasing their total allotted days.

#### 8. Block User

With this option, you can block or disconnect the user.

*   A value of `true` is equivalent to disconnected.
*   A value of `false` is equivalent to connected.

*   **Developer Note:**  Simple boolean toggle to enable/disable the user's access.

---

## Delete User

By selecting this option from the main bot menu, you can delete a user.

After selecting, you will be prompted for the username, and after sending the correct username, the user will be deleted.

---

## Server Info

After selecting this option, the server information will be sent to you in a message.

```
📈 CPU Usage: 6.2%
📋 Total RAM: 1963MB
💻 Used RAM: 345MB
👥 Online Users: 2

🚦Total Traffic:
🔼16.91 GB uploaded
🔽239.35 GB downloaded
```
* **Developer Note**: Basic system monitoring info and total traffic stats.

## Backup Server

By selecting this option, the following files will be sent to you in a `zip` file, based on the hour and day.

```shell
FILES_TO_BACKUP=(
    "/etc/hysteria/ca.key"
    "/etc/hysteria/ca.crt"
    "/etc/hysteria/users.json"
    "/etc/hysteria/config.json"
    "/etc/hysteria/.configs.env"
)
```

*   **Developer Note:** This backs up the essential configuration files, including the CA key and certificate (critical for TLS), the user database, the main configuration file, and environment variables.  This is a very good practice for disaster recovery.

----
## Search Users
To enable user search in Telegram bot, you need to activate `Inline mode` by [`@BotFather`](https://t.me/BotFather)

How to activate:
Open `botfather` and enter command `/mybots`.
Select your bot and press `Bot Settings` button.
Select `Inline Mode` and press `Turn On`.

### Video

<p align="center">
<img src="/Picture/telegram_search.gif" width="320" height="200">
</p>

