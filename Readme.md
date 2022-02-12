# Como usar o Git e o Github no Linux

Como estou usando um Linux Ubuntu, irei fazer esse tutorial por aqui mesmo. Irei atualizar conforme for aprendendo coisas novas do Git e Github.  

# O que é controle de versão?

É um sistema com a finalidade de gerenciar diferentes versões de um mesmo documento. Existem mais de um sistema de controle de versão, mas atualmente o mais utilizado é o Git.

No Git, toda vez que um arquivo muda, é criado um snapshot dele. Ele é responsável por versionar os arquivos de um mesmo projeto. 

Os outros sistemas trabalham com as diferenças dos arquivos. Já o git trabalha com os seus estados.

# Configurações do Git no Linux

Lembrando que ele já vem de padrão, então não é necessário instalar nada (Isso no Linux).

Você poderá dar início a algumas configurações utilizando os códigos a seguir em qualquer terminal:

## Para dar o nome do usuário
```bash 
git config --global user.name "Nome do usuário"
``` 
## Para dar o e-mail do usuário
```bash
git config --global user.email "email@exemplo.com"
```
## Para definir o editor principal
```bash
git config --global core.editor code
```
* Note que o editor utilizado foi o VSCode, mas poderia ter sido qualquer outro como o vim, sublime text, etc.

## Para ver as configurações feitas
Você pode usar uma chave como "user.name" ou "core.editor" ou ainda ver a lista com todas as configurações feitas:
### Usando uma chave
```bash
git config user.name
```
### Listando todas
```bash
git config --list
```
# Criando um diretório e um arquivo pelo editor de texto VScode

Para criar um diretório, com o VScode já instalado, acesse a pasta onde você deseja criar o diretório pelo terminal com o comando cd. Para exemplificar, estarei utilizando a pasta Documentos
```bash
cd Documentos
```
ao acessar o local, crie o diretório com o comando
```bash
mkdir nome_do_diretorio
```
com o diretório criado, crie o arquivo apenas utilizando o código
```bash
code Readme.md
```
* Nesse exemplo estamos utilizando um arquivo .md mas você poderá utilizar qualquer tipo de arquivo que desejar. 
* Dá pra fazer manualmente também mas aí vai de você preferir.

Salve o arquivo com ctrl + s

# Inicializando um git dentro do diretório

Para dar início a um Git, não há segredo. apenas acesse o diretório do arquivo pelo terminal do editor após salvar o arquivo criado (e se o terminal não abrir com o diretório aberto) com 
```bash 
cd nome_do_diretorio
```
e logo após apertar o enter, digite o seguinte código:
```bash
git init
```
Dê enter e assim o diretório em que estão seus arquivos terá um git iniciado.

# Como funciona o Git?
O Git possui 4 camadas.

> A primeira é chamada de untracked

Nessa camada não há arquivo. Mesmo que você tenha criado um arquivo, enquanto não adicioná-lo ao git, ele não vai existir dentro do Git. Deve-se adicionar o Git dentro do diretório com o "git init" para que ele mude de camada.

> A segunda camada é chamada de unmodified

Nesse momento o arquivo está dentro do Git já, porem ele ainda não foi modificado. Nessa etapa, você deve editar o arquivo edar "ctrl + s". Logo ele estará disponível na próxima camada.

> A terceira camada é chamada de modified

Nesse momento o arquivo está modificado, porém ainda não está salvo, assim que você o adicionar, ele irá para a próxima camada.

> A última camada se chama staged

Nesse momento, só restará uma ação a ser feita, que é utilizar o comando para comitar o arquivo, ou seja, atualizar sua versão.

Após feito isso, ele voltará a se referir ao arquivo como unmodified

# Como adicionar e entregar o arquivo ao Git?

Após você ter criado e salvo o arquivo, poderá adicioná-lo a camada "staged" usando o seguinte comando:
```bash
git add Readme.md
```
* Repare que novamente utilizei um arquivo qualquer, mas você pode adicionar o que quiser, não apenas um .md

depois disso, basta comita-lo como comando
```bash
git commit -m "Mensagem explicando as mudanças"
```
Ele voltará a camada de "unmodified" e é exatamente o que queremos.
* Para adicionar todos os arquivos de uma só vez, utilizar -am ao invés de apenas -m
* O comando -m identifica uma mensagem a deixar no sistema, como boa prática, a mensagem a ser deixada deve explicar a mudança feita no arquivo.
* O comando -a adiciona todos os arquivos a serem entregados.

Agora sempre que for editar o arquivo, repetir esses dois comandos, lembrando: 
* Primeiro edite, adicione e então comite.
### Verificando status do git

Para saber em que camada dentro do Git o seu arquivo se encontra, segue o seguinte comando:
```bash
git status
```
# Vizualizar logs e edições

Logs são as edições já feitas dentro do Git após a entrega do mesmo. não só isso mas através deles você pode saber quem alterou o que puxando ele pelo usuário, também se descobre a data e horário exato que as alterações foram feitas.

Abaixo darei algumas ideias de como puxar os logs.

## Todos os logs com todas as informções
```bash
git log
```
* Ele mostra a hash do commit (que é a sua identificação), quem foi o autor da versão e o email, a data e horário e uma mensagem para o commit definida pelo usuário.

## Filtrando pelo autor

Você pode filtrar todos os Gits criados por um único autor:
```bash
git log --author="Nome do autor"
```
* Ele vai mostrar todos os Gits feitos pelo autor buscado.

## Resumo do log
 Com esse comando é possivel verificar quais são os autores, quantos Gits cada um deles fez e quais foram.
 ```bash
git shortlog
```
Há ainda uma forma de reduzir ainda mais esse resumo, mostrando apenas o nome dos contribuintes e a quantidade de Gits feitos:
```bash
git shortlog -sn
```
## Gráficos no Git
Esse log mostra de forma gráfica o que está acontecendo com os branches em cada versão:
```bash
git log --graph
```
## Hash
Dentro do log há essa hash. Com essa hash que seria a identificação do Git, éw possível identificar o que foi adicionado dentro do commit, o que aconteceu com ele. Para exemplificar vou colocar uma hash qualquer e o comando que nos mostrará o que houve dentro do commit.
```bash
git show 5f80faeeba3c5be643864a1136318784b4468e31
``` 
* A hash do seu commit ficará ao lado da palavra commit, após você comitar e dar um log no Git poderá ver essa hash que é composta de letras e números.

# Vizualizar diferenças antes de comitar
Para vizualizar as diferenças antes do commit, caso você queira verificar e analisar, procurando por algo errado e ter certeza de que está tudo certinho para commitar, utilize o comando:
```bash
git diff
```
Com ele poderá ser vizualizado as diferenças antes de comitar. 

Há ainda uma forma de vizualizar somente o nome do arquivo que foi modificado. Serve por exemplo para o caso de você ter uma lista grande com vários arquivos modificados. O código é o seguinte:
```bash
git diff --name-only
```









> logo mais atualizarei com mais informações sobre o Git e com as informações ainda não dadas sobre o Github.