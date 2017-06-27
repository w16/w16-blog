---
title: Entendendo o Ransomware
excerpt: Você provavelmente já ouviu falar sobre Ransomware, certo? O vírus mais falado do momento tem causado a maior dor de cabeça aos administradores de sistemas, com casos recentes de ataques em grande escala como o WannaCry, para Windows, e o Erebus para Linux.
thumbnail: gallery/ransomware-post.jpg
banner: gallery/ransomware-post.jpg
categories:
  - Segurança
tags:
  - Malware
  - Ransomware
  - Vírus
  - WannaCry
  - Erebus
author: Diego Marques
date: 2017-06-26 11:06:00
---

## Introdução
Você provavelmente já ouviu falar sobre Ransomware, certo? O vírus mais falado do momento tem causado a maior dor de cabeça aos administradores de sistemas, com casos recentes de ataques em grande escala como o [WannaCry](https://www.tecmundo.com.br/malware/116652-wannacry-ransomware-o-mundo-chorar-sexta-feira-12.htm), para Windows, e o [Erebus](https://tecnoblog.net/217148/empresa-hospedagem-resgate-ransomware-linux/) para Linux. O ideia deste malware é sequestrar os dados do usuário de forma que o mesmo precise pagar um resgate para obte-los novamente, através de criptografia.

## Ah… Criptografia, sei…
Se você ouve falar bastante em criptografia mas não sabe exatamente como funciona, esta é a hora de entender um pouco melhor!
A criptografia é um processo que tem como intenção tornar uma mensagem (ou um dado) ilegível para aqueles aos quais o dado não é destinado, através de um processo envolvendo um segredo que irá “embaralhar” o dado original e que pode “reajeitar” o mesmo sabendo o segredo. Com base nisso, existem diversos esquemas de criptografia atualmente que auxiliam na segurança de dados sigilosos.
Na parte computacional, a maioria dos esquemas criptográficos utilizam-se de uma forte base matemática para se chegar ao resultado esperado, sendo que a premissa básica da criptografia computacional é de que o esquema tem que ser “forte” o suficiente ao ponto do poder de processamento computacional atual não conseguir testar todas as combinações possíveis para descobrir o segredo em tempo razoável.

## Uma faca de dois gumes
Como dito anteriormente, a criptografia é essencial na segurança dos dados na era da informação, e os esquemas mais utilizados hoje em dia garantem que os dados estarão seguros de olhos e ouvidos indesejados.
Mas assim como a criptografia pode ser utilizada para fazer o bem, ela pode ser utilizada de formas menos ortodoxas, como no caso do Ransomware. Certo dia, alguém teve o brilhante pensamento: “Se a criptografia hoje em dia é tão boa que não pode ser quebrada tão facilmente, então se eu criptografar os dados de alguém sem ele saber, os mesmos serão irrecuperáveis para ele, certo?”. Este pensamento é a base do funcionamento de um Ransomware, um ataque que depende completamente de um esquema criptográfico para cifrar os dados do usuário, onde o atacante retém o segredo, impossibilitando a recuperação por parte da vítima.

## Mas como funciona o resgate?
A partir do momento que o atacante retém o segredo, ele (em teoria) é o único que tem o poder de retornar os dados criptografados ao seu estado original, então basicamente o resgate se trata do atacante revelar para a vítima qual é o segredo. Além disso, normalmente os [resgates são pedidos utilizando Bitcoin](http://brasil.elpais.com/brasil/2017/05/12/economia/1494621106_047933.html), uma moeda que também é baseada em criptografia e que tem como uma das principais características uma certa [taxa de anonimato](https://foxbit.com.br/blog/o-bitcoin-e-realmente-anonimo-descubra-se-moeda-e-segura/) e [dificuldade de rastreamento de transações](https://bitcoin.org/pt_BR/proteger-sua-privacidade), tornando o processo de identificação do criminoso uma tarefa extremamente árdua.

## E a solução?
Não existe uma solução geral ao problema dos Ransomwares nos dias de hoje, pois se pararmos para analisar a situação, se fosse possível resolver o problema dos Ransomwares de forma genérica, estaríamos automaticamente “quebrando” toda a segurança baseada em criptografia dos tempos modernos junto!
O que existem são soluções para tipos específicos do vírus, que dependem na maioria das vezes de uma falha de implementação de software do malware. Um bom exemplo disto é a própria [solução para o WannaCry](https://www.showmetech.com.br/ferramenta-descriptografa-arquivos-bloqueados-ransomware/), onde os números primos geradores da chave criptográfica (este conceito fica para um próximo artigo) persistiam em memória após a execução do malware, trazendo a possibilidade de se recuperar a chave e assim decifrar os dados.

## Como se previnir?
A maioria dos ataques em geral necessitam de um ponto de falha no seu sistema, que podem variar desde uma versão desatualizada de um software que é conhecido por ter vulnerabilidades naquela versão, a um ataque de engenharia social, onde o criminoso induz a vítima a “deixá-lo entrar” em seu sistema. Para evitar que este tipo de situação ocorra, é necessário tomar algumas medidas de segurança como definir uma política de senhas, manter os softwares atualizados, definir perímetros de confiança na rede, entre outras. Em breve teremos um artigo sobre este tema!