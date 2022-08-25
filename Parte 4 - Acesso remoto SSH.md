<h1 align="left">Acesso Remoto SSH</h1>
O SSH(Secure Shell) é um protocolo para acessar uma máquina remota em segurança, sendo possível a execução de uma linha de comando, transferência de arquivos e criar redes privadas seguras. A vantagem dele é a segurança e simplicidade.

De primeira instância, vale lembrar que nesse momento do processo a tabela de endereços anteriormente já feita irá ser de extrema importância. 

## Antes de tudo...

1. Nas configurações das VM's mude o Adaptador1 para NAT, O modo NAT permite que a sua máquina virtual se conecte à rede interna utilizando o IP da sua máquina física.

   ![20220811_105708~3](https://user-images.githubusercontent.com/80183918/186547690-92ab2436-9b8b-450a-94ce-34d9ffdd82b6.jpg)

2. E comente com "#" as linhas de endereço IP estático do (gateway e endereço IP) e ative o DHCP nas configurações do Netplan

   ![20220811_112925](https://user-images.githubusercontent.com/80183918/186547851-f46b9f8e-9d28-4dc6-b88a-13b600fca3a4.jpg)

## Confirmando que as VMs estão tendo acesso à internet
   
 1. Primeiramente, foi feito uma atualização das definições e versões de todos os pacotes e bibliotecas do repositório ubuntu. Esse comando também deve ser usado após uma nova instalação. Atualiza o banco de dados e como foi anteriormente citado, informa a existência de outros pacotes disponíveis. Usando o comando:
 
   ```bash
   sudo apt update
   ```
   
2. Após a atualização anterior, é executada uma nova atualização a fim de atribuir aos novos pacotes, suas novas definições e versões. Depois que atualiza o banco de dados, agora atualiza os pacotes instalados. Para isso:

  ```bash
  sudo apt upgrade -y
  ```
  
![20220811_113926~2](https://user-images.githubusercontent.com/80183918/186549359-f4febe16-1fe5-46ce-9e8b-132abf98eb38.jpg)

## Instalação do SSH

Normalmente, não vem com esse recurso ativo, então é necessário acessá-lo instalando o pacote do servidor OpenSSH. Para ativá-lo, escreva o comando:

```bash
sudo apt-get install openssh-server
```
Quando instalado, ele deve ser iniciado automaticamente.
Para verificar se realmente houve a instalação utiliza o comando:

```bash
systemctl status ssh
```
Após esses passos é só esperar um tempinho para que haja uma instalação bem sucedida.

![20220811_114044](https://user-images.githubusercontent.com/80183918/186551722-aadb229c-4add-4616-ba35-1dc72c157b65.jpg)

## Verificação das portas do sistema

Faz-se necessário uma verificação das conexões TCP na porta 22, de forma que o status que apareca seja como "LISTENING". Esse comando exibe a tabela de roteamento para todos os endereços IP vinculados ao servidor:

```bash
netstat -an | grep LISTEN. 
```
![20220811_123041~2](https://user-images.githubusercontent.com/80183918/186551745-fbcdc617-0fdb-4ad0-9bb5-92f95bc92983.jpg)

## Verificar o Firewall
Para ativar o ssh no firewall UFW do ubuntu, use:
```bash
sudo ufw allow ssh.
```
Você poderá verificar o status de ativação do firewall UFW. Para isso, temos que usar o comando sudo simples.
```bash
sudo ufw status
```

Após o uso do comando citado acima, a saída irá dizer se o firewall UFW está atualmente desabilitado ou inativo. Para habilitá-lo  e deixar pronto para uso é só utilizar:

```bash
sudo ufw enable
```

![20220811_123149~2](https://user-images.githubusercontent.com/80183918/186553568-9aef9217-9a49-404a-b259-cce85f811180.jpg)

### Reconfigurando
Volte com as antigas configurações das VM's, colocando-as em Modo Bridge e tirando os comentários anteriormente adicionados.

### Acessando as VM's
Para testar as conectividades das VM's, basta o usuário seguir o modelo de comando abaixo, apenas colocando seu ```endereço IP``` e o nome de seu ```user```. Tem que ter o SSH instalado e ativado na outra máquina, caso contrário, não irá funcionar.

```bash
ssh administrador@192.168.13.49
```
Faça esse processo em ambas as Máquinas Virtuais de todos os computadores a serem posteriormente conectados.
