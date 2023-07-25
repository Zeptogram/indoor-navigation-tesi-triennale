# Tesi Triennale Scienze Informatiche
> Un’app a supporto della navigazione indoor nel campus UniMiB

[![Download Tesi PDF](https://img.shields.io/badge/Download%20Tesi-PDF-lime.svg)](https://github.com/Zeptogram/indoor-navigation-tesi-triennale/releases/download/tesi_presentazione/Tesi_LT_28Luglio2023.pdf)
[![Download Presentazione PDF](https://img.shields.io/badge/Download%20Presentazione-PDF-orange.svg)](https://github.com/Zeptogram/indoor-navigation-tesi-triennale/releases/download/tesi_presentazione/Presentazione_LT_24Luglio2023.pdf)
[![Tesi su Overleaf](https://img.shields.io/badge/Tesi-Overleaf-green.svg)](https://www.overleaf.com/read/tgvnszsrwjdt)

# Autore e Ulteriori Informazioni

- **Autore**: Elio Gargiulo
- **Università**: Università degli studi Bicocca, Milano, Scienze Informatiche
- **Anno Accademico**: 2022/23

# Stage

- **Titolo stage**:  App personalizzata di navigazione indoor per l'Ateneo 
- **Obiettivi formativi e competenze da acquisire:** Programmazione di dispositivi mobili 
- **Descrizione stage**: Lo stage ha come obiettivo la realizzazione di una app multipiattaforma che permetta la navigazione indoor in Ateneo. La navigazione deve tener conto dello stato del contesto (corridoi affollati, ascensori fuori servizio, etc.) e delle caratteristiche dell'utente (disabilità, preferenze, etc.). <br>
Lo stage prevede innanzitutto un'indagine relativa a come graficamente le piante debbano essere presentate all'utente e come queste possano descrivere il contesto (dell'ambiente e personale). Quindi poi verrà richiesta l'implementazione di un prototipo che copra anche un solo edificio. <br>
L'utente, infine, attraverso l'app, potrà contribuire a mantenere lo stato del contesto ambientale aggiornato. Ad esempio, potrà segnalare che una scala mobile è fuori servizio, oppure che un corridoio è affollato. L'applicazione dovrà mostrare l'interno di ogni edificio in 2D o 3D. Ogni mappa avrà come base un grafo con nodi ed archi e si baserà sull'algoritmo di Dijkstra per la navigazione e tenendo conto di preferenze (interne) e segnalazioni (esterne). La mappa deve essere in formato facilmente fruibile dall'utente e salvata in un formato che consente la modellazione dinamica (ex. XML, SVG o JSON).

## Indice dei contenuti
- [Ulteriori Informazioni sulla Proposta](#Ulteriori-Informazioni-sulla-Proposta)
- [ToDo List](#ToDo-List)
- [Studenti](#Studenti)
- [Riferimenti Stage](#Riferimenti-Stage)
- [Riferimenti Progetto](#Riferimenti-Progetto)
- [Approfondimento su Navigine](#Approfondimento-su-Navigine)
- [Piantine U14](#Piantine-U14)
- [Test su Beacon Estimote](#Test-su-Beacon-Estimote)
- [Applicazione Demo](#Applicazione-Demo)
- [FAQ](#FAQ)

## Ulteriori Informazioni sulla Proposta

Sviluppare un’app che funzioni per l’indoor che individua il percorso per aula o ristorazioni. Garantire Accesso anche per disabilità.

- **Generale**: Progetto su Navigazione indoor 
- **Funzionalità Principali**: Percorso su mappa e come ti sposti rispetto al percorso, Evidenziare una determinata area sulla mappa.
- **Funzionalità Aggiungive**: Ti dice dove sei rispetto al percorso, Funzionamento simil navigatore (ex. ricalcolo se sbaglio strada)
- **Cose da considerare:** Il GPS non funziona, si consiglia l'utilizzo di QR Code o beacon per la localizzione dell'utente
- **Informarsi su**: Come vengono visualizzate le mappe e i percorsi.
- **Cercare**: App su Apple o Google Play simili alla richiesta.

## Obiettivi

- Ricerca di validi servizi per Mapping e Navigation.
- Analisi sulla rappresentazione dei dati.
- Analisi sull'implementazione dei dati.
- Progettare la soluzione finale (mockup).
- Creare un'applicazione di testing su un edificio.

## Studenti

Lo stage è stato svolto da:
- Gargiulo Elio
- Biancini Mattia
  
## Riferimenti Stage
- **Tutor Universitario**: Prof. Micucci _<daniela.micucci@unimib.it>_
- **Tutor Aziendale**: Prof. Ginelli _<davide.ginelli@unimib.it>_

## Riferimenti Progetto

### Riferimenti Principali

| Nome API | Linguaggi Supportati | Piattaforme Supportate | Costi | Tecnologie di Navigazione | Ulteriori Informazioni |
| ------------ | ------------ | ------------ | ------------ | ------------ | ------------ |
| [MapsPeople](https://www.mapspeople.com/) | Java, Kotlin, Swift | Android, iOS | A pagamento | Beacon, WiFi, Ultra suoni, Posizionamento Geomagnetico, LED based positioning, [più info](https://blog.mapspeople.com/mapsindoors/indoor-positioning-101)| Richiede una mail per la demo. Si puó visionare la demo sia per Android (Key Demo = d876ff0e60bb430b8fabb145) che iOS. Richiede versione minima di android SDK 21 (Android 5.0) e l'utilizzo di Java 8 ([Maggiori Info](https://docs.mapsindoors.com/getting-started/android/v4/new-project)). Non consentono lo sviluppo a fini accademici. |
| [Navigine](https://github.com/Navigine) | Java, Kotlin, Swift, Dart | Android, iOS, Flutter | Free | [iBeacon](https://developer.apple.com/ibeacon/), WiFi, [WiFi RTT](https://developer.android.com/guide/topics/connectivity/wifi-rtt), Gateway/Locator, [Eddystone](https://www.mokoblue.com/all-about-eddystone-beacon/), [BLE Beacons](https://en.wikipedia.org/wiki/Bluetooth_Low_Energy_beacon) | La scelta più valida al momento, [approfondimento](https://gitlab.com/unimib-wayfinding/indoor-navigation-biancini-gargiulo#Approfondimento-su-Navigine). |
| [Steerpath](https://www.steerpath.com/products/maps-indoor-navigation) | Java, Objective-C, Swift | Android, iOS, Web | Piano base 690$/mese | Beacon | Consente la visualizzazione anche in 3D. |
| [MazeMap](https://api.mazemap.com/js/v2.0.94/docs/#intro) | JavaScript | React | Free per l'utilizzo dell'API. <br>A pagamento per la realizzazione e integrazione della mappa | Beacon e [altro](https://www.mazemap.com/solutions/indoor-positioning) | API ben realizzata, ma sembra necessitare di una [mappa](https://www.mazemap.com/about-us/faqs) realizzata dall'azienda per essere utilizzata. |
| [Situm](https://situm.com/en/desarrollo-mobile-sdk/) | Java, Objective-C, Dart | Android, iOS, Flutter | 30 days free | WiFi, BLE Beacons, Ultra-Broadband | Molto simile a Navigine, ottima compatibilità ma oltre i 30 giorni necessita di un pagamento. |
| [IndoorAtlas](https://www.indooratlas.com/platform/) | JavaScript, Objective-C, Swift, Java | Android, iOS, React | 60 days free | WiFi, BLE Beacons, Posizionamento Geomagnetico, Inerzia, VIO (Realtà Aumentata), Posizionamento Barometrico  |Anche lui simile a Navigine, molto valido, ma vi è un limite di una location e 60 giorni di prova. |

### Altri Riferimenti
#### OpenStreetMap
- [Open Street Map](https://www.openstreetmap.org/#map=6/42.088/12.564) <br>
*Non consente la visualizzazione dell'interno dell'edificio. Ottimo per avere una pianta generale di piú edifici e informazioni riguardo ad un edificio nel suo complesso.*
- [Simple Indoor Tagging](https://wiki.openstreetmap.org/wiki/Simple_Indoor_Tagging) <br> 
*Sistema di mapping indoor che si appoggia su OpenStreetMap*
- [OpenInDoor](https://github.com/open-indoor/openindoor6) <br>
*Da considerare come ispirazione, é una Web App*
- [Indoor=](https://wiki.openstreetmap.org/wiki/Indoor%3D) <br>
*Utilizza OpenStreetMap, é una Web App*
- [OpenLevelUp](https://wiki.openstreetmap.org/wiki/OpenLevelUp/Use_cases/Schools_or_universities) <br>
*Utilizza OpenStreetMap, é una Web App*
- [GeoJSON](https://geojson.org/) <br>
*Formato interessante per rappresentare una mappa, convertibile poi in OSM*
### Altro
- [Woosmap](https://www.woosmap.com/en/products/indoor-mapping) <br>
*A Pagamento, hanno una pagina di GitHub, la funzione di navigazione indoor è in Early Access*
- [WRLD](https://www.wrld3d.com/#INTRO) <br>
*Modellazione 3D di mappe indoor*
- [inMapz](https://apps.apple.com/us/app/inmapz-indoor-navigation-maps/id1064844439) <br>
*Applicazione per Android e iOS, consente la navigazione indoor per alcuni aeroporti e edifici.*
- [Navin](https://nav-in.com/) <br>
*Applicazione per Android e iOS, consente navigazione indoor e outdoor, con visualizzazione 2D e 3D*
- [Navigine App](https://play.google.com/store/apps/details?id=com.navigine.navigine&hl=en&gl=US) <br>
*Applicazione per Android e iOS, consente di visualizzare le mappe create su navigine e navigazione.*

## Approfondimento su Navigine
### Informazioni su Demo Navigine per Android
Necessita della registrazione sul [sito](https://locations.navigine.com/dashboard) per l'utilizzo.

Una volta completata la registrazione, la demo necessita il login da parte dell'utente per poter accedere alle mappe create da quest'ultimo.

Per la creazione di mappe viene fornita una dashboard dove vi sono alcune funzionalità: 
- Possibilità di caricare una piantina della mappa in formati differenti: svg, png o jpg, con dimensione massima pari a 5Mb.
- Al momento non vi è una differenza percettibile tra i tre formati. Il formato svg sembra essere automaticamente convertito in png o jpg nell'applicazione Demo, per cui vi è una lieve perdità di qualità quando si effettua lo zoom
- Possono essere aggiunti più piani.
- E' possibile inserire ed editare sulla mappa:
	- Posizione dei Beacon
	- Bounds (muri)
	- Punti di Interesse
	- Percorsi di navigazione
	- Aree (Stanze etc)
	- Scale
- Al momento, la demo per il login utilizza l'userHash generato dalla registrazione sul sito del creatore della mappa. Sembra però essere possibile definire un sistema di utenti con proprio account etc.
- Più informazioni sul setup di mappe e dashboard sono presenti sulle [Docs](https://docs.navigine.com/)
- La demo, e in generale la mappa creata, è integrabile con l'[SDK](https://github.com/Navigine/Indoor-Navigation-Android-Mobile-SDK-2.0/wiki) messo a disposizione.
- L'SDK fornisce delle classi e metodi per poter ottenere informazioni su aree, percorsi (routing tra due o più punti), display di mappe, etc, più [info](https://github.com/Navigine/Indoor-Navigation-Android-Mobile-SDK-2.0/wiki/Android-Studio-Integration).
- Permette di aggiungere e rimuovere sensori/beacon.
- Fornisce Listeners e Getters.
- Download delle mappe dai server di Navigine.

#### Testing 

L'applicazione è stata testata sia tramite l'emulatore fornito da Android Studio, sia da un dispositivo reale.

La demo si presenta come una vera e propria applicazione completa, il progetto presenta ViewModels, Adapters, Activity e molti Fragment suddivisi per compiti, e un ampia parte di questi dedicati al debugging.

All'apertura l'applicazione richiede il login da parte dell'utente, inserendo quindi un UserHash. Per semplificare l'accesso, è stato modificato il codice rendendo di "default" l'userHash utilizzato per i test:

```
// Esempio della modifica
// Questa classe gestisce le infomazioni di accesso dell'utente (che sono poi anche mostrate nel layout della visualizzazione del profilo) 
// Al momento sono presenti, eccetto per l'userHash, dei dati fittizi.
public class UserSession {

    public static String USER_HASH       = "userHash";
    public static String USER_NAME       = "user";
    public static String USER_COMPANY    = "company";
    public static String USER_EMAIL      = "default@mail.com";
    public static String USER_AVATAR_URL = "";
    public static String LOCATION_SERVER = BuildConfig.DEFAULT_SERVER_URL;
}
```
Una volta autenticati, l'applicazione presenta quattro principali sezioni:
- La prima che si occupa di gestire la scelta dell'edificio da visualizzare, elencati tramite una lista.
- La seconda che si occupa di mostrare la mappa, con punti di interesse interattivi, routes percorribili (nel caso ci siano dei beacon attivi, i quali sono necessari per ottenere le routes e la posizione dell'utente) con interfaccia grafica di navigazione e direzioni.
- La terza che si occupa di debugging, mostra sensori, indirizzi mac di beacon, informazioni generali sul dispositivo.
- La quarta che si occupa della gestione dell'account dell'utente.

La principale sezione, che più interessa ai nostri scopi, è la seconda, ovvero quella di navigazione.
Essa presenta già un sistema di visualizzazione e navigazione della mappa ben realizzato.
E' possibile:
- Ingrandire e Rimpicciolire la mappa.
- Modificare il piano che si vuole visualizzare.
- Interagire con i punti di interesse impostati dal Map Manager, visualizzandone delle proprietà e la possibilità di navigazione.
- Filtrare per punti di interesse in base al tipo (sono presenti di default diversi tipi di POI).
- Navigare tra punti di interesse, dove verrà mostrato il percorso ideale in base a come sono stati realizzati sul Map Manager.
- Visualizzare le direzioni per arrivare ad una destinazione.
- Centrare la mappa in base alla posizione dell'utente.

Non è stato possibile testare al massimo delle sue potenzialità il sistema di navigazione in quanto si necessitano i beacon fisici. 

Forzando però l'applicazione ad impostare la posizione dell'utente ad una specifica coordinata, all'interno del "NavigationFragment" utilizzando la classe "Position" e fornendo una posizione casuale all'interno della mappa, è stato possibile effettuare una pseudonavigazione utilizzando dei beacon fittizi (ottenuti inserendo sul Map Manager l'indirizzo mac dei beacon rilevati dalla sezione di debugging) e le route tracciate sul Map Manager. L'applicazione fornice effettivamente un percorso per raggiungere un determinato punto di interesse ma impreciso (fornisce delle indicazioni riguardanti i metri mancanti alla destinazione che non sono effettivamente verificabili, etc.) in quanto bisognerebbe utilizzare i [beacon reali](https://docs.navigine.com/en/locations_guide).



### Informazioni su Demo Navigine Flutter
Come la demo per Android, richiede la registrazione, la presenza dell'userHash nel codice e la definizione di una mappa sul loro sito.

La [demo](https://github.com/Navigine/Indoor-Navigation-Flutter-SDK/tree/main/example) si presenta molto più semplice rispetto a quella Android, che può definirsi quasi una vera e propria applicazione completa.

Essa permette di visualizzare a schermo la mappa dell'edificio scelto, permettendo lo zoom in e out di quest'ultima.
Sono presenti i punti di interesse (al momento però non vi è un interazione, sono solamente mostrati a schermo), e un'icona posizionata staticamente che rappresenta la posizione corrente dell'utente. 
Inoltre sono presenti varie stampe che forniscono informazioni di debugging riguardanti locations, percorsi (routes) e oggetti della mappa (La posizione dell'utente nel nostro caso).

La demo ovviamente fornisce anche l'SDK, dove nel caso di Flutter, è definibile come un plugin.

Esso fornisce funzionalità molto simili a quelle fornite per Android (e iOS).

Le varie librerie sono divise per types e managers, e due classi principali che si occupano di gestire le location.

La repository di GitHub che contiene l'SDK e l'esempio sembra essere in costante aggiornamento, quindi le procedure di installazione potrebbero cambiare, e protrebbero essere aggiunte più funzionalità.


#### Testing 

La demo è stata testata su un ambiente Android. Per essere testata, oltre alla installazione di Flutter e del progetto (Può essere seguita [qui](https://github.com/Navigine/Indoor-Navigation-Flutter-SDK), necessita di alcune modifiche al codice.
In particolare viene richiesto l'userHash dell'utente proprietario delle mappe nel file "MainActivity.java":

```
// Esempio di setting dell userHash
public class MainActivity extends FlutterActivity {
  @Override
  public void configureFlutterEngine(@NonNull FlutterEngine flutterEngine) {
    Navigine.initialize(getApplicationContext());
    NavigineSdk.setUserHash("userHash");
    super.configureFlutterEngine(flutterEngine);
  }
}
```
e viene richiesto l'id dell'edificio (locationId), e del suo piano (sublocationId) nel file "main.dart":

```
void main() {
  runApp(MaterialApp(home: MainPage()));
}

int LOCATION_ID = 495; // Put here your location id
int SUBLOCATION_ID = 652; // Put here your sublocation id

```
Una volta impostati i parametri sopra elencati, l'applicazione all'avvio (con il comando "flutter run" nel terminale aperto nella cartella del progetto), mosterà la mappa con il piano indicato.

Per ogni interazione con la mappa, l'applicazione Demo stampa in console alcune informazioni di debugging come la posizione x,y del punto toccato sulla mappa e altre informazioni. 

Esempio:
```
I/GestureDetector(31068): handleMessage TAP
I/flutter (31068): onSingleTap
I/flutter (31068): Point(264.029296875, 861.96875)
```

### Algoritmi di navigazione
Navigine utilizza diverse misurazioni per triangolare la posizione dell'utente, quali:
- Accelerometro
- Giroscopio
- Magnetometro
- Barometro
- Orientamento
- Localizzione
- WiFi
- BLE (Bluetooth Low Energy)
- WiFi RTT (WiFi Round Trip Time)
- Beacon

Nel codice sorgente vengono utilizzati contemporaneamente:
- 1 strumento di misurazione tramite onde radio (WiFi, Beacon, ...)
- 1 strumento di misurazione tramite sensori (Magnetometro, Accelerometro, ...)

### Requisiti Minimi
#### Android
- Android SDK API >= 21 (Android 5.0+);
- Supporto per Bluetooth 4.0;
- CPU delle seguenti architetture: arm, arm64, x86, x86_64.

#### Flutter
- Supporto versione Android: SDK 21+ 
- Supporto versione iOS: iOS 12+

### Considerazioni Attuali

Navigine sembra essere una valida soluzione al problema principale. Fornisce, soprattutto tramite l'SDK Android, un ottimo punto di partenza dell'applicazione finale. Avendo già disponibili degli algoritmi di navigazione, e soprattutto una rappresentazione della mappa, una volta eseguita l'integrazione si potrebbe iniziare ad estendere l'applicazione Demo (creando ovviamente un progetto in Android Studio da zero) introducendo le preferenze dell'utente e tutto ciò rimanente. Si potrebbe poi provare ad utilizzare dei Beacon fisici (reali), in combinazione con la mappa vera e propria dell'edificio desirato.

## Piantine U14

Sono state realizzate delle piantine (eventualmente convertibili in diversi formati di immagine) dell'edificio U14 sulla base dei riferimenti forniti nella cartella  **"Mappa U14/Riferimenti"**  e in seguito ad una investigazione effettuata direttamente nell'edificio dai membri dello stage, in particolare sulle singole stanze (per capire se fossero aule di professori, di studio, uscite di emergenza ecc.).

Le piantine sono state realizzate con uno stile molto semplice ma funzionale attraverso la seguente [WebApp](https://planner5d.com) e il software *"Adobe Photoshop"* e verranno utilizzate per la navigazione all'interno dell'applicazione. 

Un esempio di progetto di mappa (del piano 0) è disponibile [qui](https://planner5d.com/v?key=daccaeafb12581cf8f3100fa9d092315&viewMode=2d),  mentre i file veri e propri sono disponibili nella cartella **"Mappa U14"**.

Le piantine sono state inserite nel sistema di navigine attraverso la piattaforma descritta nell'approfondimento.
Sono state inserite le routes di navigazione, i punti di interesse fondamentali, sistema di elevazione per scale e ascensori e tutti i muri dell'edificio.

In seguito le immagini delle mappe impostate su Navigine:

### U14 - Piano -1

![U14 - Piano -1](/Mappa%20U14/Navigine/U14%20-%20Navigine%20-1.png)

### U14 - Piano 0

![U14 - Piano 0](/Mappa%20U14/Navigine/U14%20-%20Navigine%200.png)

### U14 - Piano 1

![U14 - Piano 1](/Mappa%20U14/Navigine/U14%20-%20Navigine%201.png)

### U14 - Piano 2

![U14 - Piano 2](/Mappa%20U14/Navigine/U14%20-%20Navigine%202.png)

## Test su Beacon Estimote

Dopo aver acquisito alcuni Beacon Estimote (iBeacon), sono stati analizzati e testati per verificarne la funzionalità.

Sul campione dato solo un Beacon si è rilevato funzionante, dopo un cambio della batteria ([CR2477 3V](https://www.amazon.it/dp/B08F9HSS6X?psc=1&ref=ppx_yo2ov_dt_b_product_details)), esso attraverso alcune app fornisce le seguenti informazioni:

- ID
- Major
- Minor
- RSSI
- Accuracy
- Proximity
- Distance (in metri)

I dati sono stati prelevati specificamente dall'applicazione [Locate Beacon](https://apps.apple.com/it/app/locate-beacon/id738709014?l=en), in quanto l'applicazione [Estimote](https://apps.apple.com/it/app/estimote/id686915066?l=en) si arresta in modo imprevedibile quando si cerca di accedere alle informazioni del Beacon rilevato (probabilmente perchè i Beacon in esame sono abbastanza datati).

L'applicazione Estimote però fornisce la possibilità di creare un *Beacon Virtuale* attraverso il proprio smartphone.

Inserendo quindi il seguente id "8492E75F-4FD6-469D-B132-043FE94921D8" in un'applicazione di rilevazione Beacon (come Locate Beacon), il Virtual Beacon si comporterà esattamente come un Beacon reale, fornendo le informazioni descritte sopra.

I Beacon, essendo degli iBeacon, possono essere inseriti e utilizzati nella piattaforma di Navigine.

Beacon usati per il test: Beacon Estimote, Developer preview kit. Compatibili con iPhone 4S, 5, 5C, 5S, iPad Mini, 3rd e 4th Generazione, Android 4.3+

## Applicazione Demo

Dopo alcuni test effettuati con i Beacon, il setup delle mappe e test dell'applicazione demo di [Navigine](https://gitlab.com/unimib-wayfinding/indoor-navigation-biancini-gargiulo#Approfondimento-su-Navigine), è stata creata sulla base della demo una applicazione "mockup" che tenta di rappresentare una ipotetica inferfaccia della applicazione finale, variando nello specifico i colori e alcune schermate per renderle più coerenti alle nostre necessità.

![Icona](/ScreenshotsDemo/app_icon.png)

<br>

L'icona dell'applicazione realizzata con il software "Adobe Photoshop".

![Login](/ScreenshotsDemo/login.png)

<br>

La schermata iniziale dell'applicazione dove si effettua il login tramite email e password. Nell'applicazione viene ancora utilizzato l'userHash al posto della email come metodo di login dato che non è stato creato ancora un sistema di account (che può essere implementato in futuro attraverso [Firebase Authentication](https://firebase.google.com/docs/auth?hl=it) per esempio).

![Sign Up](/ScreenshotsDemo/signup.png)

<br>

La schermata per la registrazioe di un utente attraverso un menù a tendina.

![Locations](/ScreenshotsDemo/locations.png)

La schermata che permette di effettuare la scelta dell'edificio (mappa di navigazione).

<br>

![Navigation](/ScreenshotsDemo/navigation.png)

La schermata di navigazione vera e propria dell'applicazione, con punti di interesse, zoom, piani etc. (si veda l'approfondimento su Navigine).

<br>

![Settings](/ScreenshotsDemo/settings.png)

La schermata che permette di gestire il proprio account e le preferenze di navigazione. Al momento sono state inserite quattro preferenze mockup attivabili e disattivabili tramite uno Switch, ma come per il sistema di account, è implementabile in futuro. 

<br>

Il tema è stato variato, tendendo a colori rossi, ovvero quelli utilizzati dall'università Bicocca.

