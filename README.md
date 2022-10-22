# neomutt
Configurartion/Help/Links

## Originator Website
https://neomutt.org/man/neomutt

Installiere folgender Programme
```
sudo apt install neomutt curl isync notmuch abook
```
Installiere mutt-wizard
```
git clone https://github.com/lukesmithxyz/mutt-wizard
cd mutt-wizard
sudo make install
```
generiere GPG keypair
```
gpg --full-gen-key
```
wenn abgeschlossen, bilde einen pw container für die email adresse
```
pass init your@gpgpemail.com
```
Einstellung Gmail Account
* 2FA login
* App Passwort erstellen
Account > Sicherheit > "Bei Google Anmelden" > App Passwörter
(neues App Passwort generieren und zwischenspeichern)
---
## Mit mutt-wizard neomutt konfigurieren
```
mw -a deineemail@gmail.com
```
Passwort eingeben (App-Passwort von Gmail)<br>
Passwort bestätigen (App-Passwort von Gmail)<br>
Pop-Up Fenster geht auf: Passphrase aus GPG eingeben<br>
Meldung erscheint:
```
login successful
```
Danach alle Emails einlesen mit dem Befehl
```
mw -y deinemail@gmail.com
```
Wenn abgeschlossen kann neomutt geöffnet und verwendet werden
```
neomutt
```
