## Media di oggi

Fratelli d'Italia: 30.00%  
Partito Democratico: 23.66%  
Movimento 5 Stelle: 11.15%  
Forza Italia: 9.53%  
Lega: 8.62%  
Alleanza Verdi Sinistra: 6.53%  
Azione: 3.21%  
Altri: 3.07%  
Italia Viva: 2.46%  
+Europa: 1.79%  
## Grafico
![Latest Moving Average](latest_average_plot.png)

# Archiving Italian Political Polls

Questo progetto si occupa di archiviare tutti i sondaggi mai caricati sul sito ufficiale [sondaggipoliticoelettorali.it](https://www.sondaggipoliticoelettorali.it/), cercando quelli che riguardano l'intenzione di voto nazionale utilizzando il confronto di stringhe e l'estrazione delle risposte al sondaggio utilizzando un Large Language Model (LLM).
Per a chi interessano solo i dati dei sondaggi aggiornati giornalieramente, sono disponibili in formato JSONL nel file `italian_polls.jsonl` e in formato CSV nel file `italian_polls.csv`.

## Requisiti

Avere un'installazione di Python con un setup di Selenium funzionante e le librerie `openai` e `bs4` installate.
Avere nel proprio environment la variabile d'ambiente `OPENAI_API_KEY` settata con la propria chiave API di OpenAI.
Per esserne sicuri, basta installare i requisiti con il seguente comando:

```shell
pip install -r requirements.txt
```


## Installazione

1. Clona il repository sul tuo computer:

```shell
git clone https://github.com/ruggsea/llm_italian_poll_scraper.git
```

2. Entra nella directory del progetto:

```shell
cd llm_italian_poll_scraper
```

## Utilizzo

I sondaggi dovrebbero essere archiviati nel file `italian_polls.jsonl` in formato JSONL. Per aggiornare il file con i nuovi sondaggi, esegui il seguente comando:

```shell
python3 llm_poll_parser/archiving_polls.py
```


## Note

La media si basa sui sondaggi archiviati nel file `italian_polls.jsonl` e viene calcolata tramite media mobile a peso esponenziale (EWMA). Il grafico non riporta Azione, +Europa e Italia Viva poiché le loro unioni e divisioni rendono difficile rappresentarne una serie storica (sono tuttavia presenti nei dati raccolti).

## Partiti considerati

Sono considerati in maniera abbastanza esaustiva tutti i partiti sondati nei sondaggi archiviati sul sito (2013-presente). I partiti considerati sono:

- Fratelli d'Italia
- Partito Democratico
- Movimento 5 Stelle
- Forza Italia
- Lega
- Alleanza Verdi Sinistra
- Azione
- Italia Viva
- +Europa
- Pace Terra Dignità
- Sud Chiama Nord
- Stati Uniti d'Europa
- Azione/+Europa
- Azione - Italia Viva
- Unione Popolare
- Sinistra Ecologia Libertà
- Unione di Centro
- Scelta Civica

Sono incoraggiati consigli e suggerimenti su partiti da aggiungere, altri miglioramenti e correzione dei dati: in caso aprire una issue. Grazie!

Per domande, chiarificazione o contatti media contattemi su fu twitter at [ruggsea](https://twitter.com/ruggsea) o al seguente profilo [LinkedIn](https://www.linkedin.com/in/ruggsea/).