---
icon: circle-exclamation
layout:
  title:
    visible: true
  description:
    visible: false
  tableOfContents:
    visible: true
  outline:
    visible: false
  pagination:
    visible: false
---

# common escrow errors

<details>

<summary>Error parsing script ... syntax error near &#x3C;\1></summary>

### Error Example

```bash
[script:filo_vehiclekey] Error parsing script @filo_vehiclekey/server/server.lua in resource filo_vehiclekey: @filo_vehiclekey/server/server.lua:1: syntax error near '<\1>'
[    c-scripting-core] Failed to load script server/server.lua.
```

### Solutions

* **You are using FileZilla and files have been corrupted during transfer** - try using an alternative FTP client such as [WinSCP](https://winscp.net/eng/index.php)
* You are transferring the folder to your server file by file — **you must upload the .zip file as-is** and then extract it **after** it has been transferred to your VPS
* Your server version is too old, the minimum version is 4752
  * You can download updated server artifacts [here](https://runtime.fivem.net/artifacts/fivem/build_server_windows/master/)
  * ...or check out the official [FiveM guide](https://docs.fivem.net/docs/server-manual/setting-up-a-server/)



</details>

<details>

<summary>Failed to verify protected resource</summary>



**Error Example**

```
[svadhesive] Failed to verify protected resource filo_vehiclekey
```

**Solutions**

* Try restarting your server
* You are transferring the folder to your server file by file — you must upload the .zip file as-is and then extract it **after** it has been transferred to your VPS
* You don't have `.fxap` file in the script folder - try installing the script again
* You are using **File**Zilla and files have been corrupted during transfer - try using an alternative FTP client such as [WinSCP](https://winscp.net/eng/index.php)

</details>

<details>

<summary>You lack the required entitlement</summary>

**Error Example**

```
You lack the required entitlement to use filo_vehiclekey
```

**What does this mean?**

Some of our scripts use escrow system, which means scripts are linked to your FiveM account (the account you used on Tebex).

In order to work, the script(s) must be run in a server which is using a server key created by the same FiveM account you used on Tebex. You can create a server key in [FiveM Keymaster](https://keymaster.fivem.net/).

Once you've created a server key, add it to your server's `server.cfg` like this:

```
sv_licenseKey "licensekeyhere"
```

**The script is on my friend's FiveM account**

To transfer the script to another account, you can head to:

[FiveM Keymaster](https://keymaster.fivem.net/) -> Purchased assets tab -> Transfer to another account

cfx.re only allow scripts to be transferred 1 time, so you won't be able to transfer the script again if you do this.

</details>
