<h1 align="left"> Rede ponto a ponto entre PC's</h1>

 Criação de uma rede ponto a ponto física entre 4 PCs e uma LAN lógica com 8 VMs

 ## Conexão ponto a ponto
 
* Abrir o terminal nos 4 PCs e, assim verifique as configurações de rede;
* A configuração de interfaces de rede Ubuntu no Neplan;
* Para encontramos esse arquivo digitamos: 
```bash
fconfig -a
cd /etc/netplan
ls -la 
cat /etc/netplan/01-network-manager-all.yaml
   ```
## Criando uma rede ponto a ponto com as 8 máquinas virtuais
* Criar uma rede ponto a ponto entre os 4 PCs, mas juntando uma LAN com 2 VMs dentro do VirtualBox de cada PC;
* É necessário que as VMs e as interfaces das VMs sejam configuradas;
* Fazer login nas VMs C
```bash
Usuário da VM: administrador.
Senha da VM: adminifal.
   ```
## Configuração estática de endereço IP na interface de rede
 Configurar os IPs das interfaces de rede·
* Para configurar as interfaces de rede o Ubuntu utiliza um arquivo YAML e este arquivo se encontra na pasta /etc/netplan/. Para isso digite:

```bash
ifconfig -a
ls -la /etc/netplan
cat /etc/netplan/01-netcfg.yaml
```
* Verifique se o nome do arquivo está correto no seu servidor.
   
## Configuração da VMs nos PCs
Na VM - Lab01 do PC1E assim, faça o mesmo para pingar as outras duas máquinas

* Configure o IP.
* Edite o arquivo 01-netcfg.yaml.
```bash
$ sudo nano /etc/netplan/01-netcfg.yaml
```
* Adicione as linhas para a configuração estática do IP para configurar o IP para 192.168.13.48/28
* Depois de salvar o arquivo é necessário aplicar as configurações, com o netplan apply e após veja a configuração das interfaces com:
```bash
*ifconfig -a.
```
```bash
$ sudo netplan apply;
$ ifconfig -a.
```
 Faça a configuração das VMs nas próximas 7 Vms restantes.
* Montando a rede LAN Ponto a Ponto com cabeamento.
* Conecte o cabo de rede entre os quatro PCs.
* Configuração da rede brigde do VirtualBox nos dois PCs e nas duas VMs.
* Configuração das NICs como modo “bridge”.
## Testar a conectividade entre as VMs com o comando ping.
```bash
    Ping da VM1-PC1 para VM2-PC2
    Ping da VM1-PC1 para VM2-PC2
    ```
* E assim, faça o mesmo para pingar as outras duas máquinas.






     



