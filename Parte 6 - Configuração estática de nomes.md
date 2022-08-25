<h1 align="left"> Configuração estática de nomes</h1>

> NOTA: Está aula tem como objetivo configurar um serviço de nomes e  configurar /etc/hosts.

## Login da VM ubuntu server

* Usuário da VM: administrador.
* Senha da VM: adminifal.

## Configurar o serviço de nomes estáticos.

* Edite os arquivo /etc/hosts conforme as definições da Tabela de Endereços e Nomes.
```bash
sudo nano /etc/hosts
```
* Edite o arquivo acima levando em consideração a tabela abaixo:
```bash
-------------------------------------------------------------------------------------------------
|  DESCRICAO  |         IP        |   HOSTNAME  |              FQDN                  |  ALIASE  |
-------------------------------------------------------------------------------------------------
|   VM1-PC1   |   192.168.13.49   |   vm1-pc1   |   vm1-pc1.grupo4-913.ifalara.net   |   gio1   |
|   VM2-PC1   |   192.168.13.50   |   vm2-pc1   |   vm2-pc1.grupo4-913.ifalara.net   |   gio2   |
|   VM1-PC2   |   192.168.13.51   |   vm1-pc2   |   vm1-pc2.grupo4-913.ifalara.net   |    ju1   |
|   VM2-PC2   |   192.168.13.52   |   vm2-pc2   |   vm2-pc2.grupo4-913.ifalara.net   |    ju2   |
|   VM1-PC3   |   192.168.13.53   |   vm1-pc3   |   vm1-pc3.grupo4-913.ifalara.net   |   cris1  |
|   VM2-PC3   |   192.168.13.54   |   vm2-pc3   |   vm2-pc3.grupo4-913.ifalara.net   |   cris2  |
|   VM1-PC4   |   192.168.13.55   |   vm1-pc4   |   vm1-pc4.grupo4-913.ifalara.net   |   lud1   |
|   VM2-PC4   |   192.168.13.56   |   vm2-pc4   |   vm2-pc4.grupo4-913.ifalara.net   |   lud2   |
-------------------------------------------------------------------------------------------------
```
* FOTO ANEXAR
>NOTA: Faça isso em todas as 8 VMs!!

## Acessando uma VM remotamente


* ssh administrador@192.168.13.56/28


