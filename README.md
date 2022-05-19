# Einführung
Dieses Repository dient als Ausgangspunkt für die Code Aufgabe, die man als Bewerber\*in bei anybill als Web-Entwickler\*in durchführen muss.

# Ablauf
**Das Repository soll geforkt werden.** Alle Änderungen und Entwicklungen sollten in einem privaten **Fork** dieses Repositories durchgeführt werden.
Bearbeite die dir gestellte Aufgabe unter Einbezug der Zeitvorgaben so gut wie möglich. Achte dabei darauf, dass die gestellten Mindestvoraussetzungen erfüllt werden. Sind diese erledigt, können weitere optionale Aufgaben erfüllt werden. Die optionale Aufgaben sollten nur dann erledigt werden, wenn noch freie Zeit vorhanden ist. Diese dienen dazu, weitere Fähigkeiten und Kenntnisse unter Beweis zu stellen und eventuell hervorzuheben. Die optionalen Aufgaben sind lediglich eine Sammlung von typischen Aufgaben, die ein\*e Web-Entwickler\*in im Arbeitsalltag lösen muss.

# Aufgabe
Die Aufgabe besteht daraus, eine Webseite mit einem Formular zur Registrierung eines Accounts bei anybill zu entwickeln. Dabei kann das offizielle Formular von anybill als Beispielvorlage benutzt werden. Das Formular findet man unter https://test.anybill.de/business, indem man auf den Button **Unverbindlich Anmelden** klickt:
![image](https://user-images.githubusercontent.com/8490302/169285063-140df3f3-d7f5-45e1-a945-8621c4f29373.png)
Das Formular wird von Händlern (z.B. Getränktemärkte, Gastronomen, etc.) genutzt, die Interesse an einem digitalen Bon mit anybill haben.

## Mindestvoraussetzungen
Entwickle eine Webseite mit einem Formular zur Anmeldung bei anybill. Halte dich dabei an folgende **drei Mindestvoraussetzungen**:
- **Mindestvoraussetzungen 1:** Benutze für diese Aufgabe **Typescript** und einen **beliebiges Frontend-Framework** (NuxtJs, Vue, React, NextJs, Angular, etc.) deiner Wahl. Da anybill hauptsächlich NuxtJs verwendet, wäre das die präferierte Wahl. Aber auch andere Frameworks sind völlig in Ordnung! 
- **Mindestvoraussetzungen 2:** Das Formular sollte mindestens die Eingaben für **Unternehmensname**, **E-Mail** und einer **Auswahl der benutzen Kassensoftware** des Händlers enthalten
- **Mindestvoraussetzungen 3:** Kommunizieren mit unserer öffentlichen API. Die API ist unter https://partner.stg.anybill.de/api/swagger/index.html dokumentiert. Benutze dabei die folgenden zwei Endpunkte:
  - [GET /customer/pos](https://partner.stg.anybill.de/api/swagger/index.html#/Customer/get_customer_pos): 
  Dieser Endpunkt gibt eine die Kassensoftwareliste zurück. Dabei sind vor allem die **Id** und der **Name** der Kassensoftware wichtig. Der Name der Kassensoftware soll im **Auswahlfeld der benutzen Kassensoftware** des Händler angezeigt werden. Beispiel: 
  ```console
  foo@bar:~$ curl https://partner.stg.anybill.de/api/customer/pos
  ```
  Das Ergebnis ist eine Liste mit solchen Einträgen:
  ```json
  [
    {
      "Id": "44901dc6-c9ab-41d9-8f4f-5a719071bdde",
      "Name": "Test-PosSoftwareCustomer",
      "IsActivated": true,
      "State": "Live"
    }
  ]
  ```
  - [POST /customer/vendor/apply](https://partner.stg.anybill.de/api/swagger/index.html#/Customer/post_customer_vendor_apply)
  Dieser Endpunkt soll dazu benutzt werden, die im Formular eingegeben Daten abzuschicken und die Registrierung abzuschließen. Dabei müssen mindestens die folgenden Angaben verschickt werden:
  1. **CompanyName:** Der eingegebene **Unternehmensname**
  2. **Email:** Die eingegeben E-Mail
  3. **PosSoftwareCustomerId:** Die Id der ausgewählten **Kassensoftware** (Im Beispiel oben "44901dc6-c9ab-41d9-8f4f-5a719071bdde")
  Beispiel: POST /customer/vendor/apply
  ```json
  {
     "CompanyName": "Test Bewerbung Web",
     "Email": "random@anybill.de",
     "PosSoftwareCustomerId": "44901dc6-c9ab-41d9-8f4f-5a719071bdde"
  }
  ```
## Optionale Aufgaben
Neben den Mindestvoraussetzungen können nach Belieben noch weitere Features in die Webseite integriert werden. Gibt es bestimmte Themen, in denen du dich 

# Abgabe
- Vorgehen
- Benutzes Frameworks und Bibliotheken
- Beschreibung der implementieren Features
