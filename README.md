# ex-react-animali-preferiti
Esercizio L07


📌 Milestone 1: Inserire un Componente React

Monta un componente React all’interno dell’elemento con classe .lista-animali.

Il componente deve includere:
Un elemento <details> con titolo "Animali", che contiene:
Una lista <ul> statica che viene creata a partire da un array di stringhe (animals) dove ciascuna stringa rappresenta il nome di un animale.

Obiettivo: Mostrare la struttura base della lista di animali con un <details> che può essere espanso o contratto.


📌 Milestone 2: Aggiungere Animali Casuali

Trasforma l’array animals usando useState (l’array è inizialmente vuoto).
Aggiungi un bottone "Aggiungi Animale" sopra il <details>.
Cliccando il bottone, un animale casuale viene aggiunto alla lista.
Usa un array predefinito per scegliere casualmente:

const animalsChoices = ["Cane", "Gatto", "Pappagallo", "Cavallo", "Panda"];
L’animale selezionato deve essere aggiunto all’interno della lista <ul> come <li>.

Obiettivo: L’utente può vedere gli animali aggiunti dinamicamente nella lista.


📌 Milestone 3: Usare una Modale per Aggiungere Animali

Partendo da questo componente Modal:

function Modal({
      title, 
      content, 
      show = false, 
      onClose = () => {}
  }){
      return show && ReactDOM.createPortal(
          <div className="modal-container">
              <div className="modal">
                  <h2>{title}</h2>
                  <p>{content}</p>
                  <button onClick={onClose}>Annulla</button>
              </div>
          </div>,
          document.body
      )
  }

.modal-container{
    position: fixed;
    top: 0;
    left: 0;
    width: 100%;
    height: 100%;
    background-color: rgba(0, 0, 0, 0.75);
    display: flex;
    justify-content: center;
    align-items: center;
}
.modal{
    background-color: white;
    padding: 20px;
    border-radius: 5px;
}
Espandilo affinché:
La vecchia prop content può essere usata per passare un componente qualsiasi.
Un nuovo div in fondo alla modale contiene il bottone Annulla e un nuovo bottone Conferma.
Una nuova prop onConfirm si aspetta una funzione per gestire l’azione di conferma.
Sostituisci l’aggiunta casuale dell’animale con una modale interattiva:
Cliccando il bottone "Aggiungi Animale," si apre una modale.
La modale include un input di testo (passato al prop content) per inserire il nome di un animale.
Conferma: Aggiunge l’animale alla lista e chiude la modale.
Annulla: Chiude la modale senza modificare la lista.

Obiettivo: L’utente può aggiungere animali specifici utilizzando la modale.