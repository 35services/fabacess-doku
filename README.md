# fabacess-doku
Unser Fabaccess setup

Unter https://github.com/falkorichter/mqtt-learnings dokumentiert Falko Dinge die er über MQTT lernt.

## Kommunikation

> Es gibt einen Matrix-Space und eine Telegram-Gruppe zum Austausch für Interessierte und Projekte, die das System testen wollen.

> Matrix-Space beitreten: [#fabaccess:vow.chat](https://app.element.io/#/room/#fabaccess:vow.chat)

> Telegram-Gruppe beitreten: https://t.me/joinchat/Ly6Y3VODsQAlzHdt2D8RlQ

kopiert von [offene-werkstaetten.org/de/seite/ein-zugangssystem-fuer-offene-werkstaetten](https://www.offene-werkstaetten.org/de/seite/ein-zugangssystem-fuer-offene-werkstaetten)

### 35services intern
* fabaccess[ät]35services[punkt]in-berlin[punkt]de
* [Slack Kanal](https://35services.slack.com/archives/C069XFDTC9G) (intern bei 35services.slack.com)
* [google doc](https://docs.google.com/document/d/1mZ4q9aeXbiIsVolyeHUPPtWCRi8ltKP_bN-eaYpCWPk/edit) ist privat und hat auch passwörter für unser lokales setup

# Zeitstrahl

## 204-05-24 

trying to install fabaccess
```
 git clone https://gitlab.com/fabinfra/fabaccess/dockercompose fabaccess-server
``` 

`docker-compose` fehlt
* https://intux.de/2023/03/03/docker-und-docker-compose-auf-dem-raspberrypi/
* https://fab-access.readthedocs.io/en/v0.3/installation/server_docker.html

folling https://dev.to/elalemanyo/how-to-install-docker-and-docker-compose-on-raspberry-pi-1mo :
confirming
```
groups ${USER}                    
35services : 35services adm dialout cdrom sudo audio video plugdev games users input render netdev spi i2c gpio lpadmin docker
```
install docker-compose:
```
sudo apt-get install libffi-dev libssl-dev
sudo apt install python3-dev
sudo apt-get install -y python3 python3-pip
~~sudo pip3 install docker-compose~~
sudo systemctl enable docker
```

https://dev.to/elalemanyo/how-to-install-docker-and-docker-compose-on-raspberry-pi-1mo hilft auch nur bedingt
`apt install docker-compose` hat funktioniert
reboot



**tried to generate a config:**
```
docker run registry.gitlab.com/fabinfra/fabaccess/bffh:dev-latest --print-default                       
Unable to find image 'registry.gitlab.com/fabinfra/fabaccess/bffh:dev-latest' locally
dev-latest: Pulling from fabinfra/fabaccess/bffh
dc1f00a5d701: Pull complete 
7f489e95c7bd: Pull complete 
Digest: sha256:98f3dccf61f2a8301a2f50705536e9433c1284901113d7e1fc2fcc4106d0c4d0
Status: Downloaded newer image for registry.gitlab.com/fabinfra/fabaccess/bffh:dev-latest
```
with error
```
thread 'main' panicked at 'called `Result::unwrap()` on an `Err` value: Error(Dhall(Error { kind: IO(Os { code: 2, kind: NotFound, message: "No such file or directory" }) }))', bin/bffhd/main.rs:119:76
note: run with `RUST_BACKTRACE=1` environment variable to display a backtrace
thread 'main' panicked at 'called `Result::unwrap()` on an `Err` value: Error(Dhall(Error { kind: IO(Os { code: 2, kind: NotFound, message: "No such file or directory" }) }))', bin/bffhd/main.rs:119:76
note: run with `RUST_BACKTRACE=1` environment variable to display a backtrace
```

### config changes
https://gitlab.com/volkersfreunde/dockercompose habe ich geforkt
``
git remote add falko https://gitlab.com/volkersfreunde/dockercompose.git
git pull falko main
```
mosquito config [versucht zu öffnen](https://gitlab.com/volkersfreunde/dockercompose/-/blob/main/config/mosquitto/mosquitto.conf?ref_type=heads)

### shelly config (offen)
* https://fab-access.readthedocs.io/en/v0.3/usage/setup_steps.html



## 2024-01-08 Falko baut lokal ein MQTT/testsetup
* https://fab-access.readthedocs.io/en/v0.3/installation/server_docker.html
  * erster PR https://gitlab.com/fabinfra/fabaccess/docs/-/merge_requests/6
* Falko hat unter https://github.com/falkorichter/mqtt-learnings/ mal (wieder) ein bisschen `MQTT` und `node-red` bespielt für fabaccess bereit zu sein.


## 2023-12-13 Schulung + Setup
* 16:30 zweite Schulung
* fabaccess[ät]35services[punkt]in-berlin[punkt]de angelegt [admin](https://mailman.35services.in-berlin.de/mailman/listinfo/fabaccess-35services.in-berlin.de)
* Falko hat Damian, Patrick, Billy, Arne, Tobias, Ploenne direkt angefragt

## 2023-12-12 erste Schulung
* Falko war dabei
* Es wird eine Aufzeichnung geben
* Matrix angefragt

## 2023-12-07 Wir sind dabei 
* wir bekommen unsere Zusage - Yipee
* https://www.offene-werkstaetten.org/de/seite/ein-zugangssystem-fuer-offene-werkstaetten
