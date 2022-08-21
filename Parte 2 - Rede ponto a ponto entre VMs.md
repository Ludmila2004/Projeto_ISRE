# Rede Ponto a Ponto Entre VMs

> Após termos criado os diretórios e subdiretórios necessários e anexado o arquivo ```ubuntu-server-mini.ova``` no subdiretório ```original```, podemos importar as máquinas virtuais no VirtualBox, para que assim a conexão ponto a ponto entre as VMs sejam feitas. Mas antes de realizar a importação, o pacote de extensão do Virtualbox deve ser instalado (esse pacote permite justamente a conexão remota de máquinas virtuais, que é o que faremos ao decorrer desse projeto). A instalação é bastante simples e é feita através dos comandos:
```bash
sudo apt install virtualbox-ext-pack
```
![img8](https://user-images.githubusercontent.com/80183918/185101387-c33e7674-53ab-44cd-9aae-93adf68d3ad7.png)


### Importação das VMs para dentro do VirtualBox

* Como o objetivo principal deste projeto é conectar 8 máquinas virtuais, precisamos primeiramente importá-las para o VirtualBox, já que possuímos o arquivo ```ubuntu-server-mini.ova```(formato de exportação da VM) de cada uma delas.
 1) Arquivo > Importar Appliance 
  
    ![Inkedimg9](https://user-images.githubusercontent.com/80183918/185103492-6f1d74ac-7414-4bb4-aa27-b5a3c20e6593.jpg)
 2) Na parte de ORIGEM, é inserido o caminho e o arquivo .ova que será importado. No lado de CONFIGURAÇÕES, é definido o nome da máquina virtual e logo abaixo (em PASTA PADRÃO PARA MÁQUINAS) o caminho do diretório em que as máquinas serão salvas.
 
    ![Inkedimg10](https://user-images.githubusercontent.com/80183918/185105820-5e2b0325-9b95-4e15-a775-a00b0dcc352c.jpg)
 
    ![img11](https://user-images.githubusercontent.com/80183918/185108262-51d8d28d-e9f5-4648-86a6-fd51660727fe.png)

 3) Após a importação, a máquina virtual foi criada e prosseguimos selecionando-a e dando início ao processo de clonagem. Foi redefinido o nome do clone da máquina virtual e novamente inserido o caminho do diretório onde o clone será armazenado
 
    ![Inkedimg12](https://user-images.githubusercontent.com/80183918/185109484-53bb853e-14a2-475d-918b-d9eb3511d051.jpg)
    
    ![Inkedimg13](https://user-images.githubusercontent.com/80183918/185110148-8509b712-d0d6-4455-8583-91596a3f038d.jpg)
    
    ![Inkedimg17](https://user-images.githubusercontent.com/80183918/185111619-cbade523-abac-4045-a388-e3f3e045aa23.jpg)
  
### Configuração da rede virtual
* As VMs precisar estar conectadas na memsma rede interna, para isso devemos acessar as configurações de cada uma das 8 VMs, acessar a opção Rede e selecionar o mdo ```rede interna```.
* Agora, basta definir o nome da rede interna de cada uma delas como ```labredes```. 

### Configuração dos Endereços Estáticos 

* Para alterar os endereços estáticos das nossas VMs basta acessarmos o arquivo YAML, presente no Ubuntu e, antes disso, instalar as ferramentas de rede. Certifique-se de estar logado no usuário ```redes``` senha ```admin@Lab92```.
```bash
 sudo apt install net-tools -y
```

  ![20220811_085458~2](https://user-images.githubusercontent.com/80183918/185114064-17ba8b8d-88bd-404f-b6bb-b2e5e783cca0.jpg)
  
  ![20220811_085629~2](https://user-images.githubusercontent.com/80183918/185114094-ad96a8e4-4086-4e68-94c8-9254915bdea8.jpg)


* Após instalar essa ferramenta, basta alterar o arquivo ```yaml```:
```bash
 sudo nano /etc/netplan/01-netcfg.yaml
```

  ![20220811_085734~2](https://user-images.githubusercontent.com/80183918/185116210-32492b3c-c9ac-4d7a-9c68-5c17540770ef.jpg)

* O arquivo ```yaml``` já possui algumas linhas preenchidas, no entanto, você deve configurar o endereço estático utilizando o ```addresses``` e o ```gateway4``` (de acordo com o endereço pré-definido para as máquinas que estão na tabela no arquivo READEME.md) e desativando o ```dhcp4```:

  ![20220811_090229~2](https://user-images.githubusercontent.com/80183918/185116226-d71c1684-638e-420a-bbd0-2a70fa25d533.jpg)

> NOTA: Certifique-se de não usar recuo de linhas para realizar a indentação, além de identar corretamente as linhas, pois qualquer erro implicará na invalidação da configuração. Os espaços também devem ter atenção especial.
* Feito isso, digite ```ctrlX```, seguido por ```y``` e ```enter```, para salvar as alterações.
* Por fim, basta digitar o seguinte comando para aplicar as alterações na interface de rede:
```bash
 sudo netplan apply
 #para verificar as alterações, utilize:
 ifconfig -a
```

  ![20220811_090336~2](https://user-images.githubusercontent.com/80183918/185116236-ba4f8b41-5dce-4a73-9680-eec82f8dcfe3.jpg)


### Replicação dos passos nas demais VMs
* No tópico anterior, nós alteramos os endereços estáticos de uma única VM, agora basta replicar os passos do tópico anterior para todas as outras VMs de cada computador.
> NOTA: Lembre-se que o gateway é o mesmo para todas as VMs, mas o addresses deve ser único, conforme especificado na tabela de Endereçamento IP

### Teste de Conectividade
* O ```ping``` é um comando responsável por testar a conectividade. Logo, para saber se as configurações forram bem-sucedidas, basta realizar pings entre as VMs.

* Realizamos os testes de conectividade entre as duas máquinas dos 4 computadores e como comprovação, segue os anexos dos testes entre a VM1 e VM2 do PC4:
  
  ![20220811_092026~2](https://user-images.githubusercontent.com/80183918/185121140-63e04534-2ed6-4321-9cd2-a1d3f4b43ce6.jpg)
  
  ![20220811_092018~2](https://user-images.githubusercontent.com/80183918/185121175-a3da9260-3591-4e8d-a9ff-06781cd277d4.jpg)

> NOTA: o endereço do ping deve corresponder a VM que deseja ser acessada.
