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
3. Fazer login nas VMs 
```bash
Usuário da VM: administrador;
Senha da VM: adminifal.


