## SSH-Verbindung mit Benutzername und Passwort aufbauen

```
ssh [user]@[host]
```

Passwort bei Aufforderung eingeben

## SSH-Ordner im Benutzerverzeichnis anlegen

```
cd ~
mkdir .ssh
```

## SSH-Config anlegen

```
cd .ssh
vi config
```

Inhalt:

```
Host=[host]
User=[user]
```

Anschließend SSH-Verbindung schließen:

```
exit
```
  
## Public-Key übertragen

Public-Key-Datei muss im lokalen Benutzerorder liegen "~/.ssh/id_rsa.pub"

Key mit folgendem Befehl in "authorized_keys"-Datei auf Server einfügen

```
cat ~/.ssh/id_rsa.pub | ssh [user]@[host] "mkdir -p ~/.ssh && cat >> ~/.ssh/authorized_keys"
```

Passwort bei Aufforderung eingeben

## Abschluss

Login sollte jetzt ohne Passwort funktionieren:

```
ssh [user]@[host]
```

Auf die gleiche Art kann man nun auch weitere SSH-Keys hinzufügen, z.B. um Buildtools den Zugriff zu ermöglichen

## Quellen

Anleitung zur Einrichtung der Authentifizierung per SSH Key
http://www.gerritbrands.com/blog/ssh-keys-1and1-hosting
