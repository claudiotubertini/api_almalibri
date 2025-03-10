# Le API di Almalibri

Applicazione per ricercare e scaricare records da terminale in formato `json` e `csv`, dalla banca dati [Almalibri](https://almalibri.it). L'accesso è riservato agli abbonati che al momento della sottoscrizione hanno comunicato il proprio indirizzo IP e alcuni campi facoltativi a cui sono interessati.  
&nbsp;
&nbsp;

## Installazione e utilizzo  

- Create un ambiente virtuale e installate almalibri_client, il client di Almalibri  

```bash
python3 -m venv your_virtual_env
python3 -m pip install almalibri-client
```

I requisiti sono `pandas`, `click` e `requests`.  In caso di errori nell'esecuzione del programma reinstallate le librerie con il comando  

```bash
pip install requests --upgrade
pip install click --upgrade
pip install pandas --upgrade
```  

- Il programma va lanciato da terminale con il comando `alma_api` seguito dal comando desiderato.  
I comandi disponibili sono:

- **unicod**   Genera l'elenco delle università disponibili, con l'anno accademico dell'ultimo aggiornamento. Non vi sono opzioni aggiuntive.  

- **fulltext**  Effettua una ricerca full-text di una query. Se la query consiste di più parole è necessario racchiuderla fra virgolette. Scarica i "programmi" di studio e le bibliografie così come pubblicate delle università selezionate. E' possibile specificare il nome del file (senza estensione); senza indicazione del nome del file verrà usata la data e l'ora del download. Le opzioni per selezionare le università sono le seguenti:

```bash
--uni_cod
--a_a [required]  
--query [required]  
```

- **programmi**  Scarica le bibliografie dei corsi di studio riportando anche il campo  ``insegnamento_id`` utile per il collegamento ai dati scaricati con il comando ``adozioni``. E' possibile specificare il nome del file (senza estensione); senza indicazione del nome del file verrà usata la data e l'ora del download. Le opzioni per selezionare i corsi sono le seguenti:

```bash
--uni_cod [required]  
--a_a [required]  
--laurea_nome  
--laurea_tipo  
--laurea_classe_cod  
--curr_nome  
--materia_nome  
--materia_ssd_cod  
--curr_materia_anno  
--curr_materia_periodo  
--insegnamento_prof  
--isbn  
--autori  
--titolo  
--editore  
--testo_obb  
--page
```

- **adozioni**  Scarica l'elenco delle adozioni delle università e dei corsi selezionati. E' possibile specificare il nome del file (senza estensione); senza indicazione del nome del file verrà usata la data e l'ora del download. Le opzioni per selezionare i corsi sono le seguenti:

```bash
--uni_cod  
--a_a [required]  
--laurea_nome  
--laurea_tipo  
--laurea_classe_cod  
--curr_nome  
--materia_nome  
--materia_ssd_cod  
--curr_materia_anno  
--curr_materia_periodo  
--insegnamento_prof  
--isbn  
--autori  
--titolo  
--editore  
--testo_obb  
--page
```  
