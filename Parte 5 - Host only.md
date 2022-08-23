# Host Only

> Nesta parte do nosso projeto de trabalhar com VM's, vamos aprender como nos conectar às VM's criadas, utilizando o terminal do computador em que estamos trabalhando. Assim, para fazer isso, iremos utilizar o comando ```ssh``` (explicado na aula anterior) e o coneceito de ```Host-Only``` (o qual será explicado adiante).

## Passo 1 - Login nas VM's
  Utilizando o VirtualBox se conecte às VM's que você criou.
  * Usuário: administrador
  * Senha: adminifal 

## Passo 2 - Interface de comunicação
  Após se conectar às VM's, precisamos configurar uma interface que possibilite a comunicação entre ela e o PC, isso deve ser feito pois queremos nos comunicar com a VM utilizando o terminal de um computador, que nesse caso será o nosso ```Host```.
  * Dentro do VirtualBox, clique em ```Arquivo``` e logo após em ```Host Network Manager```, seguido por ```Adaptador```. 
  * FOTO
  > É importante que os valores dos campos estejam iguais aos da imagem acima. 
  
  ### Configuração do servidor DHCP 
  Ainda dentro do ```Network Manager```, selecione o campo ```Servidor DHCP```.
  * Certifique-se de habilitar o servidor DHCP, clicando em ```Habilitar Servidor```.
  * FOTO
  * Após verificar se os campos estão preenchidos como mostrador na imagem acima, aplique as configurações clicando em ```Aplicar```. 
  > Pelo ```terminal do PC```, verifique se a configuração foi realizada com sucesso utilizando o comando:
  ```bash
    ifconfig-a #você saberá se a configuração foi bem sucedida se aparecer a interface: vxboxnet0
  ```
