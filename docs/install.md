## Description
---
It is recommended to update the server packages and services before installation using the following command:  

```bash
apt update && apt upgrade -y
```

## Installation Command
---
Run the following command:  

```bash
bash <(curl https://raw.githubusercontent.com/ReturnFI/Hysteria2/main/install.sh)
```

Please be patient while the required services and packages are installed for the script to run.

Once the installation is complete, you will enter the menu.  
Press `1` to access the `Hysteria2 Menu`, then select the `Install and Configure Hysteria2` option by pressing `1`.

Next, you will be asked to enter an `SNI`.  
You can skip this step by pressing Enter to use the panel's default `SNI`.

If you prefer to use your own `SNI`, enter it in the following format:  

Example:  
`bing.com`  

Avoid using `https://` or any `/` characters.  
The correct format for entering `SNI` is as shown in the example.

After entering the `SNI`, you will be asked to specify a `port` for activation.  
You can use any port of your choice. For example:  
`1433`

## Video
---
<p align="center">
<img src="https://returnfi.github.io/Hys2-docs/Picture/install.gif">
</p>
