# Linux Lightweight Configuration

Este repositório contém configurações recomendadas para o arquivo `sysctl.conf` em sistemas Linux. O `sysctl.conf` é usado para configurar diversos parâmetros do kernel do Linux, ajudando a otimizar o desempenho e a segurança do sistema.

## Aplicando as Configurações

Para aplicar essas configurações, siga os passos a seguir:

1. Abra o arquivo `sysctl.conf` em um editor de texto usando o comando:

   ```bash
   sudo nano /etc/sysctl.conf
   ```

2. Adicione as configurações recomendadas listadas abaixo ao arquivo `sysctl.conf`. 

   Configurações recomendadas:

   ```bash
	vm.swappiness = 10
	vm.vfs_cache_pressure = 50
	vm.dirty_background_ratio = 5
	vm.dirty_ratio = 10
   ```

3. Após adicionar as configurações desejadas, salve o arquivo e feche o editor.

4. Para que as mudanças entrem em vigor, execute o seguinte comando:

   ```bash
   sudo sysctl -p
   ```

Para alterar temporariamente a configuração de `vm.swappiness`, você pode usar o comando:

```bash
sudo sysctl vm.swappiness=10
```

Lembrando que essas configurações são recomendadas e podem ser ajustadas de acordo com as necessidades específicas do seu sistema.

## Comandos Adicionais (Não Testados)

Aqui estão algumas configurações adicionais que ainda não foram devidamente testadas. Elas podem ser exploradas para otimização adicional:

### Otimização - Internet:

```bash
net.core.wmem_default = 8192
net.core.wmem_max = 65536
net.core.rmem_default = 8192
net.core.rmem_max = 65536
net.ipv4.tcp_timestamps = 0
net.ipv4.tcp_fin_timeout = 30
```

### Otimização - Segurança:

```bash
kernel.randomize_va_space = 2
fs.suid_dumpable = 0
kernel.sysrq = 0
kernel.kptr_restrict = 2
net.ipv4.conf.all.log_martians = 1
net.ipv4.icmp_echo_ignore_broadcasts = 1
net.ipv4.icmp_ignore_bogus_error_responses = 1
```

Lembre-se de que essas configurações adicionais devem ser usadas com cautela e testadas em um ambiente de desenvolvimento antes de serem aplicadas em produção. Elas podem ajudar a melhorar o desempenho e a segurança do sistema, mas também podem afetar o comportamento do sistema de forma imprevista se não forem configuradas corretamente
