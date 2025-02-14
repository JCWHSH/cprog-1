# VSCode

Dies ist ein Tutorial zur Installation von VSCode um damit C zu programmieren.

Es beginnt mit einer betrisbssystem-spezifischen Anleitung für Linux, MacOS und Windows. 

Im Anschluss daran gibt es einen allgemeinen Teil, in dem wir unsere Installation testen und ausprobieren.

Entworfen und getestet wurde die Anleitung auf frisch aufgesetzten Betriebssystemen. Sollte etwas nicht so funktionieren wie beschrieben schaut bitte in die Troubleshooting-Sektion. Hier gibt es zunächst einen allgemeinen Teil, der für alle gilt. Danach gibt es Abschnitte für die drei Betriebssysteme.


## Linux

<details>
<summary>Click to expand</summary>

Welcome to the light side. We all know you just clicked for the lulz.

</details>

## MacOS

<details>
  
<summary>Hier klicken um VSCode auf MacOS zu installieren</summary>  

### Bevor wir beginnen
Damit wir mit Visual Studio Code C programmieren können brauchen wir einen Compiler und Debugger. 

Dazu öffnen wir, z. B. mit Spotlight oder aus dem Launchpad, ein Terminal und überprüfen, ob dies der Fall ist, indem wir
> clang –version
eingeben. Bekommen wir eine Vesionsnummer angezeigt können wir bei Schritt 1 weitermachen.
Ist dies nicht der Fall geben wir
> Xcode-select –install
ein und überprüfen das Ergebnis mit einem weiteren 
> clang –version

### Installation von Visual Studio Code
Wir öffnen im Browser unserer Wahl die folgende Website:
https://code.visualstudio.com/docs?dv=osx
und laden dadurch VS Code for Mac herunter.

Danach schieben wir im Finder einfach die Datei `<Visual Studio Code.app>` in den `<Programme>` Ordner. 

### Konfiguration von VSCode

#### Grundeinrichtung

Wir öffnen als nächstes unser Visual Studio Code.
Ein kleiner Hinweis vorab: Irgendwann wir VSCode wahrscheinlich ein Update auf die Insiders-Version anbieten. Davon wird abgeraten. Insiders bedeutet hier Beta-Tester und ein stabiler Betrieb ist wichtiger als die neuesten Features, die beim C-Programmieren kaum zum Tragen kommen werden.

<img width="419" alt="image" src="https://user-images.githubusercontent.com/78163337/111457567-a446cb80-8718-11eb-9e1d-26213b51a86c.png">

Die „richtige“ Antwort wäre also `<Nicht mehr anzeigen>`.

Nun installieren wir einige Erweiterungen, in dem wir auf das Symbol mit 3+1 Quadraten auf der linken Seite klicken:

<img width="367" alt="image" src="https://user-images.githubusercontent.com/78163337/112048606-e031c480-8b4e-11eb-81a7-13dccddf3201.png">

Wir möchten die drei Extensions C/C++, Code Runner und GitLens. Oft gibt es eine reguläre, stabile und eine Vorab-Test-Version. Man kann sich an den Downloadzahlen aus den folgenden Screenshots orientieren, um die stabile Version zu erwischen:

![image](https://user-images.githubusercontent.com/78163337/112048686-f50e5800-8b4e-11eb-871f-51418cd4aaf6.png)

![image](https://user-images.githubusercontent.com/78163337/112048709-fb9ccf80-8b4e-11eb-8c6b-92e817526a56.png)

![image](https://user-images.githubusercontent.com/78163337/112048726-00618380-8b4f-11eb-84c5-c4ed73dc9d22.png)

In der Startansicht wählen wir `<„Open folder…“>`

Hier können wir z.B. im Ordner „Dokumente“ einen neuen Ordner „Projekte“ anlegen.
In diesem erstellen wir eine neue Datei,

nennen sie 
> HelloWorld.c
Und füllen sie auch gleich mit unserem ersten kleinen Programm:

<img width="376" alt="image" src="https://user-images.githubusercontent.com/78163337/112048927-369f0300-8b4f-11eb-9c8b-967b51e6c29b.png">

Wir rechtsklicken (oder control+Klick) in das Fenster mit unserem Code und wählen „Run Code“. Alternativ Klicken wir oben rechts auf Play oder benutzen die Tastenkombination aus dem Screenshot:

![image](https://user-images.githubusercontent.com/78163337/112048960-41f22e80-8b4f-11eb-9cb2-14f6c10ee3bd.png)

Sollte es dabei Problemchen geben, kann das an einem Tippfehler liegen, mit dem wir uns hier nicht lange aufhalten wollen. 

<details>
<summary>Daher hier das Programm zum Kopieren und Einfügen</summary>

> #include <stdio.h>
> int main(){
>   printf("Hello World!\n");
>   return 0;
> }

</details>

Spätestens jetzt können wir uns hoffentlich über unser erstes Programm freuen:

<img width="283" alt="image" src="https://user-images.githubusercontent.com/78163337/112049524-09068980-8b50-11eb-94c8-79f7167ca78e.png">

Damit wir später auch Programme mit Benutzereingaben ausführen können, klicken wir unten links auf das Zahnrad und wählen dann Settings.

<img width="219" alt="image" src="https://user-images.githubusercontent.com/78163337/112049574-1ae82c80-8b50-11eb-9a04-7d40bc4943b6.png">

Dort geben wir „code-runner.runintermimal“ in die Suche ein und setzen den entsprechenden Haken. 

![image](https://user-images.githubusercontent.com/78163337/111459615-351ea680-871b-11eb-9819-b7dce6bfdf37.png)

#### Konfiguration des Debuggers

Für den Fall, dass es in etwas komplizierteren Programmen zu Beginn mal nicht ganz rund läuft, richten wir auch gleich noch den Debugger ein.
Ein Debugger ist ein Werkzeug, das bei der Fehlersuche behilflich ist. Man kann es sich vielleicht als MRT oder Röntgengerät mit eingebauter Zeitlupe vorstellen.

Unser erstes Beispielprogramm HelloWorld.c funktioniert einerseits gut und enthält andererseits keine Variablen und nur eine Zeile sinnvoll "untersuchbaren" Code, sodass es zum Ausprobieren des Debuggers ungeeignet ist.

Wir wählen daher links die Datei debugtest.c und klicken oben auf

> Terminal

und dann

> Configure Default Build Task

Auf meinem Rechner ist noch ein weiterer Compiler installiert, nicht irritieren lassen, wenn die Auswahl ein wenig anders aussieht.

![image](https://user-images.githubusercontent.com/78163337/112050085-bd081480-8b50-11eb-80df-a291eb903839.png)

In unserem Projekte Ordner legt uns VSCode nun automatisch eine Datei „tasks.json“ an. Diese gilt auch für alle Programme in diesem Ordner, wir müssen diesen Schritt also nur einmal ausführen. Sollte es im Folgenden Probleme geben, ist eine funktionierende Version dieser Datei im Anhang. Pfade, etc. können aber abweichen, daher dient diese eher dem Vergleich, als dem kompletten Ersetzen.

Wir schreiben nun unser zweites Programm „debugtest.c“, mit dem Inhalt aus dem Screenshot unten:

<img width="226" alt="image" src="https://user-images.githubusercontent.com/78163337/112050268-f2146700-8b50-11eb-8565-632c2626e7f5.png">

**_Jetzt ist es wichtig, dass tatsächlich auch debugtest.c geöffnet und markiert ist (Focus hat), und nicht tasks.json, da VSCode nun eine weitere Konfigurationsdatei erzeugen wird, und zwar basierend auf der aktiven Datei._**

Wir achten also darauf, dass wir unseren Code sehen können und klicken oben auf
> Run
und dann
> Start Debugging
und gehen dann wie auf den Screenshots markiert vor:

![image](https://user-images.githubusercontent.com/78163337/112050854-939bb880-8b51-11eb-82ba-055a312bffa0.png)

![image](https://user-images.githubusercontent.com/78163337/112050881-97c7d600-8b51-11eb-869a-f05a0b726c1c.png)


</details>

## Windows

<details> 
<summary>Hier klicken um VSCode auf Windows zu installieren</summary> 

### Bevor wir beginnen
Die Mutigen unter euch sind im Begriff sich mit drei Befehlen 4 Programme, 3 Extensions, 1 Schriftartenfamilie und 2 Programmiersprachen zu installieren.
Das spart eine Menge Zeit und wahrscheinlich zwei Dutzend Arbeitsschritte, bei denen sich Fehler einschleichen können. Trotzdem solltet ihr das nur bei absolut vertrauenswürdigen Quellen, wie hier ein Dokument aus dem Kurs von Prof. Dr. Will, in Erwägung ziehen. Gleich beim ersten Befehl sollten alle Warnleuchten angehen.

`<Set-ExecutionPolicy Bypass>`bedeutet, dass die üblichen Sicherheitseinstellungen umgangen werden und `<DownloadString('https://chocolatey.org/install.ps1')>` lädt ein Script (erkennbar an der Endung .ps1) aus dem Internet nach.

Bei chocolatey handelt es sich um einen sogenannten „Packet Manager“, mit dem sich sehr einfach Programme installieren und aktualisieren lassen.
Wer die Programme lieber von Hand installieren möchte, kann dies natürlich tun.
Zunächst benötigen wir auch nur einen Complier und Debugger, wir nutzen mingw, und dann Visual Studio Code (es gibt auch Visual Studio ohne Code, das ist etwas anderes).
Zu beachten ist jedoch, dass bei einer manuellen Installation Compiler und Debugger evtl. händisch zum „PATH“ hinzugefügt werden müssen. Das ist mit einer Suchmaschine eurer Wahl sicherlich auch kein Hexenwerk, sollte aber vor dem ersten Starten von VSCode erledigt sein.
In VSCode empfehlen wir die Installation der Extensions „C/C++“ und „Code Runner“.

### Installation von Visual Studio Code
Zunächst rechts-klicken wir ganz unten links auf das Windows-Icon und wählen im erscheinenden Menü „Windows PowerShell (Administrator)“:

<img width="276" alt="image" src="https://user-images.githubusercontent.com/78163337/111452622-000e5600-8713-11eb-9c34-0cbfdfcc411c.png">


In diese PowerShell kopieren wir am Stück folgende Zeile:

> Set-ExecutionPolicy Bypass -Scope Process -Force; [System.Net.ServicePointManager]::SecurityProtocol = [System.Net.ServicePointManager]::SecurityProtocol -bor 3072; iex ((New-Object System.Net.WebClient).DownloadString('https://chocolatey.org/install.ps1'))

und bestätigen mit „Enter“ und warten ab, bis uns PowerShell einen frischen Eingabeprompt anbietet:

<img width="163" alt="image" src="https://user-images.githubusercontent.com/78163337/111456918-d9065300-8717-11eb-93a9-88fddd8459ff.png">

Damit wir uns sicher sein können, dass die Änderungen wirksam sind, schließen wir das PowerShell Fenster und öffnen ein neues (wieder mit Administrator-Rechten)
Nun kopieren wir die folgende Zeile in die PowerShell, bestätigen mit Enter und warten wieder auf den Eingabeprompt.

> choco install mingw --version=8.1.0 -y

Und noch ein drittes Mal:

> choco install vscode vscode-cpptools vscode-code-runner vscode-gitlens git cascadiafonts python -y

Dieses Mal kann sich die Sache auch ein paar Minütchen ziehen, nicht nervös werden.
An dieser Stelle haben wir alles installiert was wir brauchen und können uns an die Einrichtung von VSCode machen.

### Konfiguration von VSCode

#### Grundeinrichtung

Auch die Grundeinrichtung von VSCode beginnen wir in PowerShell, diesmal jedoch als normaler Benutzer. Der Nutzer in diesem Beispiel heißt mail und er möchte seine Programm im „Dokumente“-Ordner aufbewahren, also wechseln wir mit 

> cd Documents

in das Verzeichnis:

<img width="159" alt="image" src="https://user-images.githubusercontent.com/78163337/111457345-5a5de580-8718-11eb-84e8-60ab31ce04f5.png">

Dort laden wir uns mit

> git clone https://github.com/and1yps/VSCodeForC.git

die Konfiguration (fast) fix und fertig von Github herunter:

Jetzt ist es endlich soweit und wir öffnen Visual Studio Code.

Ein kleiner Hinweis vorab: Irgendwann wird VSCode wahrscheinlich ein Update auf die Insiders-Version anbieten. Davon wird abgeraten. Insiders bedeutet hier Beta-Tester und ein stabiler Betrieb ist wichtiger als die neuesten Features, die beim C-Programmieren kaum zum Tragen kommen werden.

<img width="419" alt="image" src="https://user-images.githubusercontent.com/78163337/111457567-a446cb80-8718-11eb-9e1d-26213b51a86c.png">

Die „richtige“ Antwort wäre also `<Nicht mehr anzeigen>`.

In der Startansicht wählen wir „Open folder…“

<img width="239" alt="image" src="https://user-images.githubusercontent.com/78163337/111457735-dce6a500-8718-11eb-8ad8-504a45538b74.png">

Und wählen unter Dokumente\VSCodeForC\ den Ordner Projekte

<img width="371" alt="image" src="https://user-images.githubusercontent.com/78163337/111457815-f7b91980-8718-11eb-8ec2-c96cdb9df8e1.png">

Wir finden im Ordner Programmiersprache_C fertig vorbereitet die Datei HelloWorld.C

<img width="421" alt="image" src="https://user-images.githubusercontent.com/78163337/111458047-44045980-8719-11eb-8bdf-54a3d9e8febd.png">

Das Programm ist kurz und unspektakulär, aber ein echter Klassiker.

Wir rechtsklicken in das Fenster mit unserem Code und wählen „Run Code“

<img width="385" alt="image" src="https://user-images.githubusercontent.com/78163337/111458152-626a5500-8719-11eb-87fc-40ae6b391886.png">

Weiter unten sehen wir in der Mitte von vielen anderen, eher kryptisch anmutenden Dingen, die Ausgabe unseres Programms, nämlich "hello world".

<img width="283" alt="image" src="https://user-images.githubusercontent.com/78163337/111458210-77df7f00-8719-11eb-9e41-39180d41cfda.png">

Wer diese Ausgabe *nicht* erhält sollte sich an dieser Stelle der Troubleshooting-Sektion zuwenden. Solange ein Programm nicht abgearbeitet wird, wird auch das Folgende nicht funktionieren.

Damit unsere Programme später Input vom Terminal entgegennehmen können, z. B. mit scanf, müssen wir noch eine Einstellung vornehmen.

Also begeben wir uns die die Settings, geben „code-runner.runinterminal“ in die Suche ein und setzen den entsprechenden Haken.

<img width="310" alt="image" src="https://user-images.githubusercontent.com/78163337/111459570-246e3080-871b-11eb-8050-d287916a961c.png">

![image](https://user-images.githubusercontent.com/78163337/111459615-351ea680-871b-11eb-9819-b7dce6bfdf37.png)

#### Konfiguration des Debuggers

Für den Fall, dass es in etwas komplizierteren Programmen zu Beginn mal nicht ganz rund läuft, richten wir auch gleich noch den Debugger ein.
Ein Debugger ist ein Werkzeug, das bei der Fehlersuche behilflich ist. Man kann es sich vielleicht als MRT oder Röntgengerät mit eingebauter Zeitlupe vorstellen.

Unser erstes Beispielprogramm HelloWorld.c funktioniert einerseits gut und enthält andererseits keine Variablen und nur eine Zeile sinnvoll "untersuchbaren" Code, sodass es zum Ausprobieren des Debuggers ungeeignet ist.

Wir wählen daher links die Datei debugtest.c und klicken oben auf

> Run

und dann

> Start Debugging

und gehen dann wie auf den Screenshots markiert vor:

<img width="453" alt="image" src="https://user-images.githubusercontent.com/78163337/111460420-3ef4d980-871c-11eb-8171-68ef90b857eb.png">

<img width="453" alt="image" src="https://user-images.githubusercontent.com/78163337/111460432-42886080-871c-11eb-8ad9-c00c8c94a59f.png">

An dieser Stelle sind wir mit dem windows-spezifischen Teil der Installation und Grundeinrichtung durch, und begeben uns in den allgemeinen Teil dieses Tutorials, um unsere Arbeit zu testen und auszuprobieren.

</details>

## Ich habe VSCode bereits installiert

<details>
<summary>Click to expand</summary>

Kein Problem. Du kannst der entsprechenden Anleitung trotzdem einfach folgen. Falls du MacOS nutzt überspring einfach den Schritt mit dem Herunterladen und Installieren von VSCode an sich, falls du Windows benutzt kannst du einfach der Anleitung 100% folgen.

</details>

## Allgemeiner Teil

Nun testen wir unsere Installation und machen uns dabei schon ein wenig mit VSCode vertraut. Wir werden einen neuen Ordner anlegen, eine neue Datei erstellen, ein Programm schreiben und dieses abarbeiten und debuggen.

- [ ] Ordner angelegt
- [ ] Datei angelegt
- [ ] Programm geschrieben und gespeichert
- [ ] Programm abgearbeitet
- [ ] Programm debugt


### Ordner anlegen

Das Anlegen eines neuen Ordner ist denkbar einfach, jedoch gibt es ein paar Kleinigkeiten zu beachten, die sonste große Kopfschmerzen bereiten können.

Die wichtigste ist es Sonder- und Leerzeichen, Umlaute und andere nicht-ASCII-Zeichen unbedingt zu vermeiden. Spätestens wenn das eigene Programm inklusive Unterordner auf einem Produktionsserver ohne grafische Benutzeroberfläche landet führt das zu allerlei Schwierigkeiten. Wahrscheinlich geht es einem aber schon auf dem eigenen Rechner gehörig auf die Nerven.

Wie fast immer in VSCode führen viele Wege ans Ziel und es ist Geschmackssache, welchen man wählt.

Im folgenden Screenshot sind mal drei Möglichkeiten markiert (eine mit vorherigem Rechtsklick):



- [x] Ordner angelegt
- [ ] Datei angelegt
- [ ] Programm geschrieben und gespeichert
- [ ] Programm abgearbeitet
- [ ] Programm debugt


### Datei erstellen

Die Datei erstellt man genau wie den Ordner, nur der Kommandozeilen-Befehl lautet nicht `<mkdir>`, sondern `<touch>` bei Linux und MacOS bzw. `<New-Item -ItemType file>` in der Windows PowerShell.

Damit VSCode weiß, wie es mit einer Datei umzugehen hat, muss sie von uns mit der richtigen Endung versehen werden. Wir legen zum Ausprobieren zwei neue Dateien an:

> beispielProgramm.c   // Eine Datei mit C-Code
  und
> raumFuerNotizen.txt  // Eine Text-Datei
 
Ein erster Eintrag in raumFuerNotizen.txt könnte z. B. sein:

> *Der Zugang zu Computern und allem, was einem zeigen kann, wie diese Welt funktioniert, sollte unbegrenzt und vollständig sein.
> *Alle Informationen müssen frei sein.

Mit der Datei beispielProgramm.c befassen wir uns im nächsten Abschnitt.

- [x] Ordner angelegt
- [x] Datei angelegt
- [ ] Programm geschrieben und gespeichert
- [ ] Programm abgearbeitet
- [ ] Programm debugt


### Programm schreiben und speichern

Wir begeben uns in unsere neu angelegte Datei beispielProgramm.c

und fügen folgenden Text ein:

> 
>
> 
>
> 
>     
>     
>     /*Ein Programm ohne höheres Ziel. Wir wollen nur VSCode kennenlernen und den Debugger ausprobieren*/
>     
>     #include <stdio.h>
>     
>     int main(){
>       int iSchub = 1000;      //wir legen eine Variable Namens iSchub an und weisen ihr den Wert 1000 zu
>       printf("Three!\n");     //Beginn eines kurzen Countdowns
>       iSchub = 2000;          //vorm Abarbeiten dieser Zeile hat iSchub weiter den Wert 1000
>       printf("Two!\n");       //jetzt ist der Wert 2000
>       iSchub = 3000;          //Two! steht irgendwo auf dem Bildschirm
>       printf("One!\n");
>       iSchub = 4000;
>       printf("Lift off!\n");
> 
>     return 0;
>     }

Bei einem Blick an den oberen Bildschirmrand sehen wir neben dem Namen unserer Datei einen weißen (bei Standardfarbeinstellungen) Kreis. Dies bedeutet, dass es nicht gespeicherte Änderungen gibt.

Durch das Betätigen von [command] + [s] (MacOS) bzw. [strg] + [s] speichern wir unsere Arbeit und sehen, dass sich der Kreis in ein X verwandelt.

- [x] Ordner angelegt
- [x] Datei angelegt
- [x] Programm geschrieben und gespeichert
- [ ] Programm abgearbeitet
- [ ] Programm debugt


### Programm abarbeiten

Das ist der Zeitpunkt, an dem wir die Früchte unserer harten Arbeit ernten. Wir arbeiten unser neues Programm ab. Wie das geht haben wir schon bei der Installation gelernt.

Dies ist der erwartete Output:

> Three!
> 
> Two!
>
> One!
>
> Lift off!
>

Mit allem was davor steht brauchen wir uns nicht aufzuhalten.

<details>
  
<summary>Aber ich *muss* wissen, was da passiert!</summary>  
Kein Problem, so kompliziert ist das gar nicht.

VSCode lässt uns einfach nur wissen, was es getan hat.

So sieht der Output bei mir aus:

> cd "/Users/username/vscodeforc/Projekte/ProgrammierspracheC/" && gcc helloWorld.c -o helloWorld && "/Users/username/vscodeforc/Projekte/ProgrammierspracheC/"helloWorld

Auf Windows wird das im Zweifelsfall mit c: losgehen und die / sind \, aber das Prinzip ist das gleiche.

Hätten wir genau das in die Kommandozeile getippt und auf Enter gedrückt, hätten wir auch unser Programm abgearbeitet, nur mit viel Tipperei vorweg.


`<&&>`kann man einfach als "danach tu noch:" lesen.

Wir haben da also

> cd "/Users/username/vscodeforc/Projekte/ProgrammierspracheC/"

danach tu noch:

> gcc helloWorld.c -o helloWorld

danach tu noch:

> "/Users/username/vscodeforc/Projekte/ProgrammierspracheC/"helloWorld

Der erste der drei Befehle ist cd "Pfadname", wobei cd für change directory, also "wechlse Verzeichnis" steht. 

gcc ist der Befehl mit dem wir unseren "C-Umwandler" bitten, sich an die Arbeit zu machen und aus unserem Quellcode in beispielProgramm.c eine ausführbare Datei zu machen. -o ist kurz für Output und signalisiert dem "C-Umwandler", dass die ausführbare Datei "beispielProgramm" heißen soll. Unter Windows wäre das "beispielProgramm.exe"

Die letze Zeile ruft dann einfach unsere gerade kreierte ausführbare Datei auf, was dazu führt, dass wir deren Output auf den Monitor bekommen.

</details>

- [x] Ordner angelegt
- [x] Datei angelegt
- [x] Programm geschrieben und gespeichert
- [x] Programm abgearbeitet
- [ ] Programm debugt


### Programm debuggen

Zum Debugger gelangen wir z.B., indem wir links auf das Symbol mit Play-Button und Käfer ([Bug](https://de.wikipedia.org/wiki/Programmfehler)) klicken.
Indem wir links neben die Zeilennummern klicken, können wir sogenannte Breakpoints einfügen, die sich durch rote Punkte zu erkennen geben, und wollen dies auch großzügig wie im gezeigten Screenshot tun, danach starten wir den Debugger durch Klick auch den grünen Play-Button:

![image](https://user-images.githubusercontent.com/78163337/111460491-5207a980-871c-11eb-85d0-c31a90780bdc.png)


- [x] Ordner angelegt
- [x] Datei angelegt
- [x] Programm geschrieben und gespeichert
- [x] Programm abgearbeitet
- [x] Programm debugt


# Troubleshooting

## Allgemein

### Sonder- oder Leerzeichen irgendwo im Pfad?

Insbesondere, aber nicht nur, bei den Fehlermeldungen

#### File not found

oder

#### No such file or directory

sollte man dies nochmal genau überprüfen.

  Heißt die Datei z. B. Prüfsumme.c?
  Irgendeiner der Ordner, in der sich die Datei schließlich befindet "Übung" oder "Neue Projekte"?
  Ist der Benutzername Ségolène?
  
### Virenscanner?

Bei der Installation, insbesondere dem Herunterladen und Installieren von Chocolatey können übereifrige Virenscanner Probleme machen.

Auch das Aufrufen des Compilers oder -noch öfter- des Debuggers kann Virenscanner irritieren.

Der hauseigene Virenscanner von Windows (Defender) ist bisher eher zurückhaltend, bekannt sind Problem mit AntiVir und McAfee.

In diesem Fall kann man das Anti-Virus Programm für einen kurzen Moment ausstellen und es so probieren. Beim Testen von Compiler und Debugger kann man die Internetverbindung vorher trennen.


## Linux

## MacOS

## Windows

### Choco
<details>
<summary>Die Benennung "choco" wurde nicht als Name eines Cmdlet, einer Funktion, einer Skriptdatei oder eines ausführbaren Programms erkannt.</summary>

Entweder wurde chocolatey nicht installiert, das Ende der Installation wurde nicht abgewartet oder die PowerShell Sitzung wurde nach der Installation nicht beendet.

Also einmal PowerShell beenden und (wieder als Administrator) neu öffnen. Wenn das nicht hilft den vorherigen Schritt wiederholen.

</details>

### Existing Chocolatey installation
<details>
<summary>An existing Chocolatey installation was detected. Installation will not continue.
For security reasons, this script will not overwrite existing installations.</summary>


Eine unvollständige Installation von Chocolatey kann man mit folgendem Befehl entfernen:

> Remove-Item C:\ProgramData\chocolatey -Recurse

</details>
