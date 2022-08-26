# Host Only

> Nesta parte do nosso projeto de trabalhar com VM's, vamos aprender como nos conectar às VM's criadas, utilizando o terminal do computador em que estamos trabalhando. Assim, para fazer isso, iremos utilizar o comando ```ssh``` (explicado na aula anterior) e o coneceito de ```Host-Only``` (o qual será explicado adiante).

## Passo 1 - Login nas VM's
  Utilizando o VirtualBox se conecte às VM's que você criou.
  * Usuário: administrador
  * Senha: adminifal 

## Passo 2 - Interface de comunicação
  Após se conectar às VM's, precisamos configurar uma interface que possibilite a comunicação entre ela e o PC, isso deve ser feito pois queremos nos comunicar com a VM utilizando o terminal de um computador, que nesse caso será o nosso ```Host```.
  * Dentro do VirtualBox, clique em ```Arquivo``` e logo após em ```Host Network Manager```, seguido por ```Adaptador```. 
    
    ![20220825_073641](https://user-images.githubusercontent.com/80183918/186929348-cd5c3c49-8fc5-4692-b160-f9d6fbc375ae.jpg)
    
    ![cc0f81f0-4cd1-4b2e-b21a-853e841b025d](https://user-images.githubusercontent.com/80183918/186929827-636c8f07-2473-420c-827e-42f53df66dcc.jpeg)
  
  > É importante que os valores dos campos estejam iguais aos da imagem acima. 
  
  ### Configuração do servidor DHCP 
  Ainda dentro do ```Network Manager```, selecione o campo ```Servidor DHCP```.
  * Certifique-se de habilitar o servidor DHCP, clicando em ```Habilitar Servidor```.
  
  ![20220825_073733](https://user-images.githubusercontent.com/80183918/186930056-e1c12c2c-1afa-4636-a635-cbb09a147034.jpeg)
  
  * Após verificar se os campos estão preenchidos como mostrador na imagem acima, aplique as configurações clicando em ```Aplicar```. 
  > Pelo ```terminal do PC```, verifique se a configuração foi realizada com sucesso utilizando o comando:
  ```bash
    ifconfig-a #você saberá se a configuração foi bem sucedida se aparecer a interface: vxboxnet0
  ```
  ![20220825_073848](https://user-images.githubusercontent.com/80183918/186930756-29a9e41d-658b-4f54-a69d-9daed7b82c24.jpeg)

  ### Aplicação do Host-Only
  Como o foco desta nossa aula é se conectar a uma VM utilizando o terminal, então é imprescindível que o ```endereço IP``` e o ```endereço MAC``` da nossa VM seja exclusivo, para que não haja conflito no momento de realizar a conexão. Daí vem o conceito de ```Host-Only```. 
  * Para isso, retorne ao seu ```VirtualBox```, selecione a sua VM e clique na opção ```Rede```.
  * Após, adicione um novo ```Adaptador de Rede``` à VM, selecionando a opção ```Adaptador 2```.
  * Feito isso, ```habilite a placa de rede```, conecte a VM no modo ```Placa de rede exclusiva de hospedeiro (host-only)```, altere o nome do adaptador para ```enp0s8```, altere o ```endereço MAC``` e salve as alterações clicando em  ```OK```.
  > A imagem abaixo apresenta quais campos devem ser alterados/pressionados, seguindo a sequência lógica que foi descrita.
  
  ![20220825_074108](https://user-images.githubusercontent.com/80183918/186934710-c9cab17f-1777-4dbe-9f57-b48ffb3e6d0e.jpeg)
  
  ### Ativação das configuração da interface
  * Antes de tudo, verifique a existência das interfaces pelo ```terminal da VM```, usando ```ifconfig-a```.
  * Para que o Adaptador 2 funcione corretamente, temos que acessar o arquivo ```yaml``` e ativar o ```DHCP```, definindo ele como ```true```.
   ```bash
    sudo nano /etc/netplan/01-netcfg.yaml
  ```
  * FOTO DA ALTERAÇÃO 
  * Feito isso, aplique as alterações e verifique se o endereço IP da interface de rede que criamos foi estabelecido corretamente.
  ```bash
    sudo netplan apply #aplica alterações 
    ifconfig -a        #verifica alterações
  ```
  * FOTO DA VERIFICAÇÃO
  
  ### Passo 3 - Acesso da VM pelo terminal do PC
  * Vimos que o comando para estabelecer uma conexão é:
    ssh ```<user>```@```<ipServidorRemoto>```
  * Assim, para realizar a conexão via terminal basta alterar os campos ```user``` e ```ipServidorRemoto``` por ```administrador``` e pelo endereço IP correspondente a máquina de preferência. Como no comando abaixo:
   ```bash
    ssh administrador@192.168.13.53
  ```
  * FOTO
  > Note que no comando acima retratamos a conexão em apenas uma VM, mas você pode e deve fazer isso em todas as outras, para testar se as configurações foram feitas com sucesso. 
