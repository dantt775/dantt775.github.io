---
layout: post
title: "Upstream e Downstream em Microsserviços"
date: 2026-08-13 22:00:00 -0000
tags: offtopic
permalink: /upstream-downstream/
---

### Downstream e Upstream!

Essa semana estava analisando um log de erro pelo Grafana, era um erro HTTP de um microserviço, nossa aplicação faz várias chamadas para diversas APIs, uma dessa chamadas resultou em um erro 500, foi uma intermitência da aplicação, nada fora do normal, como estava sem paciência de ler o stacktrace linha a linha, pedi pro claude code cuspir alguma coisa, ele prontamente me devolveu que era um problema no Downstream e com isso o erro 500 interrompeu todo fluxo e o erro foi propagado para o upstream, até ai tudo bem, tirando o fato que eu não sabia precisamente o real significado de upstream e downstream, foi mais um dos casos onde a IA faz se sentir burro.


Prontamente adicionei esses termos pra eu estudar com mais carinho pra entender o que de fato eles significam, afinal, se você trabalha com agentes de IA e apenas aceita o que eles cospem e nao tira nada disso, você está se prejudicando e as vezes nem percebe.

Upstream e Downstream nada mais é do que um termo utilizado (não somente em microsserviços e TI) para identificar o caminho da informação (data flow direction) a partir de um determinado **ponto de vista**. Vamos analisar o diagrama abaixo:

![imagem com 4 aplicações que interagem entre si exibindo um fluxo de dados](/assets/images/downup-stream.png)

O primeiro passo é escolher um ponto de vista, vamos utilizar como exemplo a **payments-api**, digamos, observando a partir dela, podemos afirmar que o upstream é o client e o downstream seria **notifications-api**, podemos também afirmar que **email-api** é um downstream indireto, já que a **payments-api** não consome diretamente esse serviço. 

É uma maneira de fazermos referência a quem nos chama e a quem nós chamamos sem precisar ficar dando nome aos bois, um termo mais agnóstico.



[[voltar]](/posts)
