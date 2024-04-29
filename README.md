# BOOLZAPP

- MILESTONE 1 
   Visualizzazione dinamica della lista contatti: tramite la direttiva v-for, visualizzare nome e immagine di ogni contatto.

- MILESTONE 2
   Visualizzazione dinamica dei messaggi: tramite la direttiva v-for, visualizzare tutti i messaggi relativi al contatto attivo all’interno del pannello della conversazione. Click sul contatto mostra la conversazione del contatto cliccato.

--- 

## Analisi dei dati
 
   - Creo un data.js e implemento il costrutto base per utilizzare vue.js

   - Analizzo la struttura dati che ho all interno di data:

   - Contacts è un array di oggetti(elemento più esterno)
     Poi ho degli oggetti ovvero gli avatar contatti che trovo sulla sinistra della mia webb app.
     Ogni Oggetto(avatar) è costituito da chiavi, rispettivamente: name, avatar,
     visible(variabile con valore booleano), messages.
     Messages e una chiave array nella
     quale sono presenti tre oggetti ognuno dei quali ha tre chiavi:
     date, message e status(classe CSS).

--- 

## Inserimento dinamico dei dati in Pagina

  - Analizzando l html fornitomi vado ad    eliminare le ridondanze.
  lascio un unico contatto(div class="contact"), nel quale applico il v-for.
  Gli passo un elemento corrente ed un indice in contacts(array) 
  al tag img aggiungo la forma contratta v-bind
  dinamicizzando così il tag.
  Utilizzo i template literals e al loro interno scrivo il percorso delle immagini.
  sostituisco l'elemento img della cartella con la sintassi dinamica ${} nella quale deposito {curContact "elemeto corrente del ciclo for in"
  .avatar(chiave)}.jpg
  Cosi facendo le immagini sono state stampate dinamicamente nella mia web app.

  - Attraverso l'interpolazione {{}} stampo sempre dinamicamente il nome del mio avatar
  {{ curContact.name }}.

  - Nel data.js creo una varibile activeIndex nella quale deposito il valore 0 number.

  - Nel contenitore destro vado a sostituire l'immagine statica con l'immagine dinamica
  :src (procedura usata in precedenza per rendere
  attributi e classi dinamice) tra template literals prendo percorso delle immgagine
  dalla cartella più esterna fino al file desiderato che sostituisco utilizzando la sintassi dollaro graffe ${contacts[activeIndex].avatar}.jpg
  A differenza di prima ora abbiamo associato alla chiave avatar un contatore.
  Dunque il primo elemento(Michele) che corrisponde ad activeIndex 0 sarà stampato nella parte alta della chat.
  Pure in alt tramite classe dinamica e all tag small tramite interpolazione applichiamo lo stesso principo: 
  contacts[activeIndex].name

---

###  Evento Click

  Nei methods del nostro data.js creiamo una funzione che ci permette al click di selezionare una chat scorrendo tra i nostri contatti e di visualizzarla nella parte destra dell'applicazione.
  Inizializziamo la nostra funzione chooseAvatar
  e al tag contact lo inseriamo un @click = "chooseAvatar(index)" passandogli come argomento l'indice del nostro contatto.
  Nell methods alla funzione chooseAvatar passo un argomento curIndex.
  Richiamo la variabile activeIndex con la parolachiave this = a curIndex.
  Cosi facendo al click su un contatto questo sarà
  Visualizzato nella parte destra in alto della chat.

---

### Messaggi dinamici

 Ogni contatto come detto in precedenza ha un array di messaggi corrispondenti che devono essere visualizzati dinamicamente quando selzioniamo l avatar corrispondente.

 Scorrendo nel html elimino il div che contiene il message con classe received e lascio solo quello con classe sent

 Elimino la elimino anche sent(è una seconda classe all interno del mio tag message)
 applico una classe dinamica e un ciclo for in
 nel for in inizializzo un curMessage "messaggio" corrente in contacts[activeIndex].messages
 L'activeIndex mi facilita la vita facendomi penetrare all interno dell array messages
 Tra il tag span message-text grazie ad interpolazione stampo in pagina curMessage.message(ovvero il messaggio corrente corrispondente ad ogni avatar)
 Aggiungendo la classe dinamica curMessage.status
 separo i messaggi inviati da quelli ricevuti.
 Questo avviene perche la chiave status corrisponde a due classi css: sent e recevied.

 Ora entrambi i MIlestone sono stati svolti
 Al click di un avatar sulla parte destra avremo:
 In cima il nome dell avatar e nella parte centrale i messaggi che ha ricevuto e le risposte. 

---

 - MILESTONE 3

   Aggiunta di messaggio: L'utente scrive un testo nella parte bassa e digitando "enter" il testo viene aggiunto al thread sopra, come messaggio verde.

   Risposta dall'interolcutore: ad ogni inserimento di un messaggio, l'utente riceverà
   un ok come risposta, che apparirà dopo un secondo 
    

    