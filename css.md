# CSS

Inspirado em diversos guias, sejam atuais ou antigos e práticas adotadas por 
grandes companhias, resolvemos adotar o padrão de desenvolvimento Guava. 
Abaixo seguem as convenções adotadas para escrita de CSS.


## Estrutura

Abaixo segue a estrutura dos arquivos que utilizamos.

```
├── app
  └── assets
        └── stylesheets
            └── base.css.scss
            └── general.css.scss
            └── typography.css.scss
            └── application.css.scss
            └── form.css.scss
            └── components.css.scss
            └── sprite-generator.css.scss
```

**base** será o arquivo contendo: _variáveis_, _mixins_, _includes_, _extends_ e _helpers_ considere utilizar neste arquivos seus utilitários.

**general** será o arquivo contendo a formatação geral, seria o que as páginas tem em comum.

**typography** será o arquivo responsável pela estilização da tipografia, tamanho, pesos, estilos, font-face, etc..

**application** será o arquivo contendo a ordem de chamadas para cada arquivo usando o `@import`.

**page, pageN** será o arquivo gerado pelo `rails` referente ao estilo de cada página.

**form** será o arquivo contendo toda a formatação dos formulários (caso o projeto tenha), serão: _labels_, _inpust_, _textarea_, etc...

**components** serão todos todos os componentes do projeto: botões, barras de progresso, nav, alertas, tabelas, etc..

**sprite-generator** será o arquivo responsável pela geração automática de sprites com o auxílio da biblioteca _compass_.



## Overview

- A linguagem adotada para todos os projetos é **en-US**.
- Usamos **SCSS**.
- `Indentação` apenas com `2 spaces`.
- Use o `.editorconfig` em todos os seus projetos para manter o nosso padrão.
- Mantenha **baixa especificidade** _(no máximo 2 níveis)_.
- `rem` para fontes e `px` para os outros.
- Use nomes **claros** e **diretos** que não engessem sua _classe_ e/ou _id_.
- Não estilize elementos utilizando _id's_, use apenas _classes_.
- **Nomeie** suas _classes_ e _id's_ de **acordo com a função** do elemento, nunca pela aparência.
- Para classes compostas, **utilize o hífen** como separador e tipografia em **lowercase**. `.my-class`.
- Use **shorthand** sempre que possível. Ex: `padding: 15px 0;`.
- Caso a sua classe represente um estado do elemento, ela deverá ser prefixada com o `is-`. Ex: `.is-active`.
- Caso a sua classe seja ativada invocada pelo javascript, ela deverá ser prefixada com o `js-`. Ex: `.js-open-content-menu` e não deverá ser estilizada.


## Formatação

- Instale o [CSSComb](http://csscomb.com/ "CSSComb") no seu editor e use o arquivo `.csscomb.json` para padronizar seu código com o restante da equipe.
- No arquivo `main.css.scss` utilize comentários e observe a ordem das chamadas para separar de forma lógica o `@import` dos arquivos.



**Código**

- Separe de forma lógica as partes da sua folha de estilo.
- Agrupamento de seletores ou propriedades devem ser inseridas um **abaixo do outro**. 
- Um espaço antes e depois da abertura das chaves. `.my-class { width: 100%; }`
- Um único espaço antes da abertura das chaves e após os dois pontos da declaração. `.my-class { width: 100%; }`
- Valores hexadecimais em caixa baixa.
- Use **aspas simples** sempre que possível.
- Para valores múltiplos que necessitam de vírgula, dê um espaço entre esses valores. `linear-gradient(45deg, blue, red)`.
- O valor zero (0) não acompanha unidade.
- **Sempre** utilizar ponto e vírgula no final de cada declaração de propriedade.


**Comentários**

- Comente o seu código sempre que possível.
- Os **comentários** serão escritos todos de forma **simples e objetiva**, com apenas a primeira letra da frase em maiúscula. `//Classe utilizada para habilitar o botão de download`
- Evite **comentários** no final da linha, inclua-os **no início**.
- Comentários se dividem em **grupo**, **linha** e **blocos**.


## Referências

Analizamos os principais padrões adotados pela comunidade e por grandes empresas para criar o nosso, caso tenha interesse indicamos você ler os links abaixo :)


**Padrões**

- [SMACSS](http://smacss.com/ "SMACSS")
- [KSS](https://github.com/kneath/kss "KSS")
- [DRY](http://www.vanseodesign.com/css/dry-principles/ "DRY")
- [Atomic Design](http://bradfrostweb.com/blog/post/atomic-web-design/ "Atomic Design")
- [BEM](http://bem.info/method/ "BEM")
- [OOCSS](http://oocss.org "OOCSS")

**Artigos**
- [Trello](http://blog.trello.com/refining-the-way-we-structure-our-css-at-trello/ "Trello")
- [Codepen](http://codepen.io/chriscoyier/blog/codepens-css "Codepen")
- [Groupon](http://mikeaparicio.com/2014/08/10/css-at-groupon/ "Groupon")
- [Github](http://markdotto.com/2014/07/23/githubs-css/ "Github")
- [Medium](http://blog.trello.com/refining-the-way-we-structure-our-css-at-trello/ "Medium")
- [Buffer](http://blog.brianlovin.com/buffers-css/ "Buffer")
