# Preparação do ambiente para alocar as VMs

### Acessar o terminal
* Inicialmente, é necessário acessar o terminal e logar com o usuário ```redes```
```bash
 su redes
```
> Senha: admin@Lab92


### Criação dos diretórios e subdiretórios
* As VMs que iremos criar devem ser armazenadas dentro de diretórios e subdiretórios, a fim de organizar nosso ambiente de trabalho. Para isso devemos criar os seguintes diretórios e subdiretórios:


> labredes
* Este será o diretório principal e por isso deve ser criado na raiz ```/```
```bash
 cd / #o comando cd é reponsável pelo direcionamento nas pastas
 sudo mkdir labredes #o sudo mkdir serve para criar diretórios e subdiretórios
```

> Organização dos diretórios
* Após criar a pasta ```labredes```, vamos criar os seguintes subdiretórios:
```bash
 sudo mkdir projeto913 #lembre-se de que estamos dentro do diretório labredes
 cd /projeto913 #pois queremos criar os futuros subdiretórios nessa pasta
 sudo mkdir images
 cd /images
 sudo mkdir original
 
 #agora, vamos criar os diretórios responsáveis por armazenar as VMs criadas
 cd / #volta para a raiz
 sudo mkdir /labredes/projeto913/VM #estamos usando o caminho absoluto para especificar onde queremos guardar as VMs criadas
 sudo mkdir /labredes/projeto913/913
 sudo mkdir /labredes/projeto913/<student> #o <student> indica que este campo deve ser substituído pelo nome do aluno responsável
```

* Para verificar a existência dos diretórios criados, basta combinar os comandos ```cd``` e ```ls -la```, este último exibe o que está contido em determinado diretório, como apresentado no exemplo abaixo:
COLOQUEM ALGUMA FIGURA SOBRE ISSO AQUI

### Arquivo ubuntu
 * Para que a criação das VMs possa ser realizada, precisamos que haja em ```labredes/projeto913/images/original``` o arquivo ```ubuntu-server-mini.ova```. Para isso, verifique a existencia desse arquivo no subdiretório ```original```.
 * Se o arquivo ```ubuntu-server-mini.ova``` não for encontrado no subdiretório mas existir em uma pasta diferente basta copia-lo usando o comando ```sudo cp```:
 ```bash
 sudo cp /labredes/images/original/ubuntu-server-mini.ova /labredes/projeto913/images/original
 #o comando cp irá copiar o arquivo presente no primeiro caminho para o diretório do segundo caminho
```
 * Por fim, basta verificar se o arquivo foi copiado usando o comando ```ls -la```.
 
