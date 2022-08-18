<h1 align="left">Acesso Remoto SSH</h1>

De primeira instância, vale lembrar que nesse momento do processo a tabela de endereços anteriormente já feita irá ser de extrema importância. 

### Antes de tudo...

1. Nas configurações das VM's mude o Adaptador1 para NAT


2. E comente as linhas com "#" do Netplan(gateway e endereço IP)


### Instalação do SSH

Para instalar, basta usar os comandos:

```bash
sudo apt-get install openssh-server
```

Após usar esse comando, faz-se necessário verificar se realmente houve a instalação através do seguinte comando
```bash
systemctl status ssh
```


