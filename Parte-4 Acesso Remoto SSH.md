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
Após esses passos é só esperar um tempinho para que haja uma instalação bem sucedida.

### Verificar o Firewall
 Para verificar se o Firewall está ativado e ativá-lo no UFW da ```ubuntu```, use:
 
```bash
sudo ufw status
sudo ufw allow ssh
```
Caso não esteja, é necessário que o usuário ative-o

```bash
sudo ufw enable
```
### Reconfigurando
Volte com as antigas configurações das VM's, colocando-as em Modo Bridge e tirando os comentários anteriormente adicionados.

### Acessando as VM's
Para testar as conectividades das VM's, basta o usuário seguir o modelo de comando abaixo, apenas colocando seu ```endereço IP``` e o nome de seu ```user```
```bash
ssh administrador@
```
Faça esse processo em ambas as Máquinas Virtuais de todos os computadores a serem posteriormente conectados.
