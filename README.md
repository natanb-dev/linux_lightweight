# Linux Lightweight Configuration

**Configurações no sysctl.conf para sistemas Linux leves**

Este repositório contém as configurações recomendadas para o arquivo `sysctl.conf` em sistemas Linux leves. O `sysctl.conf` é usado para configurar diversos parâmetros do kernel do Linux.

**Objetivos**

As configurações neste repositório têm os seguintes objetivos:

* **Melhorar o desempenho do sistema**
* **Aumentar a segurança do sistema**
* **Reduzir o consumo de recursos**

**Configurações recomendadas**

As configurações recomendadas para sistemas leves são as seguintes:

```
vm.swappiness = 25
vm.vfs_cache_pressure = 25
net.core.wmem_default = 32768
net.core.wmem_max = 131072
net.core.rmem_default = 32768
net.core.rmem_max = 131072
net.ipv4.tcp_timestamps = 0
net.ipv4.tcp_fin_timeout = 60
vm.dirty_background_ratio = 5
vm.dirty_ratio = 10
```

Estas configurações otimizam o uso da memória e da rede, reduzindo o consumo de recursos e melhorando o desempenho.

**Comandos adicionais**

Além das configurações recomendadas, também é possível aplicar as seguintes configurações adicionais:

```
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
```

As configurações de otimização da internet podem melhorar o desempenho de aplicativos que dependem da rede. As configurações de otimização da segurança podem ajudar a proteger o sistema contra ataques.

**Aplicação das configurações**

Para aplicar as configurações, siga estas etapas:

1. Edite o arquivo `sysctl.conf` usando um editor de texto.
2. Insira as configurações desejadas no arquivo.
3. Salve o arquivo.
4. Execute o comando `sudo sysctl -p` para aplicar as configurações.

**Atualização das configurações**

Para atualizar as configurações, basta editar o arquivo `sysctl.conf` e salvar as alterações. Em seguida, execute o comando `sudo sysctl -p` para aplicar as alterações.

**Recomendações**

É recomendado aplicar as configurações recomendadas para sistemas leves. As configurações adicionais podem ser aplicadas para melhorar o desempenho ou a segurança do sistema, dependendo das necessidades específicas.

**Avisos**

A aplicação de configurações incorretas no arquivo `sysctl.conf` pode causar problemas no sistema. É importante testar as configurações antes de aplicar as alterações permanentemente.
