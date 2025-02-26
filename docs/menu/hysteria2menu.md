# Hysteria2 Menu
---
<p align="center">
In this menu, you can manage users.
<br>

<img src="/Picture/hysteria2menu.png">
</p>

### Menu Description

### 1. Install and Configure Hysteria2
The first option is for installing the core and setting up Hysteria2, which was already completed during installation, so there is no need to reinstall.

---

### 2. Add User

- After selecting option `2`, you will be prompted to enter a username using only letters and numbers.  
  **Do not use non-English characters or special symbols.**  
- Next, enter the user's traffic limit in gigabytes.  
- Finally, specify the number of days before expiration (e.g., `30` for one month).  
```
Enter the username: return
Enter the traffic limit (in GB): 30
Enter the expiration days: 30
User return added successfully.
```
---

### 3. Edit User

- Enter the username you want to edit.  
- Set a new username.  
- Set a new traffic limit.  
- Set a new expiration period.  
- Update the user's password.  
- Update the user’s creation date.  
- Block the user if necessary.  

```
Enter the username you want to edit: return
Enter the new username (leave empty to keep the current username):
Enter the new traffic limit (in GB) (leave empty to keep the current limit):
Enter the new expiration days (leave empty to keep the current expiration days):
Do you want to generate a new password? (y/n): n
Do you want to generate a new creation date? (y/n): n
Do you want to block the user? (y/n): n
```

**Notes:**

- Fields labeled **"leave empty to keep the current"** can be skipped to retain previous values.  
- Options marked with **(y/n)** allow skipping by entering `n` (no).  
- If the username or password is changed, a new subscription must be provided, as the old one will be invalid.  

---

### 4. Reset User

After selecting **Reset User**, enter the username to reset their data.  
This option is used when a user's time or traffic is exhausted, allowing them to retain the same limits and reconnect.

---

### 5. Remove User

After selecting **Remove User**, enter the username to delete the user from the system.

---

### 6. Get User

After selecting **Get User**, enter a username to retrieve their details.

```
Enter the username: return
User Details:
Username:         return
Password:         eeDQW4ZwvqFBgZZjIqNUrgHY8za3Lc99
Total Traffic:    30.00 GB
Total Usage:      0 GB
Time Expiration:  2025-02-13 (0/30 Days)
Blocked:          false
Status:           Offline
```

---

### 7. List Users

After selecting **List Users**, the entire user list will be displayed:

```
Username             Traffic Limit (GB)   Expiration (Days) Creation Date        Password                       Blocked
jeff                 50                   120             2025-01-14           WWRDnembtjaooTJJXkBizOkY9fmyLzgE false
return               30                   30              2025-01-14           eeDQW4ZwvqFBgZZjIqNUrgHY8za3Lc99 false
hys2                 50                   30              2024-12-10           qAuwQ3b9kVsjoCHi9DtslWjtq9JMUbj4 true
```


---

### 8. Check Traffic Status

After selecting **Check Traffic Status**, the upload and download usage for each user will be displayed:

```
Traffic Data:
-------------------------------------------------
User            Upload (TX)     Download (RX)   Status
-------------------------------------------------
jeff            392.00MB        9.45GB          Online
-------------------------------------------------
return          554.52MB        19.19GB         Online
-------------------------------------------------
hys2            4.82GB          143.71GB        Offline
-------------------------------------------------
```

---

### 9. Show User URI

After selecting **Show User URI**, enter a username to display their **IPv4** and **IPv6** configuration, along with a **QR code** for the configuration.

**Notes:**

- If sub-links are enabled, the user's subscription link will also be displayed at the end.
