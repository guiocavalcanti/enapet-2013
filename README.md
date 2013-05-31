# Projeto de site do ENAPET 2013

## Estrutura

Abaixo a estrutura de arquivo do site.

```sh
.
├── README.md
├── front-end
│   ├── css # Arquivos CSS
│   │   └── vendor # Arquivos CSS de terceiros
│   ├── img # Imagens utilizadas no projeto
│   │── js # Arquivos JavaScript
│       └── vendor # Arquivos JavaScript de terceiros
└── layout
    ├── dist  # PNGs das páginas do site
    ├── fonts # Fontes (Goolge Fonts)
    ├── icons # Ícones utilizados no projeto
    ├── images # Imagens utilizadas no projeto
    └── src # Arquivo fonte compatível com Fireworks CS6
        └── layout.png
```

## Documentação

São descritas nesta seção como integrar e customizar o layout.

### Transição de imagens

Para transição das imagens é utilizado o plugin do jQuery: [backgrounder](https://github.com/guiocavalcanti/jquery.backgrounder).

#### Adição de novas imagens

Para adicionar uma nova imagem à transição, é necessário adicionar a regra correspondente no css, por exemplo:

```css
  .imagem-nova {
    background: url("img/paris.jpg");
  }
```

Após isso, deve-se adicionar esta nova classe à chamada do [backgrounder](https://github.com/guiocavalcanti/jquery.backgrounder). Da seguinte forma:

```js
$(document).ready(function(){
  $('.event-call').backgrounder(["image-1", "image-2", "image-nova"]);
});
```

#### Customização do efeito de transição

Pode-se alterar o tempo de transição do efeito fade (`transitionTime`), bem como o tempo em que a imagem é mostrada (`displayTime`). Basta alterar os parâmetros da chamada ao backgrounder:

```js
$('.event-call').backgrounder(
  ["image-1", "image-2", ],
  { transitionTime: 3000, displayTime: 8000 }
);
```

### Centralização dos menus

Para centralizar a navegação, seja ela superior ou inferior, basta utilizar a classe `centered` na tag `<nav>`. Por exemplo:

```html
<div class="navigation">
  <nav class="navbar centered clearfix">
    <div class="container">
      <ul>
        <li><a href="index.html" title="Início">Início</a></li>
        <li><a href="generic.html" title="Informações">Informações</a></li>
        <li><a href="generic.html" title="Inscrições">Inscrições</a></li>
        <li><a href="schedule.html" title="Programação">Programação</a></li>
        <li class="active"><a href="news.html" title="Notícias">Notícias</a></li>
        <li><a href="contact.html" title="Contato">Contato</a></li>
      </ul>
    </div>
  </nav>
</div>
```
