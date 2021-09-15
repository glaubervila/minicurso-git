# Desenvolvimento Colaborativo com Git e GitHub

_________________

Este repositório é parte do mini curso oferecido pelo [LIneA](https://www.linea.gov.br/)

* [Desenvolvimento Colaborativo com Git e GitHub](#desenvolvimento-colaborativo-com-git-e-github)
  + [Objetivo](#objetivo)
  + [Pré requisitos](#pré-requisitos)
  + [Sobre Versionamento](#sobre-versionamento)
    - [Principais Vantagens](#principais-vantagens)
    - [Sobre o Git](#sobre-o-git)
    - [Sobre o GitHub](#sobre-o-github)
    - [O que é um Repositório](#o-que-é-um-repositório)
  + [Vamos a Prática](#vamos-a-prática)
    - [Git Init](#git-init)
    - [Git Status](#git-status)
    - [Git Add](#git-add)
    - [Git commit](#git-commit)
    - [Git log](#git-log)
    - [Git diff](#git-diff)
    - [Git checkout](#git-checkout)
  + [Material de Apoio](#material-de-apoio)

## Objetivo

Introduzir o participante a conceitos básicos de versionamento de código e desenvolvimento colaborativo utilizando as principais ferramentas do mercado Git e Github. O curso vai apresentar os principais comandos utilizados no dia a dia. Espera-se que no final do curso o participante esteja apto a criar o seu próprio repositório ou colaborar com repositórios já existentes.

## Pré requisitos

* Ter previamente instalado o git, pode seguir este [Tutorial de Instalação](https://git-scm.com/book/pt-br/v2/Come%C3%A7ando-Instalando-o-Git).
* Ter uma conta no [GitHub](https://github.com/signup?ref_cta=Sign+up&ref_loc=header+logged+out&ref_page=%2F&source=header-home).
* Ter configurado usuário e senha do github no seu git, seguir este [tutorial](https://git-scm.com/book/pt-br/v2/Come%C3%A7ando-Configura%C3%A7%C3%A3o-Inicial-do-Git)

**TODO:** Gravar um video mostrando a instalação e a configuração.

## Sobre Versionamento

Versionamento é o gerenciamento de versões diferentes de um documento qualquer. Não precisa ser código, pode ser arquivos texto e imagens por exemplo. O versionamento é controlado pelo o que chamamos de sistema de controle de versões. Normalmente, esses sistemas são utilizados no desenvolvimento de software para controlar as diferentes versões e histórico de desenvolvimento do código.

### Principais Vantagens

As principais vantagens de se utilizar um sistema de controle de versão para rastrear as alterações feitas durante o desenvolvimento de software ou o desenvolvimento de um documento de texto qualquer são:

* **Controle do histórico**: facilidade em desfazer e possibilidade de analisar o histórico do desenvolvimento, como também facilidade no resgate de versões mais antigas e estáveis. A maioria das implementações permitem analisar as alterações com detalhes, desde a primeira versão até a última.
* **Trabalho em equipe**: um sistema de controle de versão permite que diversas pessoas trabalhem sobre o mesmo conjunto de documentos ao mesmo tempo e minimiza o desgaste provocado por problemas com conflitos de edições.
* **Marcação e resgate de versões estáveis**: a maioria dos sistemas permite marcar onde é que o documento estava com uma versão estável, podendo ser facilmente resgatado no futuro.
* **Ramificação de projeto**: a maioria das implementações possibilita a divisão do projeto em várias linhas de desenvolvimento, que podem ser trabalhadas paralelamente, sem que uma interfira na outra.
* **Segurança**: Cada software de controle de versão usa mecanismos para evitar qualquer tipo de invasão de agentes infecciosos nos arquivos. Além do mais, somente usuários com permissão poderão mexer no código.
* **Rastreabilidade**: Com a necessidade de sabermos o local, o estado e a qualidade de um arquivo; o controle de versão traz todos esses requisitos de forma que o usuário possa se embasar do arquivo que deseja utilizar.
* **Organização**: Alguns softwares disponibilizam uma interface visual onde podem ser vistos todos os arquivos controlados, desde a origem até o projeto por completo.
* **Confiança**: O uso de repositórios remotos (na nuvem) ajuda a não perder arquivos por eventos inesperados. Além disso, e possível fazer novos projetos sem danificar o desenvolvimento do atual. [Fonte wikipedia](https://pt.wikipedia.org/wiki/Sistema_de_controle_de_vers%C3%B5es#Principais_vantagens)

### Sobre o Git

Git é um sistema de controle de versão distribuído, é gratuito e de código aberto projetado para lidar com tudo, desde projetos pequenos a muito grandes com velocidade e eficiência. [Página Oficial](https://git-scm.com/)

### Sobre o GitHub

GitHub é um serviço de hospedagem de repositórios Git. Enquanto o Git é uma ferramenta de linha de comando, o GitHub fornece uma interface gráfica baseada na web. Ele também fornece controle de acesso e vários recursos de colaboração, como wikis e ferramentas básicas de gerenciamento de tarefas para cada projeto. O GitHub também tem um aspecto de Rede Social ou comunidade de desenvolvedores. Onde qualquer um pode colaborar com projetos abertos.

### O que é um Repositório

Repositório, ou repo, é um diretório onde os arquivos do seu projeto ficam armazenados. Ele pode ser **local**, os arquivos ficam no seu computador ou **remoto** quando os arquivos ficam hospedados no GitHub por exemplo. Você pode armazenar códigos, imagens, áudios, ou qualquer outra coisa relacionada ao projeto no diretório.
__________
**TODO**: Adicionar a explicação do que é branch, commit
_________

## Vamos a Prática

Neste Mini Curso vou mostrar dois caminhos para iniciarmos com o git, o primeiro é criar um repositório do zero e outro é utilizar um repositório já existente fazendo um Clone.

### Git Init

O comando git init cria um novo repositório do Git. Ele pode ser usado para converter um projeto existente e não versionado em um repositório do Git ou inicializar um novo repositório vazio

neste caso vamos iniciar com um diretório vazio que vai se chamar *curso_git*. dentro da pasta execute o comando:

```bash
git init
```

![git init](images/git_init.png)

Feito isso o git vai mostar uma mensagem sugerindo que você mude o nome do branch default de master para main. Vamos seguir a recomendação e executar o seguinte comando:

```bash
git branch -m main
```

Pronto agora já temos nosso repositório com controle de versão, neste momento mesmo sem ter nenhum arquivo, uma estrutura com as informações do git foi criada no repositório no diretório oculto *.git*, não vamos alterar nada neste diretório, mas caso precise alterar alguma configuração do repositório vai ser no arquivo *.git/config*

Agora com o repositório criado precisamos entender como ele funciona.

### Git Status

Git status é o comando responsável por nos informar quais são os arquivos com alterações pendentes para serem adicionados a um commit.

Executando o comando abaixo temos a seguinte saída.

```bash
git status
```

![git status empty](images/git_status_empty.png)

O status nos informou que:

* Estamos trabalhando no Branch main.
* Não temos nenhum commit ainda.
* Não temos nenhum arquivo ou alteração para ser registrada.

Vamos criar um arquivo chamado README.md dentro do nosso repositório, escrever um titulo para nosso projeto e depois, executar o comando status novamente.

![git_status_nao_monitorado](images/git_status_nao_monitorado.png)

Perceba que agora temos um arquivo README.md no repositório que consta como não monitorado isso significa que apesar de estar dentro do repositório este arquivo ainda não está sendo controlado pelo git.  

Antes de adicionarmos este arquivo vamos entender quais estados um arquivo pode ter no repositório.

![git-staging-area](images/git_staging_area.png)

* Working directory - São os arquivos que estão no repositório mais ainda não foram adicionados, as mudanças nestes arquivos ainda não são monitoradas pelo git. estes arquivos não serão considerados quando o usuário realizar um commit.

* Staged/index - São arquivos já selecionados pelo usuário para fazerem parte do próximo commit que será executado.

### Git Add

Este comando server para “adicionar conteúdo” (propor uma mudança qualquer, seja ela alterar, adicionar ou remover um conteúdo) de um arquivo local ao staging area, que terá a mudança confirmada, posteriormente, com o comando git commit, e finalmente enviada ao repositório remoto pelo git push.

Vamos adicionar nosso arquivo README.md com o seguinte comando:

```bash
git add README.md
```

Agora o git status nos mostra que nosso arquivo foi adicionado ao repositório, e está marcado para o proximo commit. após o commit qualquer mudança neste arquivo estará sendo monitorada.

![git-add](images/git_add.png)

Você pode ter mais informações sobre git add na [Documentação](https://git-scm.com/docs/git-add/pt_BR).

### Git commit

Grava as alterações feitas no repositório, Cria um novo commit que tenha todos os conteúdos atuais do índice e a mensagem informada no registro log descrevendo as alterações.

```bash
git commit -m "First Commit"
```

Neste comando o parametro -m representa a mensagem que vai descrever as alterações que foram feitas no repositório.

![git_commit](images/git_commit.png)

Mo resultado o git nos informa quantos arquivos foram modificados, quantas linhas foram alteradas e o short hash do commit *25b0aa6* que funciona como um ID único.

Mais informações na [Documentação](https://git-scm.com/docs/git-commit/pt_BR).

### Git log

O comando git log exibe um log com os commits feitos no repositório, o comando aceita uma serie de parametros para formatar as informações que serão exibidas. Para conhecer todos os parametros consulte a [Documentação](https://git-scm.com/docs/git-log/pt_BR)

Executando git log no nosso repositório neste momento temos esta saida

```bash
git log
```

![git_log](images/git_log.png)

* Commit: é o hash completo para este commit.
* Author: é o autor do commit, aqui serão usadas as informações cadastradas no git de usuario e email.
* Date: data e hora que o commit foi feito.
* Mensagem do commit, no nosso exemplo foi uma unica frase, mas pode ser um texto mais complexo com paragrados.

Vamos agora fazer umas alterações no nosso repositório, 
Vamos alterar o arquivo README.md, simplesmente abrir o arquivo e adicionar uma nova linha e depois criar um novo arquivo chamado GitComandos.md e por ultimo criar um arquivo vazio teste.txt

Depois dessas mudanças nosso repositório está assim:

![git status 2](images/git_status_2.png)

Agora o status nos mostra que o aquivo README.md foi alterado e que temos dois novos arquivos que não estão sendo monitorados ainda.
Vamos adicionar esses arquivos novos arquivos.

```bash
git add GitComandos.md teste.txt
```

![git status 3](images/git_status_3.png)

Note que só adicionei 2 arquivos, deixei o arquivo Modificado separado para mostrar mais alguns comandos são eles o git Diff e o Checkout.

### Git diff

Exibe as mudanças entre os commits, o commit, a árvore de trabalho, etc.
Este comando pode ser usado de varias formas, a mais simples delas serve para exibir as alterações feitas em relação ao índice (área de preparação para o próximo commit). Em outras palavras, as diferenças são as que você pode informar ao Git para adicionar ao índice, mas ainda não o fez. Você pode preparar essas alterações utilizando

```bash
git diff README.md
```

![git diff](images/git_diff.png)

Neste caso o resultado é uma comparação entre o estado atual do arquivo e seu estado atual no branch. em quanto este arquivo não for adicionado com git add para o repositório vale a versão que já foi commit.

O simbolo + indica linhas que foram adicionadas ao arquivo, e - as linhas removidas. uma linha que foi alterada, será exibiba duas vezes uma com - (original) e a outra com + (alterada).

Neste ponto temos duas situações, as mudanças são desejadas queremos que elas façam parte do branch "add", ou por algum motivo precisamos voltar o arquivo para seu estado anterior "checkout".

Para mais informações do comando diff [Documentação](https://git-scm.com/docs/git-diff/pt_BR).

### Git checkout

Alterne entre os branchs ou restaura os arquivos da árvore de trabalho, Atualiza os arquivos na árvore de trabalho para coincidir com a versão no índice ou na árvore informada.

Neste momento vamos ver só como restaurar um arquivo ao seu estado anterior no branch. O comando checkout vai ser bastante utilizado no seu dia a dia, então recomendo uma passada pela [Documentação](https://git-scm.com/docs/git-checkout/pt_BR)

```bash
git checkout README.md
```

![git checkout](images/git_checkout_file.png)

Repare que eu executei o checkout e em seguida fiz um status.
A saída do Status me mostra que o arquivo README.md não tem nenhuma alteração, ele nem aparece mais na lista de modificados, está fora do staging e não será afetado pelo commit.

vamos fazer um commit destas mudanças

```bash
git commit -m "Foi adicionado um arquivo com varios comandos uteis do git."
```

![git commit 2](images/git_commit_2.png)

## Material de Apoio

* [O que é Git E GitHub? - definição e conceitos importantes, por Rafaella Ballerini.](https://www.youtube.com/watch?v=DqTITcMq68k&ab_channel=RafaellaBallerini)
* [Como Usar Git E GitHub na Prática! - desde o primeiro commit até o pull request!, por Rafaella Ballerini.](https://www.youtube.com/watch?v=UBAX-13g8OM&ab_channel=RafaellaBallerini)
* [Como versionar utilizando o Git, por Raphael Batagini.](https://medium.com/biblioteca-dos-devs/como-versionar-utilizando-o-git-1f5d8fe2afcd)
