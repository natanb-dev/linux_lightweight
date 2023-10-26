# linux_lightweight

# Configurações no sysctl.conf

Este repositório contém as configurações recomendadas para o arquivo `sysctl.conf` em sistemas Linux. O `sysctl.conf` é usado para configurar diversos parâmetros do kernel do Linux.

## Como Aplicar as Configurações

```bash
# Para aplicar essas configurações, você pode editar o arquivo `sysctl.conf` usando o comando: 
sudo nano /etc/sysctl.conf

# Configurações recomendadas:
vm.swappiness = 10
vm.vfs_cache_pressure = 50 
vm.dirty_background_ratio=2
vm.dirty_ratio=15

# Para que as mudanças sejam postas em prática
sudo sysctl -p 

# Comandos Adicionais (Não Testados)
Estas são configurações adicionais que ainda não foram devidamente testadas:

- editar somente a swappiness temporariamente:
    sudo sysctl vm.swappiness=50


# Otimização - Internet: 
vm.swappiness = 25
vm.vfs_cache_pressure = 50 (opcional)
net.core.wmem_default=262144
net.core.wmem_max=4194304
net.core.rmem_default=262144
net.core.rmem_max=4194304
net.ipv4.tcp_rmem = 65535 131072 4194304
net.ipv4.tcp_wmem = 65535 131072 194304
net.ipv4.tcp_timestamps=0
net.ipv4.tcp_fin_timeout=30 (opcional)


# Otimização - Segurança:
kernel.randomize_va_space = 2
fs.suid_dumpable = 0
kernel.sysrq = 0
kernel.kptr_restrict = 2
net.ipv4.conf.all.log_martians = 1
net.ipv4.icmp_echo_ignore_broadcasts = 1
net.ipv4.icmp_ignore_bogus_error_responses = 1



