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
* Note que o editor utilizado foi o VSCode, mas poderia ter sido qualquier outro como o vim, sublime text, etc.

## Para ver as configurações feitas
Você pode usar uma chave como "user.name" ou ore.editor" ou ver a lista com todas as configurações feitas:
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
code nome_do_arquivo.md
```
* Nesse exemplo estamos utilizando um arquivo .md mas você poderá utilizar qualquer tipo de arquivo que desejar. 
* Dá pra fazer manualmente também mas aí vai de você preferir.

Salve o arquivo com ctrl + s

# Inicializando um git dentro do diretório

Para dar início a um Git, não há segredo. apenas acesse o diretório do arquivo pelo terminal do editor após salvar o arquivo criado (e se o terminal não abrir com o diretório aberto) com 
```bash 
cd nome_da_pasta
```
e logo após apertar o enter, digite o seguinte código:
```bash
git init
```
Dê enter e assim o diretório em que estão seus arquivos terá um git iniciado.

# Como funciona o Git?
O Git possui 4 camadas.

>A primeira é chamada de <font color=red>untracked</font> 

Nessa camada não há arquivo, mesmo que você tenha criado um arquivo, enquanto não adicioná-lo ao git, ele não vai existir dentro do Git.

> A segunda camada é chamada de <font color=orange>unmodified</font>

Nesse momento o arquivo está dentro do Git já, porem ele ainda não foi modificado. Nessa etapa, você deve editar o arquivo. Logo ele estará disponível na próxima camada.

> A terceira camada é chamada de <font color=yellow>modified</font>

Nesse momento o arquivo está modificado, porém ainda não está salvo, assim que você o salvar utilizando o atalho crtl + s, ele irá para a próxima camada.

> A última camada se chama <font color=green>staged</font>

Nesse momento, só restará uma ação a ser feita, que é utilizar o comando para entregar o arquivo, ou seja, atualizar sua versão.

Após feito isso, ele voltará a se referir ao arquivo como unmodified

# Como adicionar o arquivo ao Git?

Após você ter criado e salvo o arquivo, poderá adicioná-lo ao Git usando o seguinte comando:
```bash
git add Readme.md
```
* Repare que novamente utilizei um arrquivo qualquer, mas você pode adicionar o que quiser, não apenas um .md

depois disso, basta atualiza-lo sempre que precisar com o comando 
```bash
git commit -m "Mensagem explicando as mudanças"
```
* Para adicionar todos os arquivos de uma só vez, utilizar <font color=blue>-am</font> ao invés de apenas -m
* O comando <font color=blue>-m</font> identifica uma mensagem a deixar no sistema, como boa prática, a mensagem a ser deixada deve explicar a mudança feita no arquivo.
* O comando <font color=blue>-a</font> adiciona todos os arquivos a serem entregados.

> logo mais atualizarei com mais informações sobre o Git e com as informações ainda não dadas sobre o Github.