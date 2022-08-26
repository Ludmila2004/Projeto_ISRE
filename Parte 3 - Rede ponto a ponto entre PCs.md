<h1 align="left"> Rede ponto a ponto entre PC's</h1>

 Criação de uma rede ponto a ponto física entre 4 PCs e uma LAN lógica com 8 VMs

 ## Conexão ponto a ponto
 
* Antes de iniciar, é preciso realizar uma verificação da existência do arquivo ```01-network-manager-all.yaml``` dentro da pasta ```/etc/netplan``` e confirmar se no arquivo de configuração, a entrada apresentada é ```renderer:NetworkManager```, caso a que estiver sendo apresentada for ```renderer:networkd```, um erro do tipo ```Wired Unmanaged error``` aparecerá. Para efetuarmos essa verificação, executa-se os seguintes comandos:
```bash
ifconfig -a
cd /etc/netplan
ls -la 
cat /etc/netplan/01-network-manager-all.yaml
```
## Criando uma rede ponto a ponto com as 8 máquinas virtuais
* Criar uma rede ponto a ponto entre os 4 PCs, mas juntando uma LAN com 2 VMs dentro do VirtualBox de cada PC;
* É necessário que as VMs e as interfaces das VMs sejam configuradas;
* Fazer login nas VMs.
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

  ![20220811_092438](https://user-images.githubusercontent.com/80183918/186790808-855c9080-1296-458b-b669-0b269d6aa1ff.jpg)
   
## Configuração das VMs nos PCs
Após realizar as verificações anteriores, especificamente a existência do arquivo ```01-netcfg.yaml```, deve-se editar o arquivo em questão tendo como base os endereços pré-definidos

* Deve-se entrar no arquivo 01-netcfg.yaml e configurar o endereço IP. Para isso, executa-se o comando
```bash
$ sudo nano /etc/netplan/01-netcfg.yaml
```
![20220811_090710](https://user-images.githubusercontent.com/80183918/186921916-b8bf0c49-6ae0-4668-a43f-42e6c07d34b0.jpg)
  
* Deve ser Adicionado as linhas para a configuração estática do IP foi definido anteriormente, sendo um específico para cada máquina virtual e a desativação do dhcp, visto que não se quer que um endereço seja gerado de forma dinâmica. Para essa edição ser realizada, a série de comandos a ser feitas será:

```bash
ifconfig -a.
```
```bash
$ sudo netplan apply.
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
> NOTA: E assim, faça o mesmo para pingar as outras duas máquinas.






     



