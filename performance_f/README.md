# linux_lightweight

# Configurações no sysctl.conf

Este repositório contém as configurações recomendadas para o arquivo `sysctl.conf` em sistemas Linux. O `sysctl.conf` é usado para configurar diversos parâmetros do kernel do Linux.

## Como Aplicar as Configurações

```bash
# Para aplicar essas configurações, você pode editar o arquivo `sysctl.conf` usando o comando: 
sudo nano /etc/sysctl.conf

# Configurações recomendadas:
vm.swappiness = 25
net.core.wmem_default = 262144
net.core.wmem_max = 4194304
net.core.rmem_default = 262144
net.core.rmem_max = 4194304
net.ipv4.tcp_rmem = 65535 131072 4194304
net.ipv4.tcp_wmem = 65535 131072 194304
kernel.randomize_va_space = 2
fs.inotify.max_user_watches = 524288

# Para que as mudanças sejam postas em prática
sudo sysctl -p 

# Comandos Adicionais (Não Testados)
Estas são configurações adicionais que ainda não foram devidamente testadas:

- editar somente a swappiness temporariamente:
    sudo sysctl vm.swappiness=50


kernel.sem = 250 32000 32 256
kernel.sched_autogroup_enabled = 0
vm.dirty_background_ratio = 5
vm.dirty_ratio = 10
net.core.netdev_max_backlog = 1000
net.ipv4.tcp_window_scaling = 1
kernel.pid_max = 65536
vm.vfs_cache_pressure = 50

