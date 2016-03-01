title: O que é AMP Project e Como Ele Pretende Melhorar a Web
thumbnail: gallery/amp-project.png
banner: gallery/amp-project.png
tags:
  - AMP Project
  - Performance
categories:
  - WPO
date: 2015-10-24 13:30:00
---

## Introdução

Estamos acostumados a utilizar smartphones na internet com conexão 3G e já esperar muito tempo até encontrarmos o que queremos. Isso porque geralmente os sites são feitos sem considerar as limitações envolvidas nos celulares.

Agora imagine a possibilidade de navegar na internet através do celular (MUITO!) mais rápido do que no seu computador! Isso será possível utilizando o Accelerated Mobile Pages Project - ou Projeto Páginas Móveis Aceleradas, na tradução literal.

## O que é AMP

O AMP Project é uma iniciativa de código aberto formada da união de grandes publishers e empresas de tecnologia a fim de facilitar o consumo de informação na atualidade, onde a mobilidade é regra.

Em seu artigo [Response Time: 3 Important Limits](https://www.nngroup.com/articles/response-times-3-important-limits/) (em inglês), Jakob Nielsen, o Guru de Usabilidade na Web, justifica a importância em manter o tempo de resposta no carregamento de páginas em menos de um segundo. Isso faz com que a experiência de navegação seja contínua e deixe de ser frustrante, como quando ficamos aguardando por muito tempo aquela página mostrar o que precisamos.

## Como funciona

O desenvolvimento das linguagens de programa web, navegadores e o aumento na velocidade da internet banda larga, unidos com a flexibilidade de HTML permitiram que o design de websites fosse levado ao extremo.

Agora são utilizando todos os recursos disponíveis, tornando-os muito bonitos porém demais complexos. Somado a isso, os curtos prazos de projetos tornam inviável a aplicação das melhores práticas de desenvolvimento, fazendo com que os websites fiquem ainda mais lentos.

Isso fez com que a experiência em dispositivos mobile, cenário desfavorável com menor processamento e velocidade de conexão, fosse prejudicada.

Sabendo da dificuldade de implantação de novas tecnologias de base da web, como os novos protocolos HTTP/2, SPDY, QUIC e outros, a grande sacada do APM Project é que, embora as tecnologias que utilizamos atualmente, como HTTP/1.1 e HTML, apresentarem algumas limitações, se forem bem programados proporcionam grande performance.

Para isso, eles propuseram uma *reprogramação* na forma como criamos websites, definindo uma [especificação](https://github.com/ampproject/amphtml/blob/master/spec/amp-html-format.md) do formato AMP HTML, que nada mais é do que o HTML que conhecemos, porém com diversas regras para manter boas práticas de performance.

Para facilitar esse processo, eles criaram alguns custom components como html tags, < amp-img>, < amp-anim>, e [muitas outras](https://github.com/ampproject/amphtml/blob/master/spec/amp-html-components.md). Para funcionar, é necessário adicionar o AMP Runtime em JavaScript que prepara tudo para nós.

Uma página com menos dinamismo, traz várias vantagens. A maior delas é a possibilidade das páginas serem geradas estaticamente, isto é, como o conteúdo delas não é dinâmico, o servidor não precisa processar a página toda vez que ela for carregada. Ao invés, ele a constrói apenas uma vez e quando for solicitada, apenas entrega o conteúdo pronto. Resposta extremamente mais rápida.

Isso também possibilita utilizar um grande recurso para performance, o cache, que pode ser otimizado para melhorar ainda mais a experiência.

A união dessas técnicas, ou boas práticas, proporciona uma navegação instantânea.

## Prática

Na prática, não dá para fazer milagre. Uma página AMP não pode ser como a maioria dos website são hoje, cheios de interatividade, muitas imagens e scripts. Mas isso não significa que são feios, como era em 1995.

De fato, atendem a necessidade dos envolvidos no projeto, a maioria, portais de conteúdo. O mais importante é o texto e não imagens e vídeos, embora ainda há espaço para conteúdo multimídia no AMP, só que não excessivamente.

Confira uma página exemplo (quase) rodando AMP em sua totalidade: [AMP Project How It Works](https://www.ampproject.org/how-it-works/)

Interessante o comentário no source dessa página:

```HTML
<!--
Welcome to AMP HTML ⚡.
Which isn't all that different from HTML. In fact, all AMP HTML files
are also HTML files. There isn't even a transpiler and they render
without further build process in all modern browsers.
How do you deploy an AMP HTML file to a web server:
Step 1: You copy it to the web server like every other HTML file.
Step 2: There is no step 2.

Visit us on Github https://github.com/ampproject/amphtml

PS: Technically this file is an invalid AMP HTML file. Load
https://www.ampproject.org/how-it-works/#development=1 to see the
validation error in the console. This is because some funky
pre-launch special casing of AMP files at Google that we will
fix super soon :)
-->
```

## Conclusão

O AMP Project é uma iniciativa para facilitar a adoção de das conhecidas boas práticas de desenvolvimento web, traçando regras para manter a web rápida o bastante para termos a melhor experiência de usuário possível em ambientes com alta latência de rede.

E tudo isso sobre a tecnologia de web que já utilizamos, como HTTP/1.1, possibilitando fácil aderência.

É fato que isso não se aplica a todos os tipos de websites, já que limita o que podemos utilizar no design. Mas isso demonstra que o ecossistema tende evoluir e nos forçar a abandonar as velhas práticas “mais fáceis”, buscando **tonar a web mais rápida.**

Agora resta saber se o mercado vai adotá-las.
