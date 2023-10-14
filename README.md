# SMACSS e BEM

> Modulo 19 - EBAC

## SMACSS

> Vide branch `smacss`

O **SMACSS** (Scalable and Modular Architecture for CSS) é uma abordagem para organizar o CSS em cinco categorias:

- Base;
- Layout;
- Módulo;
- Estado;
- Tema.

Ele promove a reutilização de código, redução de redundância e geralmente torna o CSS mais fácil de trabalhar.

### Usar SMACSS com LESS ou SASS

SMACSS se encaixa muito bem com o uso de pré-processadores, porque ele encoraja a modularização do CSS, o que os pré-processadores também fazem muito bem.

Quando usado com um pré-processador como **SASS** ou **LESS**, podemos dividir o CSS em arquivos separados de acordo com as categorias **SMACSS** e depois importá-los todos em um único arquivo principal. Por exemplo, poderiamos ter um arquivo `base.less`, um arquivo `layout.less`, etc. E então importá-los todos em um `main.less`.

Em seguida, podemos usar uma ferramenta de compilação como **Gulp** ou **Grunt** para compilar o arquivo `main.less` em um arquivo `style.css` que pode ser usado em o site.

**Isso permite que você mantenha o CSS organizado e modular durante o desenvolvimento, mas ainda tenha um único arquivo CSS para produção.**

Aqui está um exemplo de como podemos organizar os arquivos **LESS**/**SASS** usando **SMACSS**:

```ruby
📦 styles
┣ 📜 main.less
┣ 📂 base
┃ ┣ 📜 reset.less
┃ ┗ 📜 typography.less
┣ 📂 layout
┃ ┣ 📜 header.less
┃ ┣ 📜 footer.less
┃ ┗ 📜 grid.less
┣ 📂 modules
┃ ┣ 📜 button.less
┃ ┗ 📜 slider.less
┣ 📂 state
┃ ┣ 📜 active.less
┃ ┗ 📜 hidden.less
```

E então no `main.less`, importariamos todos esses arquivos:

```ruby
@import "base/reset";

@import "base/typography";

@import "layout/header";

@import "layout/footer";

@import "layout/grid";

@import "modules/button";

@import "modules/slider";

@import "state/active";

@import "state/hidden";
```

Depois, você pode usar o **Gulp** ou **Grunt** para **compilar** o `main.less` em `style.css`.

---

## BEM

> Vide branch `bem`

Ela foi criada para facilitar a manutenção e escalabilidade de folhas de estilo CSS em projetos web complexos. Ela é composta por:

- Block;
- Element;
- Modifier.

### Blocos (Block)

O bloco é a parte principal e mais geral de um componente ou elemento de interface. Por exemplo, um botão, um formulário, um cabeçalho ou um menu de navegação podem ser blocos.

### Elementos (Element)

Elementos são **partes menores** e **específicas** de um bloco que não fazem sentido por si só e só têm significado dentro do contexto do bloco ao qual pertencem. Elementos são nomeados usando um duplo sublinhado (**). Por exemplo, dentro do bloco "`botão`", você pode ter elementos como "`ícone`" ou "`rótulo`" representados como "`botao**icone`" e "`botao\_\_rotulo`".

### Modificadores (Modifier)

Os modificadores são usados para **criar variações** de um bloco ou elemento. Eles permitem que você aplique diferentes estilos ou comportamentos a um bloco ou elemento sem a necessidade de criar classes CSS separadas. Modificadores são nomeados usando um duplo hífen (--). Por exemplo, um botão pode ter um modificador de tamanho chamado "`botao--grande`" para aumentar seu tamanho.
