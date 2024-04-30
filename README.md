**SAML SSO (Single Sign-On) Python Implementation**

Descrizione

Questo progetto fornisce un'implementazione semplice di generazione e parsing di richieste e risposte SAML (Security Assertion Markup Language) in Python, senza crittografia o firme digitali. È utile per comprendere i concetti di base di SAML.

Spiegazione dettagliata del codice:

1. **Importazione delle librerie:**
   - `xml.etree.ElementTree`: Questa libreria è utilizzata per manipolare XML in Python.

2. **Definizione delle classi:**
   - `SAMLRequest`: Questa classe gestisce la generazione e il parsing delle richieste SAML. Nel metodo `generate`, crea una stringa XML con un tag `<UserID>` che contiene l'ID dell'utente. Nel metodo `parse`, estrae l'ID dell'utente dalla stringa XML.
   - `SAMLResponse`: Questa classe gestisce la generazione e il parsing delle risposte SAML. Nel metodo `generate`, crea una stringa XML con tag `<UserID>` per l'ID dell'utente, `<RandomID>` per un ID generato casualmente e `<Timestamp>` per il timestamp corrente. Nel metodo `parse`, estrae l'ID dell'utente, l'ID casuale e il timestamp dalla stringa XML.
   - `ServiceProvider`: Questa classe simula il Service Provider (SP) e contiene un metodo `verify_response` per verificare la risposta SAML ricevuta confrontando l'ID casuale con quello memorizzato nell'IdP.

3. **Esempio di utilizzo:**
   - Viene istanziata un'istanza di `SAMLResponse` per simulare l'Identity Provider (IdP) e un'istanza di `ServiceProvider`.
   - Viene generata una richiesta SAML utilizzando l'istanza di `SAMLRequest`, e il risultato viene stampato.
   - Viene effettuato il parsing della richiesta SAML utilizzando nuovamente l'istanza di `SAMLRequest`, e il risultato (l'ID dell'utente) viene stampato.
   - Viene generata una risposta SAML utilizzando l'istanza di `SAMLResponse`, e il risultato viene stampato.
   - Viene effettuata la verifica della risposta SAML utilizzando il metodo `verify_response` del Service Provider, e il risultato viene stampato.

4. **Verifica della risposta SAML:**
   - La verifica della risposta SAML avviene nel metodo `verify_response` del Service Provider.
   - Viene effettuato il parsing della risposta SAML per ottenere l'ID dell'utente, l'ID casuale e il timestamp.
   - Viene confrontato l'ID casuale con quello memorizzato nell'IdP.
   - Se l'ID casuale coincide, la risposta viene considerata valida e viene restituito `True`, altrimenti viene restituito `False`.
