---
title: "Análise de Sentimentos Sobre o Joe Biden (46º Presidente Eleito dos EUA) no Twitter - Linguagem R"
date: 2020-11-08
tags: [análise de sentimentos, data science, twitter, linguagem R]
header:
  image: "/images/post1.png"
excerpt: "Análise de Sentimentos, Twitter, Linguagem R"
mathjax: "true"
---

Esse post foi originalmente publicado por mim no LinkedIn [aqui](https://www.linkedin.com/pulse/an%C3%A1lise-de-sentimentos-sobre-o-joe-biden-46%C2%BA-eleito-dos-jos%C3%A9-carlos/).

Olá pessoal, tudo bem com vocês?

É a minha primeira vez aqui, espero que gostem! (e me deem um feedback, please).

Para minha estreia, vou trazer para vocês uma modelo de machine learning bem simples que escrevi para fazer uma análise de sentimentos. O alvo será o novo presidente eleito dos Estados Unidos. Será o que as pessoas acham dele?

Para isso, utilizei linguagem R com o RStudio e a rede social que vou utilizar para extrair os dados é o Twitter. Posteriormente irei fazer um outro com linguagem Python e coloco o link aqui.

Não vou floodar o artigo aqui com muito código, vou dar ênfase apenas nos pontos que eu considero chave para a análise.

Vamos começar importando as bibliotecas que vou utilizar no decorrer do script.

```r
library(twitteR)
library(httr)
library(SnowballC)
library(tm)
library(RColorBrewer)
library(wordcloud)
library(Rstem)
library(sentiment)
library(ggplot2)
```

Primeiro passo que temos que fazer é a autenticação com a API do Twitter, para obter esse acesso, é preciso ter uma conta no Twitter (é claro!), e responder um MONTE de perguntas, tais como: onde você trabalha, o que vai fazer com os dados extraídos, se você trabalha pro governo, etc, etc, etc. O link para você se cadastrar também é: [link](https://developer.twitter.com/en).

Tendo seu cadastro aprovado (pode levar dias até a aprovação), acessando a sua página de desenvolvedor, você vai encontrar chave e token para acesso. E então, fazemos a autenticação.

```r
setup_twitter_oauth(key, secret, token, tokensecret)
```
Bom, autenticação feita, vamos coletar alguns tweets.

Foi utilizado como palavra-chave "Biden" (remetendo a Joe Biden) e 10k tweets. Aqui, é importante destacar que, o tamanho da amostra utilizada é fundamental para qualidade final da análise, quanto maior, mais preciso.

```r
tweets = searchTwitter('Biden', n = 10000, lang = 'en')
```

...

Bacana! Alguns segundos esperando, agora temos uma massa de tweets para analisar... buuut, temos alguns trabalhos de limpeza para serem feitos antes, ou você acha que o algoritmo vai entender tudo?

Feito tudo isso, vamos gerar uma wordcloud (palavras mais comum na massa de dados).

```r
paleta = brewer.pal(8, "Dark2")
wordcloud(tweet_cor, min.freq = 2, random.color = F, max.word = 100, random.order = F, colors = paleta, scale = c(5,1))
```

COLOCAR IMAGEM

Agora vamos plotar um dendograma, que nos mostra como os agrupamentos de algumas palavras são formadas dentro da nossa massa de tweets.

```r
tweetsMtx = TermDocumentMatrix(tweets2)
tweet_den2 = removeSparseTerms(tweetsMtx, sparse = 0.9)
tweetscale = scale(tweet_den2 )
tweetdist = dist(tweetscale , method = "euclidean")
plot(hclust(tweetdist))
```

COLOCAR IMAGEM

Agora vamos para a parte mais legal, que é de fato construir nossa análise em cima dos dados. Então, aqui nessa etapa, vamos submeter nossos tweets ao classificador de emoções que foi treinado com o algoritmo de machine learning naive Bayes.

Esse classificador pode indicar sentimentos como: raiva, desgosto, medo, alegria, tristeza e surpresa.

Basta chamar a função "classify_emotion" que o algoritmo faz o resto.

Além disso, podemos classificar a polaridade do tweet, ou seja, se é positivo, negativo ou neutro. Para isso, basta chamar outra função (classify_polarity).

Capturando os sentimentos que queríamos, unifiquei todos os resultados em um dataframe.

```r
# classificador de emoção:
class_tweets = classify_emotion(tweets, algorithm = "bayes", prior = 1.0)
twt_emotions = class_tweets[,7]

# classificador de polaridade:
class_tweets_pol = classify_polarity(tweets, algorithm = "bayes")
twt_pol = class_tweets_pol[,4]

```

Sim, é isso mesmo, está pronto!

Agora vamos ver os gráficos que conseguimos com os resultados da análise.

O primeiro gráfico remete a classificação de emoções e o segundo é o classificador de polaridade.


COLOCAR IMAGENS

### Conclusões

Bom, com base nos gráficos, a gente pode ver que há mais pessoas aprovando o presidente eleito Biden do que desaprovando-o, com ênfase no sentimento de alegria (joy) no primeiro gráfico.

Apesar de simples, vocês conseguem ver o poder que essas análises podem nos trazer? Quanto você pagaria para saber o que as pessoas estão falando sobre a sua marca? Sobre o seu serviço? Sobre o seu produto?

Basicamente, estamos limitados apenas a criatividade para as perguntas a serem feitas, porque ferramentas para respondê-las nós temos.



P.S: como dito no início do texto, farei futuramente uma análise mais elaborada utilizando pyhton, e trago aqui pro LinkedIn.
