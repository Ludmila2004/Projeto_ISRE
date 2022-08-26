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

  ![Captura de tela de 2022-08-26 11-32-31](https://user-images.githubusercontent.com/80183918/186927925-62fb0d6a-b115-4f28-bd7a-e3f0acaa72db.png)

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
   ![20220811_090710 (1)](https://user-images.githubusercontent.com/80183918/186922783-ae8ae5b4-294c-4f65-8084-5213ccd255a4.jpeg)
  
* Deve ser Adicionado as linhas para a configuração estática do IP foi definido anteriormente, sendo um específico para cada máquina virtual e a desativação do dhcp, visto que não se quer que um endereço seja gerado de forma dinâmica. Para essa edição ser realizada, a série de comandos a ser feitas será:
  
   ![20220811_090930 (1)](https://user-images.githubusercontent.com/80183918/186922784-bc6c8f4c-04a3-465e-a1a9-04b1fe53eca9.jpeg)

* Para realizar a aplicação da edição e a verificação do endereçamento IP que foi pré-definido, utilizando os comandos:

```bash
$ sudo netplan apply.
$ ifconfig -a.
```

  ![20220811_091014 (1)](https://user-images.githubusercontent.com/80183918/186922788-c459e692-8fac-44c8-94c5-b176cde24b40.jpeg)
  
 Faça a configuração das VMs nas próximas 7 Vms restantes.
* Montando a rede LAN Ponto a Ponto com cabeamento.
* Conecte o cabo de rede entre os quatro PCs.
* Configuração da rede brigde do VirtualBox nos dois PCs e nas duas VMs.
* Configuração das NICs como modo “bridge”.
## Testar a conectividade entre as VMs com o comando ping.
```bash
    Ping da VM1-PC4 para VM1-PC2
```    
   ![20220811_103625](https://user-images.githubusercontent.com/80183918/186924089-c7b60969-9cef-4756-bcf6-a11434cc47b6.jpeg)

```bash
    Ping da VM2-PC4 para VM2-PC2
```
   ![20220811_103616](https://user-images.githubusercontent.com/80183918/186924079-8b17e16e-a807-4a51-80e5-01104170f92f.jpeg)

> NOTA: E assim, faça o mesmo para pingar as outras duas máquinas.






     



