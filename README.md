# neomutt
Configurartion/Help/Links - goal: work with googlemail

Installation on ArchLinux
Tested on EndeavourOS

## Originator Website
https://neomutt.org/man/neomutt

## Documentation
http://www.mutt.org/doc/manual/

Installiere folgender Programme
```
sudo pacman -S neomutt isync notmuch msmpt
```
Installiere abook
```
git clone https://aur.archlinux.org/abook.git
chmod +w abook
cd abook
sudo make install
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

---
Hilfedatei Macro Befehl umschreiben (anstelle von ```mw -Y``` setze ```mbsync -a```)<br>
```
sudo nano .config/mutt/accounts/deinemail@google.com.muttrc
```
Füge eine neue Zeile hinzu:
***macro index O "<shell-escape>mbsync -a<enter>" "sync deinemail@google.com"***<br>

---
Danach alle Emails einlesen mit dem Befehl
```
mbsync -a
```
Wenn abgeschlossen kann neomutt geöffnet und verwendet werden
```
neomutt
```
