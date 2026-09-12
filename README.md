# RaiPlay Sound Feed

Questo repository genera dei feed RSS per i programmi di RaiPlay Sound, e sono generati automaticamente tramite GitHub Actions e GitHub Pages. In modo da potersi abbonare/ascoltare su qualsiasi client podcast  e non esclusivamente tramite l’app RaiPlaySound. 


## Podcast

| Programma | Feed RSS |
|----------|----------|
| Radio3 Scienza | https://mariovernetti.github.io/raiplaysound-feed/rss/programmi/radio3scienza.xml |

## Audiolibri

| Audiolibro | Feed RSS |
|------------|----------|
| Canne al vento | https://mariovernetti.github.io/raiplaysound-feed/rss/audiolibri/cannealvento.xml |
| Da Quarto al Volturno | https://mariovernetti.github.io/raiplaysound-feed/rss/audiolibri/daquartoalvolturno.xml |
| I ragazzi della via Pal | https://mariovernetti.github.io/raiplaysound-feed/rss/audiolibri/iragazzidellaviapal.xml |
| Il Cappello del Prete | https://mariovernetti.github.io/raiplaysound-feed/rss/audiolibri/ilcappellodelprete.xml |
| Il sentiero dei nidi di ragno | https://mariovernetti.github.io/raiplaysound-feed/rss/audiolibri/ilsentierodeinididiragno.xml |
| La Linea Dombra | https://mariovernetti.github.io/raiplaysound-feed/rss/audiolibri/lalineadombra.xml |
| latigredimompracen | https://mariovernetti.github.io/raiplaysound-feed/rss/audiolibri/latigredimompracen.xml |
| Ledera | https://mariovernetti.github.io/raiplaysound-feed/rss/audiolibri/ledera.xml |
| Sorelle Materassi | https://mariovernetti.github.io/raiplaysound-feed/rss/audiolibri/sorellematerassi.xml |

## Abbonarsi o aggiungere un feed

Per abbonarsi basta copiare l'URL del feed dalla tabella nel lettore podcast.

Per aggiungere programmi o audiolibri puoi forkare il repository e aggiungere manualmente i feed, oppure aprire una Pull Request modificando [static.ts](https://github.com/giuliomagnifico/raiplaysound-feed/blob/main/src/static.ts), esempio:

```ts
{
  title: 'Radio3 Scienza',
  path: 'programmi/radio3scienza'
}
```

oppure per un audiolibro:

```ts
{
  title: 'Arancia meccanica',
  path: 'audiolibri/aranciameccanica'
}
```

> [!NOTE]
> la tabella con i feeds o audiolibri nuovi si aggiorna  automaticamente con il nuovo feed (in ordine alfabetico) quando viene eseguita la Action, non aggiungere o modificare manualmente la tabella.

## Aggiornamento ogni ora

I feed vengono aggiornati automaticamente tramite GitHub Actions ogni ora e viene controllata la validità degli URL vecchi ogni 14 giorni.

## INFO

Questo progetto è una evoluzione di un mio [precedente repository](https://github.com/giuliomagnifico/raiplay-feed),  il quale aveva il problema di non risolvere correttamente la redirect ed era quindi necessario scaricare il file prima di riprodurlo certi podcast. Adesso gli URLs vengono risolti fino alla CDN finale Rai, evitando i problemi causati dai redirect `relinkerServlet.htm` con alcuni client podcast (i.e. [PocketCasts](https://pocketcasts.com/)).


> [!TIP]
> È una versione modificata del repository [frammenti/raiplaysoundrss](https://github.com/frammenti/raiplaysoundrss) costruita per poter funzionare usando solo su GitHub, in modo da essere indipendente da un server esterno. 

