# Preparação do ambiente para alocar as VMs

### Acessar o terminal
* Inicialmente, é necessário acessar o terminal da máquina e logar com o usuário ```redes``` utilizando o comando:
```bash
 su redes
```
E a senha:
```bash
admin@Lab92
```
Figura 1: Login no usuário redes.

![login_redes](https://user-images.githubusercontent.com/80183918/184625891-ce6bb0c1-d7bc-44c3-93cd-0494ec2057db.png)


### Criação dos diretórios e subdiretórios
* As VMs que iremos criar devem ser armazenadas dentro de diretórios e subdiretórios, a fim de organizar nosso ambiente de trabalho. Para isso devemos criar os seguintes diretórios e subdiretórios:

```bash
labredes
```
Este será o diretório principal e por isso deve ser criado na raiz ```/```
```bash
 cd / # Ocomando cd é reponsável pelo direcionamento nas pastas
 sudo mkdir labredes # O sudo mkdir serve para criar diretórios e subdiretórios, nesse caso, dentro do diretório labredes
 ls -la # Comando usado para exibir a lista de diretórios da máquina, neste caso, comprovar que o diretório labredes já está criado
```
Figura 2: Criação dos diretórios e subdiretórios.

![Inkedimg2](https://user-images.githubusercontent.com/80183918/184629311-e31af470-a492-4349-af77-94f94b1ea9b1.jpg)

* Para prosseguir com a organização, após criar a pasta ```labredes```, vamos criar os seguintes subdiretórios:
```bash
 sudo mkdir projeto913 # Lembre-se de que estamos dentro do diretório labredes, logo, projeto913 será seu subdiretório 
 cd /projeto913 # Comando utilizado para entrar no subdiretório projeto913 e criar os futuros subdiretórios nele 
 sudo mkdir images # Comando para a criação da pasta images dentro de projeto913
 cd /images # Comando para entrar no subdiretório images
 sudo mkdir original # Comando para criar o subdiretório original dentro de images
 ```
 Fugura 3:  Comprovar a existência dos diretórios e subdiretórios

 ![img3](https://user-images.githubusercontent.com/80183918/184630201-cd243df9-9fa5-4ca3-b428-7e8a2b497d74.png)

 * Listagem para comprovar que todos os diretórios e subdiretórios foram criados:
 
  Fugura 4:Realização dos diretórios responsáveis em armazenar as VMs.

![img5](https://user-images.githubusercontent.com/80183918/184630977-b9082983-71b7-4e4d-9446-e5de33611dda.png)
 
 * Criação dos diretórios responsáveis por armazenar as VMs criadas
 ```bash
 cd / # Volta para a raiz
 sudo mkdir /labredes/projeto913/VM # Comando utilizado para criar a pasta VM dentro de projeto913 e usando o caminho absoluto para especificar onde queremos guardar as VMs criadas
 sudo mkdir /labredes/projeto913/VM/913 # Comando utilizado para criar a pasta 913 dentro de projeto913
 sudo mkdir /labredes/projeto913/VM/913/<student> # Comando utilizado para criar a pasta do aluno dentro do subdiretório 913, <student> indica que este campo deve ser substituído pelo nome do aluno responsável
```
Figura 5: Criação dos diretórios VMs, 913 e <student>.
 
![img6](https://user-images.githubusercontent.com/80183918/184631448-d4b1810b-1224-4eb5-afa4-d95234d00961.png)

* OBS: Como observado em algumas das imagens acima, para verificar a existência dos diretórios criados, basta combinar os comandos ```cd``` e ```ls -la```

### Arquivo ubuntu
 * Para que a criação das VMs possa ser realizada, precisamos que haja em ```labredes/projeto913/images/original``` o arquivo ```ubuntu-server-mini.ova```. Para isso, verifique a existencia desse arquivo no subdiretório ```original```.
 * Se o arquivo ```ubuntu-server-mini.ova``` não for encontrado no subdiretório mas existir em uma pasta diferente basta copia-lo usando o comando ```sudo cp```:
 ```bash
 sudo cp /labredes/images/original/ubuntu-server-mini.ova /labredes/projeto913/images/original
 # O comando cp irá copiar o arquivo presente no primeiro caminho para o diretório do segundo caminho
```
 * Por fim, basta verificar se o arquivo foi copiado usando o comando ```ls -la```.
 
 Figura 6: Verificação do arquivo
 
 ![img7](https://user-images.githubusercontent.com/80183918/184632848-e818798d-58aa-4935-b778-a750428c68e8.png)

 
