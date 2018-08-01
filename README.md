<h1 align="center">
<br>
  <img src="https://raw.githubusercontent.com/thedaviddias/Front-End-Performance-Checklist/master/images/logo-front-end-performance-checklist.jpg" alt="Front-End Performance Checklist" width="170">
  <br>
    <br>
  Checklist de Performance Front-End
  <br>
</h1>

<h4 align="center">🎮 O único checklist de performance front-end que roda mais rápido que os outros.</h4>
<p align="center">Apenas uma regra simples: "Faça o design e programe pensando em performance"</p>

<p align="center">
  <a href="http://makeapullrequest.com">
    <img src="https://img.shields.io/badge/PRs-welcome-brightgreen.svg?style=flat-square" alt="PRs são bem vindas">
  </a>
  <a href="https://gitter.im/Front-End-Checklist/Lobby?utm_source=share-link&utm_medium=link&utm_campaign=share-link">
    <img src="https://img.shields.io/badge/chat-on_gitter-008080.svg?style=flat-square" alt="Gitter">
  </a>
    <a href="https://opensource.org/licenses/MIT">
    <img src="https://img.shields.io/badge/license-MIT-blue.svg?style=flat-square" alt="Licence MIT">
  </a>
</p>

<p align="center">
  <a href="#how-to-use">Como usar</a> • <a href="#contributing">Contribuir</a> • <a href="https://www.producthunt.com/posts/front-end-performance-checklist">Product Hunt</a>
</p>
<p align="center">
    <span>Outros Checklists:</span>
    <br>
  🗂 <a href="https://github.com/thedaviddias/Front-End-Checklist#---------front-end-checklist-">Checklist de Front-End</a> • 💎 <a href="https://github.com/thedaviddias/Front-End-Design-Checklist#front-end-design-checklist">Checklist de Design Front-End</a>
</p>

## Índice

1.  **[HTML](#html)**
2.  **[CSS](#css)**
3.  **[Fontes](#fonts)**
4.  **[Imagens](#images)**
5.  **[JavaScript](#JavaScript)**
6.  **[Servidor](#server) (em progresso)**
7.  **[Frameworks JS](#js-frameworks) (em progresso)**

## Introdução

Performance é um assunto gigante, mas nem sempre é um assunto de "back-end" ou "admin": também é uma responsabilidade do Front-End. O Checklist de Performance Front-End é uma lista extensa de elementos que você deve conferir ou ao menos estar ciente como um desenvolvedor Front-End e aplicar em seu projeto (pessoal ou profissional).

### Como usar?

Para cada regra, você vai encontrar um parágrafo explicando _por que_ essa regra é importante e _como_ você pode aplicá-la. Para entender melhor, você encontrará links que te direcionarão a 🛠️ ferramentas, 📖 artigos ou 📹️mídias que complementam o checklist.

Todos os itens no **Checklist de Performance Front-End** são essenciais para alcançar o melhor resultado de performance mas você encontrará um indicador para te auxiliar a eventualmente priorizar algumas regras perante outras. Existem 3 níveis de prioridade / impacto:

- ![Baixo][low] significa que o item tem **pouco** impacto e prioridade no seu projeto.
- ![Médio][medium] significa que o item tem **médio** impacto e prioridade no seu projeto. Você não deve evitar resolver esse item.
- ![Alto][high] significa que o item tem **alto** impacto e prioridade no seu projeto. Você não pode evitar seguir a regra e aplicar as correções apropriadas.

### Ferramentas de performance

Lista de ferramentas que você pode usar para testar ou monitorar o seu website ou aplicação:

- 🛠 [WebPagetest - Teste de Performance e Otimização de Websites](https://www.webpagetest.org/)
- 🛠 ☆ [Dareboost: Teste de Velocidade para Website e Análise de Website](https://www.dareboost.com/) (use o cupom WPCDD20 para ter -20%)
- 🛠 [GTmetrix | Otimização de Velocidade e Performance de Website](https://gtmetrix.com/)
- 🛠 [PageSpeed Insights](https://developers.google.com/speed/pagespeed/insights/)
- 📖 [Pagespeed - A ferramenta e guia de otimização](https://varvy.com/pagespeed/)
- 📖 [Torne a web mais rápida | Google Developers](https://developers.google.com/speed/)
- 📖 [Sitespeed.io - Bem Vindo ao maravilhoso mundo da Performance da Web](https://www.sitespeed.io/)

### Referências

- 📖 [O Custo do JavaScript - YouTube](https://www.youtube.com/watch?v=_bzqF05xsC4)
- 📖 [Entenda a Análise de Performance em Tempo de Execução  |  Google Developers](https://developers.google.com/web/tools/chrome-devtools/evaluate-performance/)
- 📖 [A Situação da Web | 2018_01_01](https://httparchive.org/reports/state-of-the-web?start=2018_01_01)
- 📖 [O Peso da Página não Importa](https://www.speedshop.co/2015/11/05/page-weight-doesnt-matter.html)

---

## HTML

![html]

- [ ] **HTML Minificado:** ![medium] O código HTML está minificado, comentários, _white spaces_ e novas linhas são removidas dos arquivos de produção.

  _Por que:_

  > Remover todo o espaço desnecessário, comentarios e quebras reduz o tamanho do seu HTML e acelera o tempo de carregamento do seu site e obviamente reduz o peso do download para o usuário.

  _Como:_

  > ⁃ A maioria dos frameworks possuem plugins para facilitar a minificação das páginas web. Você pode usar uma porção de módulos do NPM que farão o trabalho pra você automaticamente..

  - 🛠 [Minifcador HTML | Minify Code](http://minifycode.com/html-minifier/)
  - 📖 [Experiências com com Minficador HTML — Perfection Kills](http://perfectionkills.com/experimenting-with-html-minifier/#use_short_doctype)

- [ ] **Remover comentários desnecessários:** ![low] Garanta que os comentários serão removidos de suas páginas.

  _Por que:_

  > Comentários não são úteis para o usuário e portanto devem ser removidos dos arquivos de produção. Um caso em que você manteria comentários poderia ser quando precisa manter a origem para uma biblioteca.

  _Como:_

  > ⁃ Na maior parte do tempo, comentários podem ser removidos com um plugin de minificação HTML.

* 🛠 [remove-html-comments - npm](https://www.npmjs.com/package/remove-html-comments)

- [ ] **Remover atributos desnecessários:** ![low] Atributos Type como `type="text/JavaScript"` ou `type="text/css"` não são mais necessários e devem ser removidos.

  ```html
  <!-- antes do HTML5 -->
  <script type="text/JavaScript">
      // código JavaScript
  </script>

  <!-- Hoje -->
  <script>
      // código JavaScript
  </script>
  ```

  _Por que:_

  > Atributos Type não são necessários já que o HTML5 supõe text/css e text/JavaScript por padrão. Código inutilizado deve ser removido quando não forem usados no seu website ou aplicação por deixarem as páginas mais pesadas.

  _Como:_

  > ⁃ Certifique-se de que todas as _tags_ `<link>` e `<script>` não têm nenhum atributo type.

  - 📖 [A Tag de Script | CSS-Tricks](https://css-tricks.com/the-script-tag/)

- [ ] **Sempre coloque as _tags_ de css antes das de JavaScript:** ![high] Certifique-se de que o seu CSS sempre é carregado antes de ter código JavaScript.

  ```html
  <!-- Não recomendado -->
  <script src="jquery.js"></script>
  <script src="foo.js"></script>
  <link rel="stylesheet" href="foo.css"/>

  <!-- Recomendado -->
  <link rel="stylesheet" href="foo.css"/>
  <script src="jquery.js"></script>
  <script src="foo.js"></script>
  ```

  _Por que:_

  > Ter o CSS antes do JavaScript posibilita um melhor download paralelo que torna o tempo de renderização do navegador mais rápido.

  _Como:_

  > ⁃ Certifique-se que as tags `<link>` e `<style>` no `<head>` sempre vêm antes de qualquer `<script>`.

  - 📖 [Ordenando seus estilos e scripts para o carregamento da página](https://varvy.com/pagespeed/style-script-order.html)

- [ ] **Reduza a quantidade de iframes:** ![high] Somente use iframes se não há nenhuma outra possibilidade técnica. Evite tanto quanto o possível utilizar iframes.

**[⬆ Topo](#table-of-contents)**

## CSS

![css]

- [ ] **Minificação:** ![high] Todos os arquivos CSS está minificado, comentários, _white spaces_ e novas linhas são removidas dos arquivos de produção.

  _Por que:_

  > Quando os arquivos CSS são minificados, o conteúdo é carregado mais rapidamente e menos dados são enviados ao cliente. É importante sempre minificar os arquivos CSS em produção.Isso é benéfico para o usuário e também para negócios que desejam dimminuir o custo de banda e reduzir o uso de recursos.

  _Como:_

  > ⁃ Use ferramentas para minificar seus arquivos automaticamente antes ou durante o _build_ ou _deploy_.

  - 🛠 [cssnano: Um minificador modular baseado no ecossistema PostCSS](https://cssnano.co/)
  - 🛠 [@neutrinojs/style-minify - npm](https://www.npmjs.com/package/@neutrinojs/style-minify)

- [ ] **Concatenação:** ![medium] Arquivos CSS são concatenados em um único arquivo _(Nem sempre é válido para HTTP/2)_.

  ```html
  <!-- Não recomendado -->
  <script src="foo.js"></script>
  <script src="ajax.js"></script>

  <!-- Recomendado -->
  <script src="combined.js"></script>
  ```

  _Por que:_

  > Se ainda estiver usando HTTP/1, você talvez precise concatenar seus arquivos, é menos indicado se o seu servidor usa HTTP/2 (é necessário testar).

  _Como:_

  > ⁃ Use uma ferramenta online ou algum plugin antes ou durante o _build_ ou _deploy_ do seu projeto para concatenar arquivos.
  > ⁃ Certifique-se, claro, que a concatenação não quebre o seu projeto.

  - 📖 [HTTP: Otimizando a Entrega de Aplicações - Alta performance em Conexão do Navegador(O'Reilly)](https://hpbn.co/optimizing-application-delivery/#optimizing-for-http2)
  - 📖 [Melhores Práticas de Performance na Era do HTTP/2](https://deliciousbrains.com/performance-best-practices-http2/

- [ ] **Não-obstrusivo:** ![high] Arquivos CSS precisam ser não-obstrusivos para prevenir que o DOM demore de carregar .

  ```html
  <link rel="preload" href="global.min.css" as="style" onload="this.rel='stylesheet'">
  <noscript><link rel="stylesheet" href="global.min.css"></noscript>
  ```

  _Por que:_

  > Arquivos CSS podem bloquear o carregamento da página e atrasar a renderização da sua página. Usar `preload` pode carregar os arquivos CSS antes que o navegador comece a mostrar o conteúdo da página.

  _Como:_

  > ⁃ Você precisa adicionar o atributo `rel` com o valor `preload` e incluir `as="style"` no elemento `<link>`.

  - 📖 [loadCSS por filament group](https://github.com/filamentgroup/loadCSS)
  - 📖 [Exemplo de pré-carregamento de CSS usando loadCSS](https://gist.github.com/thedaviddias/c24763b82b9991e53928e66a0bafc9bf)
  - 📖 [Pré-carregamento de conteúdo com rel="preload"](https://developer.mozilla.org/en-US/docs/Web/HTML/Preloading_content)
  - 📖 [Pré-carregamento: Pra que serve? — Smashing Magazine](https://www.smashingmagazine.com/2016/02/preload-what-is-it-good-for/)

- [ ] **Tamanho das classes CSS:** ![low] O tamanho das suas classes pode causar (baixo) impacto nos seus arquivos HTML e CSS (eventualmente).

  _Por que:_

  > Até mesmo os impactos de performance podem ser contestados, tomar uma decisão sobre a estratégia de nomenclatura do seu projeto pode ter um impacto não trivial na manutenção das suas folhas de estilo. Se estiver usando BEM, em alguns casos, você pode acabar com classes que possuem mais caracteres do que precisam. É sempre importante escolher com sabedoria os nomes e _namespaces_.

  _Como:_

  > ⁃ Definir um limite em termos de número de caracteres pode ser interressante para algumas pessoas, mas garantir que você desmembrou o seu website em componentes pode ajudar a reduzir a quantidade de classes (e declarações) e o tamanho das suas classes.

  - 🛠 [classe longa vs curta · jsPerf](https://jsperf.com/long-vs-short-class)

- [ ] **CSS inutilizado:** ![medium] Remova seletores CSS inutlizados.

  _Por que:_

  > Remover seletores CSS inutilizados pode reduzir o peso dos seus arquivos e acelerar o carregamento dos seus _assets_.

  _Como:_

  > ⁃ ⚠️ Sempre verifique se o framework de CSS que você quer usar já não possui código de _reset/normalize_. Às vezes você pode não precisar de tudo que está incluído no arquivo de _reset/normalize_.

  - 🛠 [UnCSS Online](https://uncss-online.com/)
  - 🛠 [PurifyCSS](https://github.com/purifycss/purifycss)
  - 🛠 [PurgeCSS](https://github.com/FullHuman/purgecss)
  - 🛠 [Cobertura das Ferrramentas de Desenvolvedor do Chrome](https://developers.google.com/web/updates/2017/04/devtools-release-notes#coverage)

* [ ] **CSS Crítico:** ![high] O CSS crítico (ou "sobre a dobra") contém todo o CSS usado para renderizar a parte visível da página. ele é incorporado antes da chamada principal do seu CSS e entre `<style></style>` numa única linha (minificado se possível).

  _Por que:_

  > Deixar o CSS crítico _inline_ ajuda a acelerar a renderização de páginas web reduzindo o número de requisições ao servidor.

  _Como:_

  > ⁃ Gere o CSS crítico com ferramentas online ou usando um plugin como o que Addy Osmani desenvolveu.

  - 📖 [Entendendo o CSS Crítico](https://www.smashingmagazine.com/2015/08/understanding-critical-css/)
  - 🛠 [Critical por Addy Osmani no GitHub](https://github.com/addyosmani/critical) automatiza isso.
  - 📖 [Deixando o CSS crítico _inline_ para ter melhor performance na web | Go Make Things](https://gomakethings.com/inlining-critical-css-for-better-web-performance/)
  - 📖 [Gerador de CSS de Caminho Crítico Critical - Priorize contéudo acima da dobra :: SiteLocity](https://www.sitelocity.com/critical-path-css-generator)

- [ ] **CSS incorporado ou _inline_:** ![high] Evite usar CSS incorporado ou _inline_ dentro do seu `<body>` _(não válido para HTTP/2)_

  _Por que:_

  > Uma das principais razões é que é boa prática **separar conteúdo de design**. Também te ajuda a ter um código mais sustentável e mantém o seu site aceesível. Mas com relação a performance, é simplesmente por diminuir o peso do arquivo das suas páginas HTML e tempo de carregamento.

  _Como:_

  > ⁃ Sempre use folhas de estilo externas ou incorpore o CSS no seu `<head>` (e siga as outras regras de performance).

  - 📖 [Observe as Melhores Práticas de CSS: Evite Usar Estilos CSS _Inline_](https://www.lifewire.com/avoid-inline-styles-for-css-3466846)

- [ ] **Analise a complexidade das folhas de estilo:** ![high] Analisar as suas folhas de estilo pode te ajudar a encontrar problemas, redundâncias e seletores CSS duplicados.

  _Por que:_

  > Às vezes você pode ter redundancias ou erros de validação no seu CSS, analisar os arquivos CSS e remover essas complexidades pode te ajudar a acelerar os arquivos CSS (já que seu navegador vai ler mais rápido).

  _Como:_

  > ⁃ O seu CSS deve estar organizado, Pré-processadores CSS podem te ajudar com isso. Algumas ferramentas online listadas acima também podem te ajudar a analisar e corrigir o seu código.

  - 🛠 [TestMyCSS | Otimize e Confira a Performance do CSS](http://www.testmycss.com/)
  - 📖 [CSS Stats](https://cssstats.com/)
  - 🛠 [macbre/analyze-css: Analizador de complexidade e performance de seletores CSS](https://github.com/macbre/analyze-css)

**[⬆ Topo](#table-of-contents)**

## Fontes

![fonts]

- 📖 [A Book Apart, Guia de Bolso para Webfonts](https://abookapart.com/products/webfont-handbook)

* [ ] **Formato de Webfont:** ![medium] Você usa WOFF2 no seu projeto ou aplicação web.

  _Por que:_

  > De acordo com o Google, a compressão do formato WOFF 2.0 oferece ganhos de 30% em média com relação ao WOFF 1.0. Portanto é bom usar WOFF 2.0, WOFF 1.0 como _fallback_ e TFF.

  _Como:_

  > ⁃ Antes de comprar sua nova fonte garanta que o fornecedor te entregue o formato WOFF2. Se estiver usando uma fonte grátis, você pode usar o Font Squirrel para gerar todos os formatos que precisar.

  - 📖 [WOFF 2.0 – Aprenda mais sobre a próxima geração de Formato Webfont e converta TFF para WOFF2](https://gist.github.com/sergejmueller/cf6b4f2133bcb3e2f64a)
  - 🛠 [Crie Seus Próprios Kits @font-face » Font Squirrel](https://www.fontsquirrel.com/tools/webfont-generator)
  - 📖 [Usando @font-face | CSS-Tricks](https://css-tricks.com/snippets/css/using-font-face/?ref=frontendchecklist)
  - 📖 [Can I use... WOFF2](https://caniuse.com/#feat=woff2)

* [ ] **Use `preconnect` para carregar suas fontes mais rápido:** ![medium]

  ```html
  <link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
  ```

  _Por que:_

  > Quando você acessa um website, seu dispositivo precisa encontrar onde o o site está hospedado e a qual servidor ele precisa se conectar. Seu navegador precisou acessar um servidor DNS e esperar até a consulta completar antes de buscar os recursos (fontes, arquivos CSS...). Usar `prefetch` e `preconnect` permite ao navegador reduzir o tempo de carregamento da página.

  _Como:_

  > ⁃ Antes de usar `prefetch` nas suas _webfonts_, use o webpagetest para avaliar o seu site.
  > ⁃ Procure por consultas DNS azul-petróleo e anote os _hosts_ que são solicitados.
  > ⁃ Coloque Prefetch nas fontes de dentro do seu `<head>` e eventualmente inclua esses _hostnames_ que você deveria dar _prefetch_ também.

  - 📖 [Fontes Google mais rápidas com Preconnect - CDN Planet](https://www.cdnplanet.com/blog/faster-google-webfonts-preconnect/)
  - 📖 [Torne seu site mais rápido com avisos Preconnect | Viget](https://www.viget.com/articles/make-your-site-faster-with-preconnect-hints/)
  - 📖 [Guia Final para Avisos do Navegador: Preload, Prefetch, e Preconnect - MachMetrics Speed Blog](https://www.machmetrics.com/speed-blog/guide-to-browser-hints-preload-preconnect-prefetch/)
  - 📖 [Guia Abrangente de Carregamento de Fontes Strategies—zachleat.com](https://www.zachleat.com/web/comprehensive-webfonts/#font-face)

* [ ] **Tamanho de Webfonts:** ![medium] O Tamanho das Webfonts não ultrapassa 300kb (com todas as variantes)

- 📖 [Font Bytes - Peso das Páginas](https://httparchive.org/reports/page-weight#bytesFont)

**[⬆ Topo](#table-of-contents)**

## Imagens

![images]

- 📖 [Bytes de Imagens em 2018](https://httparchive.org/reports/page-weight#bytesImg)

- [ ] **Otimização de Imagens:** ![high] Suas imagens são otimizadas, comprimidas sem impacto direto ao usuário final.

  _Por que:_

  > Imagens otimizadas carregam mais rápido no navegador e consomem menos dados.

  _Como:_

  > ⁃ Tente usar efeitos do CSS3 quando possível (no lugar de imagens pequenas)
  > ⁃ Quando possível use fontes no lugar de texto dentro de imagens
  > ⁃ Use SVG
  > ⁃ Use uma ferramenta e especifique uma taxa de compressão abaixo de 85

  - 📖 [Otimização de Imagens | Fundamentos da Web | Google Developers](https://developers.google.com/web/fundamentals/performance/optimizing-content-efficiency/image-optimization)
  - 🛠 [TinyJPG – Comprima imagens JPEG inteligentemente](https://tinyjpg.com/)

* [ ] **Formato de Imagens:** ![high] Escolha o formato das suas imagens apropriadamente.

  _Por que:_

  > Para certificar que as suas mensagens não deixam seu site lerdo, escolha o formato que terá o menor impacto

  _Como:_

  > ⁃ Use o [Lighthouse](https://developers.google.com/web/tools/lighthouse/) para identificar quais imagens podem eventualmente usar **formatos da próxima geração** (como JPEG 2000m, JPEG XR ou WebP)
  > ⁃ Compare formatos diferentes, algumas vezes usar PNG8 é melhor que PNG16, e outras não.

  - 📖 [Entregue Imagens em Formatos da próxima geração |  Ferramentas para Desenvolvedores Web |  Google Developers](https://developers.google.com/web/tools/lighthouse/audits/webp)
  - 📖 [Qual é o Formato de Imagem Certo Para o Seu Site? — SitePoint](https://www.sitepoint.com/what-is-the-right-image-format-for-your-website/)
  - 📖 [PNG8 - O Vencedor Evidente — SitePoint](https://www.sitepoint.com/png8-the-clear-winner/)
  - 📖 [8-bit vs 16-bit - Qual Profundidade de Cor Você Deveria Usar e Por que Importa - DIY Photography](https://www.diyphotography.net/8-bit-vs-16-bit-color-depth-use-matters/)

- [ ] **Use imagens vetorizadas em favor de raster/bitmap:** ![medium] Prefira usar iamgem vetorizada em vez de _bitmap_ (quando possível).

  _Por que:_

  > Imagens vetorizadas (SVG) costumam ser mais leves que _bitmap_ e SVGs são responsivos e redimencionam perfeitamente. Essas imagens podem ser animadas e modificadas com CSS.

* [ ] **Dimensões das Imagens:** ![medium] Defina atributos `width` e `height` nas `<img>` se o tamanho final da imagem exibida é conhecido.

  _Por que:_

  > Se a altura e largura da imagem são definidos, o espaço necessário para a imagem é reservado quando a página é careregada. Mas sem esses atributos o navegador não sabe o tamanho da imagem, e não pode reservar o espaço apropriado para ela. Isso causa mudança no layout da página enquanto as imagens estão sendo carregadas.

* [ ] **Evite usar imagens Base64:** ![medium] Você pode chegar a converter iamgens muito pequenas para base64 mas na verdade isso não é uma melhor prática.

  - 📖 [Codificação em Base64 & Performance, Parte 1 e 2 by Harry Roberts](https://csswizardry.com/2017/02/base64-encoding-and-performance/)
  - 📖 [Um olhar mais atento para performance de imagem Base64 – The Page Not Found Blog](http://www.andygup.net/a-closer-look-at-base64-image-performance/)
  - 📖 [Quando fazer codificação em base64 de imagens (e quando não fazer) | David Calhoun](https://www.davidbcalhoun.com/2011/when-to-base64-encode-images-and-when-not-to/)
  - 📖 [Base64 encoding images for faster pages | Performance and seo factors](https://varvy.com/pagespeed/base64-images.html)

* [ ] **Atrasar o carregamento:** ![medium] As imagens são carregadas apenas quando seriam exibidas para o usuário (Um _fallback noscript_ sempre é fornecido).

  _Por que:_

  > Isso vai melhorar o tempo de resposta da página atual e evitar carregar imagens desnecessárias que o usuário pode não precisar.

  _Como:_

  > ⁃ Use o [Lighthouse](https://developers.google.com/web/tools/lighthouse/) para ver quais **imagens estão fora da tela**.
  > ⁃ Use um plugin JavaScript como o _lazyload_ para carregar suas imagens.

  - 🛠 [verlok/lazyload: Github](https://github.com/verlok/lazyload)
  - 📖 [Atrasando o Carregamento Imagens e Video  |  Fundamentos da Web  |  Google Developers](https://developers.google.com/web/fundamentals/performance/lazy-loading-guidance/images-and-video/)
  - 📖 [5 Maneiras Brilhantes para Atrasar o Carregamento de Imagens Para Carregamentos Rápido de Páginas - Dynamic Drive Blog](http://blog.dynamicdrive.com/5-brilliant-ways-to-lazy-load-images-for-faster-page-loads/)

* [ ] **Imagens responsivas:** ![medium] Certifique-se de entregar imagens que são próximas do tamanho da tela.

  _Por que:_

  > Aparelhos pequenos não precisam de imagens maiores que a resolução deles. É recomendado ter várias versões de uma imagem em diferentes tamanhos.

  _Como:_

  > ⁃ Crie tamanhos de imagem diferentes para os aparelhos que você quer suportar.
  > ⁃ Use `srcset` e `picture` para entregar várias versões de uma imagem.

  - 📖 [Imagens Responsivas - Aprenda desenvolvimento web | MDN](https://developer.mozilla.org/en-US/docs/Learn/HTML/Multimedia_and_embedding/Responsive_images)

**[⬆ Topo](#table-of-contents)**

## JavaScript

![JavaScript]

- [ ] **Minificação de JS:** ![high] Todos os arquivos JavaScript estão minificados, comentários, _white space_ e novas linhas foram removidas dos arquivos de produção _(válido mesmo se usando HTTP/)_

  _Por que:_

  > Remover os espaços desnecessários, comentários e quebras reduz o tamanho dos seus arquivos JavaScript e acelera o carregamento das páginas do seu site e obviamente reduz o peso de download para o usuário.

  _Como:_

  > ⁃ Use as ferramentas online recomendadas abaixo para minificar os seus arquivos automaticamente antes ou durante o seu _build_ ou _deploy_.

  - 📖 [uglify-js - npm](https://www.npmjs.com/package/uglify-js)
  - 📖 [Leitura rápida: Qual a diferença do HTTP/2? Ainda devemos minificar e concatenar?](https://scaleyourcode.com/blog/article/28)

* [ ] **Nenhum JavaScript no meio:** ![medium] _(Só vale para website)_ Evite ter multiplos códigos JavaScript incorporados no meio do _body_. Reagrupe seu código JavaScript dentro de arquivos externos, no `<head>` ou no fim da sua página (antes do `</body>`).

  _Por que:_

  > Incorporar código JavaScript diretamente no `<body>` pode tornar a página lenta já que será carregado enquando o DOM é construído. A melhor opção é usar arquivos externos com `async` ou `defer` para evitar bloquear o DOM. Outra opção é colocar alguns scripts no `<head>`.

  _Como:_

  > ⁃ Certifique-se de que todos os seus arquivos são carregados usando `async` ou `deferP e escolha sabiamente o código que será inserido no`<head>`.

  - 📖 [11 Dicas para Otimizar JavaScript e Melhorar o Tempo de Carregamento de Websites](https://www.upwork.com/hiring/development/11-tips-to-optimize-JavaScript-and-improve-website-loading-speeds/)

* [ ] **JavaScript sem bloqueio:** ![high] Arquivos JavaScript são carregados assincronamente utilizando atributo `async` ou deferidos com o atributo `defer`.

  ```html
  <!--  Atributo Defer -->
  <script defer src="foo.js">

  <!-- Atributo Async -->
  <script async src="foo.js">
  ```

  _Por que:_

  > JavaScript bloqueia o _parse_ normal de um documento HTML, então quando o _parser_ encontra uma _tag_ `<script>` (especialmente se está dentro do `<head>`), ele para para buscar e executa-la. Adicionar `async` ou `defer` é altamente recomendado se seus scripts estão localizados no topo da sua página mas menos importante se estiverem logo antes da _tag_ `</body>`. Mesmo assim é boa prática usar esses atributos para evitar problemas de performance.

  _Como:_

  > ⁃ Coloque o atributo `async` (se o script não depende de outros scripts) ou `defer` (se o script depende de outro ou é necessário para outro script).
  > ⁃ Se tiver scripts pequenos, considere deixar _inline_ acima dos scripts assíncronos.

  - 📖 [Remova JavaScript que Bloqueia o Render](https://developers.google.com/speed/docs/insights/BlockingJS)

* [ ] **Bibliotecas JS Otimizadas e Atualizadas:** ![medium] todas as bibliotecas JavaScript utilizadas no seu projeto são necessárias (dê preferência para JavaScript Puro para funcionalidades simples), atualizadas para a ultima versão e não sobrecarregam o seu JavaScript com métodos desnecessários.

  _Por que:_

  > Na maior parte do tempo, versões mais novas têm otimizações e correções de segurança. Você deve usar o código mais otimizado para acelerar o seu projeto e garantir que não vai deixar seu website ou aplicação lento com _plugins_ destualizados.

  _Como:_

  > ⁃ Se o seu projeto usa pacotes NPM, [npm-check](https://www.npmjs.com/package/npm-check) é uma biblioteca interessante para atualizar suas bibliotecas.

  - 📖 [Talvez você não precise do jQuery](http://youmightnotneedjquery.com/)
  - 📖 [JavaScript Puro para construir aplicações web poderosas](https://plainjs.com/)

- [ ] **Confira o limite de tamanho das dependências:** ![low] Faça questão de suar bibliotecas externas sabiamente, muitas vezes você pode usar uma biblioteca mais leve para ter a mesma funcionalidade.

  _Por que:_

  > Talvez você queira usar um dos 745.000 pacotes que você pode encontrar no [npm](https://www.npmjs.com/), mas você deve encontrar o melhor pacote para sua necessidade. Por exemplo, o MomentJS é uma biblioteca maravilhosa mas com muitos métodos que talvez você nunca use, é por isso que o Day.js foi criado. Ele pesa 2kB gz contra 16.4 kB do Moment.

  _Como:_

  > ⁃ Sempre compare e escolha a biblioteca melhor e mais leve para as suas necessidades. Você pode usar ferramentas como [npm trends](http://www.npmtrends.com/) para comparar o número de downloads de pacotes NPM ou [Bundlephobia](https://bundlephobia.com/) para saber o tamanho das suas dependências.

  - 🛠 [ai/size-limit: Impeça Inchaço de bibliotecas JS. Se você acidentalmente incluir uma dependeência gigantesca, o Size Limit vai lançar um erro.](https://github.com/ai/size-limit)
  - 📖 [webpack-bundle-analyzer - npm](https://www.npmjs.com/package/webpack-bundle-analyzer)
  - 📖 [Limite de Tamanho: Torne a Web Mais Leve — Crônicas do Marciano, blog do time Evil Martians](https://evilmartians.com/chronicles/size-limit-make-the-web-lighter)

- [ ] **Perfilamento JavaScript:** ![medium] Confira os problemas de performance dos seus arquivos JavaScript (e CSS também).

  _Por que:_

  > A complexidade do JavaScript pode deixar a performance de execução lenta. Identificar esses possíveis problemas é essencial para oferecer a experieência de usuário mais polida.

  _Como:_

  > ⁃ Use a ferramenta Linha do Tempo nas Ferramentas de Desenvolvedor do Chrome para analisar os eventos de script e encontrar os que demoram demais.

  - 📖 [Acelere a execução de JavaScript  |  Ferramentas para Desenvolvedores Web  |  Google Developers](https://developers.google.com/web/tools/chrome-devtools/rendering-tools/js-execution)
  - 📖 [Perfilamento de JavaScript com as Ferramentas de Desenvolvedor do Chrome — Smashing Magazine](https://www.smashingmagazine.com/2012/06/JavaScript-profiling-chrome-developer-tools/)
  - 📖 [Como registrar instantâneos de pilha |  Ferramentas para Desenvolvedores Web  |  Google Developers](https://developers.google.com/web/tools/chrome-devtools/memory-problems/heap-snapshots)
  - 📖 [Capítulo 22 - Perfilando o Frontend - Blackfire](https://blackfire.io/docs/book/22-frontend-profiling)

**[⬆ Topo](#table-of-contents)**

## Servidor

![server-side]

- [ ] **Peso da página < 1500 KB:** ![high] (idealmente < 500 KB) Reduza o peso da sua página e recursos o máximo que puder.

  _Por que:_

  > Idealmente você deve tentar alcançar < 500KB mas análises da web mostram que a média é por volta de 1500KB (até em _mobile_). Dependendo do sua audiência, conexão e aparelhos é importante reduzir tanto quanto possível o total de kilbytes para alcançar a melhor experiência de usuário possível.

  _Como:_

  > ⁃ Todas as regras do Checklist de Performance Front-End te ajudará a reduz ao máximo seus recursos e código.

  - 📖 [Peso da Página](https://httparchive.org/reports/page-weight#bytesTotal)
  - 🛠 [Quanto Custa o meu Site?](https://whatdoesmysitecost.com/)

- [ ] **Tempo de carregamento das páginas < 3 segundos:** ![high] Reduza ao máximo o tempo de carregamento das suas páginas para entregar rapidamente o seu conteúdo aos usuários.

  _Por que:_

  > Quanto mais rápido o seu site ou app mais for, menor é a probabilidade de _bounces_, em outras palavras você terá menos chance de perder o usuário ou futuro cliente. Várias pesquisas provam isso.

  _Como:_

  > ⁃ Use ferramentas online como [Page Speed Insight](https://developers.google.com/speed/pagespeed/insights/) ou [WebPageTest](https://www.webpagetest.org/) para analisar o que pode estar te atrasando e use o Checklist de Performance Front-End para melhorar o tempo de carregamento.

  - 🛠 [Compare a velocidade do seu site em aparelhos móveis](https://www.thinkwithgoogle.com/feature/mobile/)
  - 🛠 [Teste a velocidade e performance do seu site - Think With Google](https://testmysite.thinkwithgoogle.com/?_ga=1.155316027.1489996091.1482187369)
  - 📖 [Tempo médio de carregamento em 2018 - Como está o seu? - MachMetrics Speed Blog](https://www.machmetrics.com/speed-blog/average-page-load-times-websites-2018/)

- [ ] **Tempo até o primeiro byte < 1.3 segundos:** ![high] Reduza ao máximo o tempo que o navegador espera até receber dados.

  - 📖 [O que é a espera (TTFB) no DevTools, e o que fazer sobre ela](https://scaleyourcode.com/blog/article/27)
  - 📖 [Monitorar os seus servidores com ferramentas grátis é facil](https://scaleyourcode.com/blog/article/7)

* [ ] **Tamanho dos _cookies_:** ![medium] Se estiver usando _cookies_ certifique-se de que cada cookie não ultrapassa 4096 bytes e o seu domínio não possui mais de 20 _cookies_.

  _Por que:_

  > _cookies_ são trocados nos _headers_ HTTP entre os servidores e navegadores. É importante manter o tamanho dos cookies o menor possível para reduzir o impacto no tempo de carregamento para o usuário.

  _Como:_

  > ⁃ Elimine _cookies_ desnecessários.

  - 📖 [Especificação do Cookie: RFC 6265](https://tools.ietf.org/html/rfc6265)
  - 📖 [Cookies](https://developer.mozilla.org/en-US/docs/Web/HTTP/Cookies)
  - 🛠 [Limites de Cookies do Navegador](http://browsercookielimits.squawky.net/)
  - 📖 [Performance de Site: _Cookies_ não são tão gostosos - Monitis Blog](http://www.monitis.com/blog/website-performance-cookies-dont-taste-so-good/)
  - 📖 [Melhores Práticas de Performance Web do Google #3: Minimize Sobrecarga de Requisição - GlobalDots Blog](https://www.globaldots.com/googles-web-performance-best-practices-3-minimize-request-overhead/)

- [ ] **Minimize Requisições HTTP:** ![high] Sempre se certifique que todos os arquivos requisitados são essenciais para o seu site ou aplicação.

- [ ] **Use uma CDN Para entregar seus ativos:** ![medium] Use uma CDN para entregar mais rápido seu conteúdo pelo mundo.

* 📖 [10 Dicas para Otimizar Performance de CDN - CDN Planet](https://www.cdnplanet.com/blog/10-tips-optimize-cdn-performance/)
* 📖 [Cacheamento HTTP  |  Fundamentos Web  |  Google Developers](https://developers.google.com/web/fundamentals/performance/optimizing-content-efficiency/http-caching)

- [ ] **Entregue arquivos com o mesmo protocolo:** ![high] Evite entregar arquivos de fontes usando HTTP se seu site usar HTTPS.

- [ ] **Entregue arquivos existentes:** ![high] Evite solicitar arquivos que não podem ser acessados (404).

- [ ] **Defina corretamente os cabeçalhos de cache HTTP:** ![high] Defina cabeçalhos HTTP para evitar voltas custosas entre o seu navegador e o servidor.

- [ ] **Compressão GZIP está ativada:** ![high]

* 📖 [Verifique compressão GZIP](https://checkgzipcompression.com/)

**[⬆ Topo](#table-of-contents)**

---

## Frameworks JS e Performance

### Vue

### React

- 📖 [Otimizando Performance - React](https://reactjs.org/docs/optimizing-performance.html)
- 📖 [Manipulação de Imagens no React | Cloudinary](https://cloudinary.com/documentation/react_image_manipulation)
- 📖 [Debugando performance do React com React 16 e ferramentas de desenvolvedor do Chrome.](https://building.calibreapp.com/debugging-react-performance-with-react-16-and-chrome-devtools-c90698a522ad)

---

## Traduções

O Checklist de Performance Front-End também deseja estar disponível em outras línguas!

## Contribuir

**Abra um issue ou um PR para mandar sugestões, alterações ou inclusões.**

## Suporte

Se tiver qualquer dúvida ou sugestão, mande sua dúvida pelo Gitter or Twitter:

- [Chat no Gitter](https://gitter.im/Front-End-Checklist/Lobby?utm_source=share-link&utm_medium=link&utm_campaign=share-link)
- [Facebook](https://www.facebook.com/frontendchecklist/)
- [Twitter](https://twitter.com/thedaviddias)

## Author

**Criado com ❤️ por [David Dias](https://github.com/thedaviddias) em [@influitive](https://influitive.com/) 🇨🇦**

**Traduzido para português (brasil) por [Fernando Malaman](https://github.com/fernandofawkes)**

## Contribuintes

Esse projeto existe graças à todas as pessoas que contribuem. [[Contribua]](.github/CONTRIBUTING.md).

## Licensa de Uso

[MIT](LICENCE.md)

Todos os ícones fornecidos por [Icons8](https://icons8.com/)

**[⬆ Topo](#table-of-contents)**

[logo]: images/logo-front-end-performance-checklist.jpg
[html]: images/html.png
[css]: images/css.png
[fonts]: images/fonts.png
[images]: images/images.png
[javascript]: images/JavaScript.png
[server-side]: images/server-side.png
[low]: https://front-end-checklist.now.sh/low.svg
[medium]: https://front-end-checklist.now.sh/medium.svg
[high]: https://front-end-checklist.now.sh/high.svg
