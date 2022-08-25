<h1 align="left"> Rede ponto a ponto entre PC's</h1>

 Criação de uma rede ponto a ponto física entre 4 PCs e uma LAN lógica com 8 VMs

 ## Conexão ponto a ponto
 
1. Abrir o terminal nos 4 PCs e, assim verifique as configurações de rede;
2. A configuração de interfaces de rede Ubuntu no Neplan;
3. Para encontramos esse arquivo digitamos: 
```bash
fconfig -a
cd /etc/netplan
ls -la 
cat /etc/netplan/01-network-manager-all.yaml
   ```
## Criando uma rede ponto a ponto com as 8 máquinas virtuais
1. Criar uma rede ponto a ponto entre os 4 PCs, mas juntando uma LAN com 2 VMs dentro do VirtualBox de cada PC;
2. É necessário que as VMs e as interfaces das VMs sejam configuradas;
3. Fazer login nas VMs C
```bash
Usuário da VM: administrador.
Senha da VM: adminifal.
   ```
## Configuração estática de endereço IP na interface de rede
1. Configurar os IPs das interfaces de rede·
2. Para configurar as interfaces de rede o Ubuntu utiliza um arquivo YAML e este arquivo se encontra na pasta /etc/netplan/. Para isso digite:
```bash
ifconfig -a
ls -la /etc/netplan
cat /etc/netplan/01-netcfg.yaml
     ```
3. Verifique se o nome do arquivo está correto no seu servidor.
   
## Configuração da VMs nos PCs

     



