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
            └── main.css.scss
            └── form.css.scss
            └── components.css.scss
            └── sprite-generator.css.scss
```

**base** será o arquivo contendo: _variáveis_, _mixins_, _includes_, _extends_ e _helpers_ considere utilizar neste arquivos seus utilitários.

**general** será o arquivo contendo a formatação **geral**, o que as páginas tem em comum.

**typography** será o arquivo responsável pela estilização da tipografia, tamanho, pesos, estilos, font-face, etc..

**main** será o arquivo contendo a ordem de chamadas para cada arquivo.

**page, pageN** será o arquivo gerado pelo `rails` referente ao estilo de cada página.

**form** será o arquivo contendo toda a formatação dos formulários (caso o projeto tenha), serão: _labels_, _inpust_, _textarea_, etc...

**components** serão todos todos os componentes do projeto: botões, barras de progresso, nav, alertas, tabelas, etc..

**sprite-generator** será o arquivo responsável pela geração automática de sprites com o auxílio da biblioteca _compass_.



## Overview

- A linguagem adotada para todos os projetos é **en-US**.
- Usamos **SCSS**.
- Mantenha **baixa especificidade** _(no máximo 2 níveis)_.
- `rem` para fontes e `px` para os outros.
- Use nomes **claros** e **diretos** que não engessem sua _classe_ e/ou _id_.
- Não estilize elementos utilizando _id's_, use apenas _classes_.
- **Nomeie** suas _classes_ e _id's_ de **acordo com a função** do elemento, nunca pela aparência.
- Para classes compostas, **utilize o hífen** como separador e tipografia em **lowercase**. `.my-class`
- Caso a sua classe represente um estado do elemento, ela deverá ser prefixada com o `is-`. Ex: `.is-active`


## Formatação

- Padronize a ordem de declaração utilizando o [CSSComb](http://csscomb.com/ "CSSComb").


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


## Padrões adotados

Analizamos os principais padrões adotados pela comunidade para criar o nosso.

- [SMACSS](http://smacss.com/ "SMACSS")
- [KSS](https://github.com/kneath/kss "KSS")
- [DRY](http://www.vanseodesign.com/css/dry-principles/ "DRY")
- [Atomic Design](http://bradfrostweb.com/blog/post/atomic-web-design/ "Atomic Design")
- [BEM](http://bem.info/method/ "BEM")
- [OOCSS](http://oocss.org "OOCSS")
