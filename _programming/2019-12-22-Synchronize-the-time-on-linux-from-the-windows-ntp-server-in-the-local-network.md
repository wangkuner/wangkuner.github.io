---
layout: index
title: Synchronize the time on linux from the windows ntp server in the local network
description: linux
---

# Synchronize the time on linux from the windows ntp server in the local network

## Configure the windows as a ntp server

Enable NTPServer.
1. Close the firewall.
2. Locate and then click the following registry subkey: **HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Services\W32Time\TimeProviders\NtpServer**.
3. Modify the value to be **1** to enable the ntp server.
4. Run command `net stop w32time` as administrator if the w32time service is running.
5. Run command `net start w32time` as administrator to start w32time service.

## Synchronize the time on linux

Run `ntpdate ntp_server_ip` as root. the ntp service should be stopped first if "*ntp socket is in use*" is returned.
Run `service ntpd stop` and then execute `ntpdate ntp_server_ip`.

