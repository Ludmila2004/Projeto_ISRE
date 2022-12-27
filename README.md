### Instituto Federal de Alagoas - Campus Arapiraca<br>Disciplina: Infraestrutura e Serviços de Rede<br>Turma: 913 - Informática<br>Grupo 4: Giovanna Stephany Souza da Silva, Júlia Vitória Marques de Góis, José Cristiano Costa Sobrinho, Ludmila Barbosa da Silva

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

* Imagem que mostra as configurações de rede das VM's do PC1.

![Captura de tela de 2022-09-02 11-46-58](https://user-images.githubusercontent.com/80183918/188178147-9800a550-4bdb-44c9-b0b1-cf14647406e5.png)

* Imagem que mostra as configurações de rede das VM's do PC2.

![Captura de tela de 2022-09-02 11-49-56](https://user-images.githubusercontent.com/80183918/188178051-a743071f-d05d-40df-9894-7765367ea04e.png)

* Imagem que mostra as configurações de rede das VM's do PC3.

![Captura de tela de 2022-09-02 11-52-28](https://user-images.githubusercontent.com/80183918/188178219-60447757-6ce5-4ed6-92cd-4e6e8837a5cc.png)

* Imagem que mostra as configurações de rede das VM's do PC4.

![Captura de tela de 2022-09-02 11-55-51](https://user-images.githubusercontent.com/80183918/188178370-14a6ecdc-3a64-4637-aec2-4b3923ba200e.png)


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
## Considerações finais
  Com este projeto, percebeu-se a importância de tornar o processo de alteração de hostnames, de aliases, de endereçamento IP e de outros componentes essenciais para uma infraestrura de rede de maneira dinâmica, pois do contrário o trabalho de configuração torna-se complexo, exaustivo e mais suscetível a erros, haja vista a mecanização dos processos realizados.
  
## Partições:
* [Parte 1 - Preparação do ambiente](https://github.com/Ludmila2004/Projeto_ISRE/blob/main/Parte%201%20-%20Prepara%C3%A7%C3%A3o%20do%20ambiente.md)
* [Parte 2 - Rede ponto a ponto entre VMs](https://github.com/Ludmila2004/Projeto_ISRE/blob/main/Parte%202%20-%20Rede%20ponto%20a%20ponto%20entre%20VMs.md)
* [Parte 3 - Rede ponto a ponto entre PCs](https://github.com/Ludmila2004/Projeto_ISRE/blob/main/Parte%203%20-%20Rede%20ponto%20a%20ponto%20entre%20PCs.md)
* [Parte 4 - Acesso remoto SSH](https://github.com/Ludmila2004/Projeto_ISRE/blob/main/Parte%204%20-%20Acesso%20remoto%20SSH.md)
* [PARTE 5 - Host Only](https://github.com/Ludmila2004/Projeto_ISRE/blob/main/Parte%205%20-%20Host%20only.md)
* [Parte 6 - Configuração estática de nomes](https://github.com/Ludmila2004/Projeto_ISRE/blob/main/Parte%206%20-%20Configura%C3%A7%C3%A3o%20est%C3%A1tica%20de%20nomes.md)
* [Parte 7 - Adicionando usuários e alterando hostnames](https://github.com/Ludmila2004/Projeto_ISRE/blob/main/Parte%206%20-%20Configura%C3%A7%C3%A3o%20est%C3%A1tica%20de%20nomes.md)

