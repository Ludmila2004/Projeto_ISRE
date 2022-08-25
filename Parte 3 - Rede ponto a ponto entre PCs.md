<h1 align="left"> Rede ponto a ponto entre PC's</h1>

 Criação de uma rede ponto a ponto física entre 4 PCs e uma LAN lógica com 8 VMs

 ###Conexão ponto a ponto
1.Abrir o terminal nos 4 PCs e, assim verifique as configurações de rede;
2.A configuração de interfaces de rede Ubuntu no Neplan;
3.Para encontramos esse arquivo digitamos: 
```bash
fconfig -a
cd /etc/netplan
ls -la 
cat /etc/netplan/01-network-manager-all.yaml
   ```
