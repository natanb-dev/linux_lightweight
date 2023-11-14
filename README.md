**Linux Lightweight Configuration**

This repository contains recommended settings for the `sysctl.conf` file on Linux systems. `sysctl.conf` is used to configure various Linux kernel parameters, helping to optimize system performance and security.

## Applying the Settings

To apply these settings, follow the steps below:

1. Open the `sysctl.conf` file in a text editor using the command:

```bash
sudo nano /etc/sysctl.conf
```

2. Add the recommended settings listed below to the `sysctl.conf` file.

**Recommended Settings:**

```bash
vm.swappiness = 10
vm.vfs_cache_pressure = 50
vm.dirty_background_ratio = 5
vm.dirty_ratio = 10
```

3. After adding the desired settings, save the file and close the editor.

4. To make the changes take effect, run the following command:

```bash
sudo sysctl -p
```

To temporarily change the `vm.swappiness` setting, you can use the command:

```bash
sudo sysctl vm.swappiness=10
```

Please note that these settings are recommended and can be adjusted to meet the specific needs of your system.

## Additional Commands (Untested)

Here are some additional settings that have not yet been properly tested. They can be explored for further optimization:

### Optimization - Internet:

```bash
net.core.wmem_default = 8192
net.core.wmem_max = 65536
net.core.rmem_default = 8192
net.core.rmem_max = 65536
net.ipv4.tcp_timestamps = 0
net.ipv4.tcp_fin_timeout = 30
```

### Optimization - Security:

```bash
kernel.randomize_va_space = 2
fs.suid_dumpable = 0
kernel.sysrq = 0
kernel.kptr_restrict = 2
net.ipv4.conf.all.log_martians = 1
net.ipv4.icmp_echo_ignore_broadcasts = 1
net.ipv4.icmp_ignore_bogus_error_responses = 1
```

Please note that these additional settings should be used with caution and tested in a development environment before being applied in production. They can help improve system performance and security, but they can also affect system behavior in unpredictable ways if not configured correctly.
