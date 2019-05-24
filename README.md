# Utilizando o Git Submodules

Uma dica bem legal, principalmente para quem já lidava com o Subversion como versionador: o Git dispõe de uma funcionalidade chamada [Git Submodules](https://git-scm.com/book/en/v2/Git-Tools-Submodules), que nada mais são que repositórios dentro de repositórios. Um pouco parecido com o [Externals](http://svnbook.red-bean.com/en/1.5/svn.advanced.externals.html) do SVN.

Funcionalidades assim surgiram devido a necessidades de inserir uma biblioteca ou outro projeto em outros projetos. No entanto, são projetos distintos, e seus desenvolvimentos são totalmente independentes. Esse tipo de problema deve ser encarado com o GitSubmodules e com o próprio Git – resolver o problema dessa dependência externa.

O Submodule permite que você mantenha o repositório Git como um subdiretório de outro repositório Git, o que permite um clone de outro repositório dentro do seu, além de permitir commits totalmente separados. Legal, não é?

Exemplo de uso: preciso inserir no meu projeto um repositório com arquivos CSV para importação. Esse repositório vive recebendo updates. Nesse caso, você irá apenas consumir esses arquivos CSV ( Comma Separated Values ) para importação local na sua base de dados.

### Mão na Massa

```
git submodule add <url-repositorio> diretorio
```
 
Exemplo: git submodule add git@bitbucket.org:rivendel/csv-imports.git import/csv

No comando acima, estamos adicionando um submodule à pasta import/csv.

Temos agora na raiz do nosso projeto um arquivo chamado .gitmodules com as devidas configurações já feitas, e uma pasta em import/csv criada e funcionando como um repositório.

### Inicializando o Submodule

```
git submodule init
```

O init vai iniciar as configurações necessárias para o trabalho dos SubModules.

### Atualizando as configurações

```
git submodule update
```

Esse comando irá carregar toda a configuração necessária, caso tenha feito alterações em seus submodulos.

### Atualizando a dependência

Primeiro, acesse a pasta do seu submodulo:

```
cd imports/csv
```

Depois, vamos executar o comando pull:

```
git pull remote your_branch #git pull origin master por exemplo
```

### Como isso tudo funciona?

Ao usar o git pull, dentro de um Submodule, temos um projeto dentro de outro. Nesse caso, o Git vai gravar o hash do submódulo, e não do seu conteúdo. Assim, ao criar um submódulo, você acaba adicionando uma versão de outro projeto ao seu.

Caso queira a versão mais nova do Submodule, basta executar os mesmos comandos que executa com seu repositório normalmente.

Assim como o Push, a única diferença é que esses comandos devem ser executados com você já estando dentro da pasta do submódulo. Como podem ver, o uso do Submodules é simples e útil inclusive para controle de dependências.
