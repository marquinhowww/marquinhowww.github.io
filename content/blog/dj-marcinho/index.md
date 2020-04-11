---
title: Como eu construi um BOT para mixagem de aúdios no telegram
date: "2020-04-07T17:43:39.910Z"
description: ffmpeg now.sh e nodejs
---

![mesa de audio](bg.jpg)

Esse bot é uma continução do meu [primeiro post](/telegram-bot/) primeiro POST onde mostro como criar um BOT e subir no now.sh.

Primeiramente peço perdão a todos DJs e produtores e que realmente mixam coisas, isso que vou mostrar uma brincadeira de final de semana entediado.

Eu sempre gostei muito de música mas infelizmente nunca aprendi tocar nada, e por não saber nada de música tábem nunca consegui trabalhar em produções. Esse experimento é uma forma de eu conseguir demonstrar meu amor por músic  a.

Eu não quero te ensinar a criar um bot de música (talvez sim), mas tomara que á partir disso você tenha novas ideias.

Antes que você desista do texto, porque já escrevi de mais, esse é resultado final:

`youtube:https://www.youtube.com/embed/f-t-iY14bSM`
[_Converse com o DJ Marcinho no telegram_](https://t.me/DjMarcinhoBot)

----------
## Ingredientes

### ffmpeg
Mixagem de áudio programaticamente é uma coisa muito interassante, para esse bot utilizei o [ffmpeg](https://www.ffmpeg.org/). Uma solução de linha de comando open source para manipulação de áudio.

### now.sh
Uma plataforma para funções serverless que tem limites gratuitos bem generosos para códigos **OPEN SOURCE**

### node.js
A mano, uma plataforma que usa o V8 da google para tu conseguir criar servidores que rodam javascript.

----------
## Fluxo

### **I** - Bot aguarda evento de áudio enviado
Geralmente eu adiciono esse bot em grupos, a brincadeira fica mais legal. Como já mencionado estou utilizando o [telegraf](https://github.com/telegraf/telegraf) que felizmente consegue fazer a filtragem de mensagens programaticamente e separar isso em eventos para facilitar nossa vida.
```js
bot.on(['voice', 'audio'], ctx => {
 // lógicas aqui pipipi popopo
})
```

No final acabei inventando umas modas aqui, mas o conceito base é esse.

### **II** - Envia menu com opções de áudio
![menu do bot quando um áudio chega](1menu.jpg)
O projeto tem uma pasta com os aúdios 

### **III** - Faz download do áudio enviado

### **IV** - Aciona o ffmpeg para fazer o mix do aúdio do usário com a faixa selecionada

