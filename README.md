### Instituto Federal de Alagoas - Campus Arapiraca<br>Disciplina: Infraestrutura e Serviços de Rede<br>Turma: 913 - Informática<br>Grupo 4: Giovanna Stephany Souza da Silva, Júlia Vitória Marques Góis, José Cristiano Costa Sobrinho, Ludmila Barbosa da Silva

<p align="center">Projeto do 2° bimestre - Ambiente de rede contendo 8 máquinas virtuais com o S.O Ubuntu Server<p>

* Tabela 1: Configurações de hardware utilizada nas máquinas virtuais
```
-------------------------------------------------------------------------------------------------------
|          QTDE. DE MEMÓRIA        |         Nº DE PROCESSADORES         |       ESPAÇO EM DISCO      |   
-------------------------------------------------------------------------------------------------------
|              512 MB              |                  1                  |          10,00 GB          |   
-------------------------------------------------------------------------------------------------------
```

* Tabela 2: Definições dos IPs das MVs com a máscara de rede /28 (255.255.255.240).
```
-----------------------------------------------------------------------------------------------
|          SUBREDES         |         REDE         |       BROADCAST      |      GATEWAY      |
-----------------------------------------------------------------------------------------------
|   192.168.13.[48-63]/28   |   192.168.13.48/28   |   192.168.13.63/28   |   192.168.13.49   |
-----------------------------------------------------------------------------------------------
```

* Tabela 3: Definições de endereços IP das MVs, nomes para hostname, nomes de domínio (FQDN), apelidos (aliases).
```
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
