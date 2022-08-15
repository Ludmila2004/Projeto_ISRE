# Rede Ponto a Ponto Entre VMs

> Após termos criado os diretórios e subdiretórios necessários e anexado o arquivo ```ubuntu-server-mini.ova``` no subdiretório ```original```, podemos importar as máquinas virtuais no VirtualBox, para que assim a conexão ponto a ponto entre as VMs sejam feitas.

### Importação das VMs para dentro do VirtualBox

* Como o objetivo principal deste projeto é conectar 8 máquinas virtuais, precisamos primeiramente importá-las para o VirtualBox, já que possuímos o arquivo ```ubuntu-server-mini.ova```(formato de exportação da VM) de cada uma delas.
* FOTOS

### Configuração da rede virtual
* As VMs precisar estar conectadas na memsma rede interna, para isso devemos acessar as configurações de cada uma das 8 VMs, acessar a opção Rede e selecionar o mdo ```rede interna```.
* Agora, basta definir o nome da rede interna de cada uma delas como ```labredes```. 

### Configuração dos Endereços Estáticos 

* Para alterar os endereços estáticos das nossas VMs basta acessarmos o arquivo YAML, presente no Ubuntu e, antes disso, instalar as ferramentas de rede. Certifique-se de estar logado no usuário ```redes``` senha ```admin@Lab92```.
```bash
 sudo apt install net-tools -y
```
* Após instalar essa ferramenta, basta alterar o arquivo ```yaml```:
```bash
 sudo nano /etc/netplan/01-netcfg.yaml
```

* O arquivo ```yaml``` já possui algumas linhas preenchidas, no entanto, você deve configurar o endereço estático utilizando o ```addresses``` e o ```gateway4```:
* FOTO
> NOTA: Certifique-se de não usar recuo de linhas para realizar a indentação, além de identar corretamente as linhas, pois qualquer erro implicará na invalidação da configuração. Os espaços também devem ter atenção especial.
* Feito isso, digite ```ctrlX```, seguido por ```y``` e ```enter```, para salvar as alterações.
* Por fim, basta digitar o seguinte comando para aplicar as alterações na interface de rede:
```bash
 sudo netplan apply
 #para verificar as alterações, utilize:
 ifconfig -a
```

### Replicação dos passos nas demais VMs
* No tópico anterior, nós alteramos os endereços estáticos de uma única VM, agora basta replicar os passos do tópico anterior para todas as outras VMs de cada computador.
> NOTA: Lembre-se que o gateway é o mesmo para todas as VMs, mas o addresses deve ser único, conforme especificado na tabela de Endereçamento IP

### Teste de Conectividade
* O ```ping``` é um comando responsável por testar a conectividade. Logo, para saber se as configurações forram bem-sucedidas, basta realizar pings entre as VMs:
```bash
 ping 192.168.13.50 #da vm1 do pc1 para a vm2 do pc1
```
* SUBSTITUA ESTE COMANDO POR FOTO DE ALGUM PING
* Faça o mesmo para cada VM de cada computador, inclusive entre a VM2 e a VM1.
> NOTA: o endereço do ping deve corresponder a VM que deseja ser acessada.
