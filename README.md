# Utilizando o Git Submodules

Uma dica bem legal, principalmente para quem já lidava com o Subversion como versionador: o Git dispõe de uma funcionalidade chamada [Git Submodules](https://git-scm.com/book/en/v2/Git-Tools-Submodules), que nada mais são que repositórios dentro de repositórios. Um pouco parecido com o [Externals](http://svnbook.red-bean.com/en/1.5/svn.advanced.externals.html) do SVN.

Funcionalidades assim surgiram devido a necessidades de inserir uma biblioteca ou outro projeto em outros projetos. No entanto, são projetos distintos, e seus desenvolvimentos são totalmente independentes. Esse tipo de problema deve ser encarado com o GitSubmodules e com o próprio Git – resolver o problema dessa dependência externa.

O Submodule permite que você mantenha o repositório Git como um subdiretório de outro repositório Git, o que permite um clone de outro repositório dentro do seu, além de permitir commits totalmente separados. Legal, não é?

Exemplo de uso: preciso inserir no meu projeto um repositório com arquivos CSV para importação. Esse repositório vive recebendo updates. Nesse caso, você irá apenas consumir esses arquivos CSV ( Comma Separated Values ) para importação local na sua base de dados.
