---
layout: post
title:  "Pseudo-código da estrada"
author: cesarcaldeira
categories: [ Inteligência Artificial , Política ]
image: assets/images/posts/surveillance.jpg
tags: [recomendados]
edicao: jul21
---

Quando o então campeão mundial de xadrez Gary Kasparov viu 19.c4[^1] no sexto e último jogo da sua segunda partida com o programa Deep Blue em 1997, soube que não tinha como escapar à derrota e renunciou [^2]. Foi a primeira vez que um campeão do mundo perdeu uma partida com regras de torneio contra um computador, e com esta derrota o mundo do xadrez nunca mais seria dominado por um humano. Em 2016 foi a vez do jogo oriental Go, onde a inteligência artificial AlphaGo (da Google) derrotou o campeão mundial Lee Sedol[^3], e já em 2007 se tinha solucionado o jogo das damas em tabuleiros de oito por oito casas[^4].

[^1]: Peão avança para a casa c4.
[^2]: Deixo aqui a anotação do jogo, para os curiosos: 1.e4 c6 2.d4 d5 3.Nc3 dxe4 4.Nxe4 Nd7 5.Ng5 Ngf6 6.Bd3 e6 7.N1f3 h6 8.Nxe6 Qe7 9.0-0 fxe6 10.Bg6+ Kd8 11.Bf4 b5 12.a4 Bb7 13.Re1 Nd5 14.Bg3 Kc8 15.axb5 cxb5 16.Qd3 Bc6 17.Bf5 exf5 18.Rxe7 Bxe7 19.c4.
[^3]: Recomendo vivamente verem o [documentário](https://www.imdb.com/title/tt6700846/) sobre este jogo.
[^4]: Note-se que nem o xadrez nem o go são jogos solucionados. Aqui quem sai a ganhar não é uma inteligência artificial, mas sim uma base de dados com todas as jogadas possíveis, resultado de centenas de computadores a calcularem as mesmas ao longo de 18 anos.

Ainda hoje nos é difícil admitir, mas cada vez mais os algoritimos de inteligência artificial são capazes de realizar as tarefas que antes só um ser humano conseguia fazer, sejam estas jogar um jogo de xadrez, conduzir um carro de forma segura ou até mesmo detetar tumores através da análise de imagens. A inteligência artificial veio para ficar na nossa sociedade e o benefício da sua aplicação em diversos serviços é óbvio. **Não obstante, levantam-se questões de ética quando tentamos aplicar estes algoritmos a situações com consequências imediatas à segurança e liberdade de um indivíduo**, e tenciono focar esta análise na sua aplicação a mecanismos legais e de governação onde, apesar das consequências não serem tão cinematicamente interessantes (muito embora um Marcelo Rebelo de Sousa ou António Costa robóticos a exercer os seus cargos seja uma premissa interessante para um _blockbuster_ de verão), o risco para a sociedade em geral e para os princípios democráticos sob os quais vivemos é enorme.

* * *

![Carros da Waymo](https://lh3.googleusercontent.com/DUdYmKSnbnZmkdLyzlJJcUVf-rDn5hVOsVvAAkwhoYBJaoH9ZlXmdCGNZWxGvzpLOJyus1QPjV7YLSnd_p8uHmTPW3dmu7lDTNp9=rw-w1024-e365)

**Na imagem...** _Waymo, o carro que se conduz a si próprio, com a sua origem no projeto de carro autónomo da Google em 2009._

* * *

Há cerca de um ano fiz um curto ensaio para uma cadeira introdutória de licenciatura focada em _PPE_ (_politics, philosophy and economics_) onde analisei um artigo de Matthew Crawford no _American Affairs Journal_ sobre governança algorítimica e legitimidade política[^5] . Crawford aponta-nos imediatamente para o que considera ser o cerne da questão: a nossa prontidão a aceitar as decisões procedimentais tomadas por um algoritmo que não deve justificação a ninguém (e mesmo que deva, as suas lógicas decisórias dificilmente podem ser explicáveis). Devo admitir que não deixo de ter as minhas simpatias pela implementação de algoritmos em algumas circunstâncias. Continuo um otimista quanto à tecnologia da inteligência artificial, mas notícias como [o escândalo das acusações erróneas de fraude fiscal nos Países Baixos devido a decisões automatizadas](https://www.politico.eu/article/dutch-lodewijk-asscher-labor-leader-tax-office-scandal/), [o algoritmo de recrutamento enviesado contra mulheres da Amazon](https://www.reuters.com/article/us-amazon-com-jobs-automation-insight-idUSKCN1MK08G) ou [o algoritmo da mesma empresa que justifica o despedimento de empregados com métricas de produtividade automatizadas](https://www.theverge.com/2019/4/25/18516004/amazon-warehouse-fulfillment-centers-productivity-firing-terminations) preocupam-me o suficiente para ainda estar de pé atrás na sua implementação.

[^5]: [Matthew Crawford, 2019. _Algorithmic Governance and Political Legitimacy_, American Affairs Journal.](https://americanaffairsjournal.org/2019/05/algorithmic-governance-and-political-legitimacy/)

# Radares e decisões

É natural e saudável, nas democracias liberais, uma certa suspeita face às autoridades. Esta suspeita é a base do nosso sistema político de **freios e contrapesos**, onde as figuras de autoridade (sejam estas políticas ou comerciais) são alvo de escrutínio constante por mecanismos que se regem por lógica. A estes mecanismos chamamos de leis. Veja-se o seguinte: se um indivíduo ultrapassa os 120 quilómetros por hora na autoestrada está a infringir uma regra à qual toda a sociedade consentiu por via das suas leis devidamente escrutinadas. A lógica, em pseudo-código[^6], ficaria algo do género:

`SE (velocidade > 120km/h) ENTÃO (60€ <= multa <= 2.500€)`

[^6]: Linguagem de cromos de informática quando querem descrever um algoritmo sem ir em grande detalhe.

Um algoritmo como estes assemelha-se ao processo de decisão para aplicar uma coima a um condutor que ultrapasse o limite de velocidade na autoestrada, mas faltam aqui detalhes fundamentais que convém esclarecer: se alguém é multado em Portugal por exceder o limite de velocidade (tendo o facto sido observado por um radar de velocidade automatizado) não é multado pelo algoritmo do radar mas sim pelo pessoal competente da Autoridade Nacional da Segurança Rodoviária que levanta os factos adquiridos pelo radar[^7].

[^7]: [Artigo 169º do Código da Estrada](http://www.ansr.pt/Legislacao/CodigoDaEstrada/Documentos/Republica%C3%A7%C3%A3o%20do%20C%C3%B3digo%20da%20Estrada.pdf).

> O pessoal da ANSR é equiparado a autoridade pública, competindo-lhe (...) o levantamento e notificação de auto de contraordenação cujos factos constitutivos sejam conhecidos através de meios telemáticos de fiscalização automática.

Como Crawford nos diz, **a automatização da tomada de decisões assemelha-se ao sistema de freios e contrapesos liberal**, mas estes não são equivalentes. Certamente parece-nos mais justo deixar ao critério de uma máquina a decisão de nos multar ou não quando a alternativa é um agente da GNR que não dá com a nossa cara. Este agente pode ter um viés contra nós e até abusar do seu poder[^8], portanto uma câmara automática que tome a decisão de nos multar será mais justa, certo? Bem, o problema aqui é duplo. Com este radar com poder de decisão quem é que é o responsável pela decisão? A quem é que podemos apelar para analisar a decisão do mesmo? Será o programador por detrás do algoritmo de inteligência artificial que vai tentar explicar que o sistema agiu desta forma porque "aprendeu" a analisar imagens de pessoas que cumprem e pessoas que não cumprem o Código da Estrada? Note-se que esta noção de aprendizagem nada se assemelha a uma análise rigorosa dos factos *à la humain*, mas sim a um "palpite" resultante da análise de milhares de casos e que pode desenvolver um viés, por exemplo, contra carros vermelhos ou descapotáveis se a sua fonte de exemplos tem os mesmos a cometer infrações desproporcionalmente. As pessoas podem justificar o seu raciocínio, uma inteligência artificial não. O agente que abuse da sua autoridade pode ser fiscalizado (se tal acontece é outra questão), o algoritmo não.

[^8]: Para deixar claro, nesta época de mal-entendidos, tanto podia estar a falar de um agente da GNR como de uma qualquer figura de autoridade com poder para aplicar uma coima.

# O que podemos fazer

Há algo de fundamentalmente errado na noção libertária de que toda a autoridade é má. Mesmo concordando que o aparelho de Estado deve ser mínimo para garantir que o mesmo não interfira excessivamente na vida dos indivíduos, que tipo de liberdade é que podemos esperar de um sistema onde a autoridade é exercida de forma algorítmica por mecanismos que não são fiscalizáveis? É fácil ceder à tentação bem-intencionada de limitar as fontes de autoridade, mas a solução mais liberal a tomar nesta circunstância é, irónicamente, introduzir maiores regulações que fiscalizem a aplicação de algoritmos a tomadas de decisões por autoridades. A democracia liberal não se refere apenas ao sistema político, mas também ao sistema económico: existem leis de concorrência, leis de contratos, leis referentes ao despedimento entre muitas mais que regem a forma de como uma entidade comercial pode agir, visto que os nossos direitos fundamentais também podem ser quebrados pelas mesmas.

A defesa dos direitos humanos no contexto digital encontra-se ainda num estado embrionário, mas é cada vez mais o foco de atenção por parte das entidades reguladoras e de grupos de interesse. Uma consequência interessante da competição sino-americana dos últimos anos tem sido exatamente a exposição que as práticas de privacidade e de aplicação de inteligência informática em vigilância por parte das autoridades chinesas têm adquirido. Também neste sentido, as práticas de grandes companhias de _Silicon Valley_ têm sido cada vez mais fiscalizadas (ou pelo menos têm mais atenção mediática), e os vários órgãos de governação públicos e privados pelo mundo liberal-democrata finalmente estão a investir recursos na criação de códigos deontológicos adequados aos problemas éticos que têm vindo a surgir nos domínios digitais. Resta-nos saber, no entanto, se o resultado final desta discussão a nível global é capaz de gerar consenso quanto aos limites a aplicar às tecnologias que tanto podem ajudar o Homem na sua procura pela liberdade como o podem amordaçar sistematicamente por detrás de um manto de procedimentos pseudo-liberais, construídos para o benefício das autoridades responsáveis pela sua manutenção quando não são devidamente fiscalizadas.

# Recomendações de leitura e vídeos

Para terminar, deixo aqui uma curta lista de leituras e vídeos interessantes sobre os direitos digitais, inteligência artificial entre outras "cromices":

1. [How Machines Learn, CGP Grey](https://www.youtube.com/watch?v=R9OHn5ZF4Uo)
2. [Vexed: Ethics Beyond Political Tribes, James Mumford](https://www.goodreads.com/book/show/52206583-vexed)
3. [Should Computers Run the World? - with Hannah Fry](https://www.youtube.com/watch?v=Rzhpf1Ai7Z4)
4. [AlphaZero: DeepMind's AI Works Smarter, not Harder](https://www.youtube.com/watch?v=1gWpFuQlBsg)
5. [Here's why we need a Declaration of Global Digital Human Rights, World Economic Forum](https://www.weforum.org/agenda/2020/08/here-s-why-we-need-a-declaration-of-global-digital-human-rights/)
