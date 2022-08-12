#Preparação do ambiente para alocar as VMs

###Acessar o terminal
*Logar com o usuário ```redes```
```bash
 su redes
```
>Senha: admin@Lab92

###Criação dos diretórios e subdiretórios
*As VMs que iremos criar devem ser armazenadas dentro de diretórios e subdiretórios, a fim de organizar nosso ambiente de trabalho. Para isso devemos criar os seguintes diretórios e subdiretórios:

>labredes
>*Este será o diretório principal e por isso deve ser criado na raiz ```/```
```bash
 cd / #o comando cd é reponsável pelo direcionamento nas pastas
 sudo mkdir labredes #o sudo mkdir serve para criar diretórios e subdiretórios
```

*Após criar a pasta ```labredes```, vamos criar os seguintes subdiretórios:
```bash
 sudo mkdir projeto913
 cd /projeto913 #pois queremos criar os futuros subdiretórios nessa pasta
 sudo mkdir images
 cd /images
 sudo mkdir original
 
 #agora, vamos criar os diretórios responsáveis por armazenar as VMs criadas
 cd / #volta para a raiz
 sudo mkdir /labredes/projeto913/VM #estamos usando o caminho absoluto para especificar onde queremos guardar as VMs criadas
 sudo mkdir /labredes/projeto913/913
 sudo mkdir /labredes/projeto913/<student> #o <student> indica que este campo deve ser substituído pelo nome do aluno responsável por este subdiretório
```

*Para verificar a existência dos diretórios criados, basta combinar os comandos ```cd```e ```ls -la```, este último exibe o que está contido em determinado diretório, como apresentado no exemplo abaixo:
>COLOQUEM ALGUMA FIGURA SOBRE ISSO AQUI

