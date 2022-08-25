<h1 align="left">Acesso Remoto SSH</h1>

De primeira instância, vale lembrar que nesse momento do processo a tabela de endereços anteriormente já feita irá ser de extrema importância. 

### Antes de tudo...

1. Nas configurações das VM's mude o Adaptador1 para NAT

   ![20220811_105708~3](https://user-images.githubusercontent.com/80183918/186547690-92ab2436-9b8b-450a-94ce-34d9ffdd82b6.jpg)

2. E comente com "#" as linhas de endereço IP estático do (gateway e endereço IP) e ative o DHCP nas configurações do Netplan

   ![20220811_112925](https://user-images.githubusercontent.com/80183918/186547851-f46b9f8e-9d28-4dc6-b88a-13b600fca3a4.jpg)

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
ssh administrador@192.168.13.49
```
Faça esse processo em ambas as Máquinas Virtuais de todos os computadores a serem posteriormente conectados.
