Pre-processing di un Dataset di Rilevazione del Tumore al Seno
Contesto del Progetto
Il settore sanitario si affida sempre di più ai dati per prendere decisioni informate, migliorare le diagnosi e ottimizzare i trattamenti. La corretta preparazione dei dati, soprattutto in un contesto delicato come quello della rilevazione del tumore al seno, è cruciale per garantire la qualità e l'accuratezza delle analisi successive. Questo progetto si concentra sul pre-processing di un dataset di rilevazione del tumore al seno, con l'obiettivo di creare un set di dati pulito e pronto per essere utilizzato nei modelli di machine learning.

Obiettivo del Progetto
Il valore aggiunto di questo progetto risiede nella creazione di un pipeline di pre-processing solida e ben strutturata, in grado di gestire i dati in modo coerente e automatizzato. Attraverso l'uso di strumenti come Pipeline e ColumnTransformer di scikit-learn, si punta a trasformare i dati grezzi in un formato che consenta di ottenere modelli predittivi più performanti e precisi.

L'obiettivo è ottenere un unico oggetto finale che racchiuda tutte le fasi di pre-processing, il cui metodo fit_transform sarà invocato per restituire il dataset trasformato e pronto all'uso. Le trasformazioni si applicano a tutte le colonne del dataset, eccetto la colonna target.

Valore Aggiunto
Automazione e scalabilità: La pipeline garantisce un processo automatizzato e facilmente replicabile su nuovi dati, riducendo i tempi di preparazione del dataset.
Ottimizzazione della qualità dei dati: Grazie alla pulizia e alla gestione delle variabili asimmetriche, la qualità dei dati sarà migliorata, portando a modelli più robusti.
Personalizzazione delle tecniche di pre-processing: La pipeline offre flessibilità nell'applicazione di tecniche di trasformazione avanzate come l'analisi della skewness, il PCA e la selezione delle variabili più informative.
Descrizione delle Pipeline
Il dataset è scaricabile da qui: https://proai-datasets.s3.eu-west-3.amazonaws.com/sample_dataset.csv

Pipeline 1: Pre-processing per Record con Target = 1
Questa pipeline si concentra sul pre-processing dei soli record in cui il target è pari a 1, ovvero i casi positivi di rilevazione del tumore. La pipeline include:

Pulizia dei Valori Mancanti: La pulizia sarà distinta tra variabili simmetriche e asimmetriche. Per le variabili asimmetriche si utilizzeranno tecniche di riempimento che tengano conto della distribuzione dei dati, mentre per quelle simmetriche si opterà per metodi di riempimento più standard.

Simmetrizzazione delle Variabili Asimmetriche: Per garantire una distribuzione più bilanciata dei dati, verranno corretti i valori delle variabili asimmetriche mediante tecniche di simmetrizzazione.

One-Hot Encoding delle Variabili Categoriche: Tutte le variabili categoriche saranno convertite in un formato numerico utilizzando il one-hot encoding, rendendo i dati utilizzabili nei modelli di machine learning.

Riscalatura mediante Standardizzazione: Le variabili numeriche saranno scalate usando la standardizzazione per garantire che tutte le variabili abbiano una distribuzione con media zero e deviazione standard pari a uno.

Questa pipeline fornirà un trattamento ottimale dei record positivi, migliorando la coerenza e la qualità dei dati su cui verranno effettuate le analisi.

Pipeline 2: Pre-processing per Tutti i Record del Dataset
Questa pipeline verrà applicata a tutti i record del dataset, con l'obiettivo di trasformare tutte le variabili numeriche e categoriche attraverso le seguenti fasi:

Pulizia dei Valori Mancanti: Sarà adottata una strategia personalizzata per riempire i valori mancanti in modo coerente con la natura delle variabili.

Discretizzazione a 20 Bin delle Variabili Numeriche: Le variabili numeriche verranno discretizzate in 20 bin per ridurre la complessità dei dati e facilitare l'analisi.

Encoding Ordinale delle Variabili Categoriche: La variabile categorica sarà codificata in base a un ordine crescente (A, B, C), mantenendo la semantica tra i valori.

Selezione delle 5 Variabili più Informative: Al termine delle trasformazioni, verranno selezionate le cinque variabili più informative rispetto al target, utilizzando una metrica appropriata, migliorando così l'efficienza e la precisione dei modelli successivi.

Pipeline 3: Pre-processing delle Variabili Numeriche
Questa pipeline si concentra esclusivamente sulle variabili numeriche, applicando tecniche avanzate di trasformazione:

Pulizia dei Valori Mancanti: Come nella pipeline precedente, verrà scelto un metodo di pulizia adeguato alle variabili numeriche.

Principal Component Analysis (PCA): Verrà applicata una PCA per ridurre la dimensionalità del dataset, mantenendo l'80% della varianza spiegata, il che permetterà di ridurre il rumore e migliorare le prestazioni dei modelli.

Simmetrizzazione: Come nella pipeline 1, anche qui si procederà con la simmetrizzazione delle variabili asimmetriche per migliorare la distribuzione.

Riscalatura mediante Normalizzazione: Infine, le variabili numeriche saranno normalizzate tra 0 e 1, per uniformare la scala e facilitare il processo di apprendimento dei modelli.

Risultato Finale
Al termine di tutte queste pipeline, verrà creato un oggetto finale che racchiude tutte le fasi di pre-processing. L'oggetto sarà esportato in modo da poter essere utilizzato direttamente in produzione dai team di data scientist e machine learning engineer. Questo approccio modulare e scalabile rappresenta un vantaggio chiave per la gestione di dataset complessi e l'addestramento di modelli robusti.

Conclusione
La pipeline di pre-processing proposta non solo migliora la qualità dei dati, ma ottimizza anche il flusso di lavoro aziendale, consentendo una maggiore efficienza operativa e una migliore affidabilità dei modelli predittivi. Attraverso la standardizzazione, la simmetrizzazione e l'uso del PCA, i dati saranno pronti per essere utilizzati nelle fasi successive di modellazione, fornendo un contributo significativo all'accuratezza delle previsioni sul tumore al seno.

Modalità di consegna:
Link pubblico a notebook di Google Colab
