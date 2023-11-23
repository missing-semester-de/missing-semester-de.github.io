---
layout: lecture
title: "Automatisierung"
presenter: Jose
video:
  aspect: 56.25
  id: BaLlAaHz-1k
---

Manchmal schreibst du ein Bash-Skript das etwas für dich tut, du möchtest allerdings, dass dies regelmäßig passiert - z.B. ein Backup.
Natürlich könntest du eine *ad hoc* Lösung schreiben, die die ganze Zeit im Hintergrund läuft und abundzu Aufgaben ausführst, allerdings können die meisten UNIX-Systeme dich hier unterstützen, denn sie kommen von Haus aus mit dem sogenannten cron deamon, welcher Aufgaben mit einer Genauigkeit von bis zu einer Minute regelmäßig ausführen kann.

Auf den meisten UNIX-Systemen läuft bereits der cron deamon, `crond` dieser läuft bereits ohne weiteres zutun, um dies zu überprüfen führe den folgenden Befehl aus `ps aux | grep crond`.

## Der crontab

Die Konfigurationsdatei für den cron deamon kann man sich anzeigen lassen, indem man folgenden Befehl ausführt: `crontab -l` bearbeiten kann man diese Datei mit dem Befehl: `crontab -e` Das Zeitformat das der cron deamon nutzt hat fünf verschiedene Zeitfelder und zusätzlich dem Befehl, der ausgeführt werden soll.

- **Minute** -  An welcher Minute einer Stunde dieser Befehl ausgeführt werden soll. Die Zahl kann zwischen '0' und '59' sein.
- **Stunde** -  An welcher Stunde dieser Befehl ausgeführt werden soll. Dabei benutzt der cron deamon das 24-Stunden-Format, also kann dieser Wert zwischen '0' und '23' sein (dabei ist 0 Mitternacht).
- **Tag des Monats** - This is the Day of Month, that you want the command run on, e.g. to
     run a command on the 19th of each month, the dom would be 19.
- **Monat** -   This is the month a specified command will run on, it may be specified
     numerically (0-12), or as the name of the month (e.g. May)
- **Tag der Woche** - This is the Day of Week that you want a command to be run on, it can
     also be numeric (0-7) or as the name of the day (e.g. sun).
- **Benutzer** -    This is the user who runs the command.
- **Kommando** - This is the command that you want run. This field may contain
     multiple words or spaces.

Note that using an asterisk `*` means all and using an asterisk followed by a slash and number means every nth value. So `*/5` means every five. Some examples are

```shell
*/5   *    *   *   *       # Alle fünf Minuten
  0   *    *   *   *       # Jede volle Stunde
  0   9    *   *   *       # Jeden Tag um 9 Uhr
  0   9-17 *   *   *       # Jede Stunde zwischen 9:00 Uhr und 17:00 Uhr
  0   0    *   *   5       # Jeden Freitag um 00:00 Uhr
  0   0    1   */2 *       # Jeden zweiten Monat, am Monatsersten, um 00:00 Uhr
```
Viele weitere Beispiele für häufige crontab Zeitpläne findest du unter [crontab.guru](https://crontab.guru/examples.html)

## Shell-Umgebung und Protokollierung

Ein häufiger Fallstrick beim verwenden von cron ist das es nicht die gleichen Umgebungsskripte lädt, wie es gewöhnliche Shells tun, wie z.B.`.bashrc`, `.zshrc`, &c und dabei nicht die Ausgaben loggt. In Kombination mit der maximalen Frequenz von einer Minute kann es anfangs recht mühsam werden, Cronscripts zu debuggen.

To deal with the environment, make sure that you use absolute paths in all your scripts and modify your environment variables such as `PATH` so the script can run successfully. To simplify logging, a good recommendation is to write your crontab in a format like this


```shell
* * * * *   user  /path/to/cronscripts/every_minute.sh >> /tmp/cron_every_minute.log 2>&1
```

And write the script in a separate file. Remember that `>>` appends to the file and that `2>&1` redirects `stderr` to `stdout` (you might to want keep them separate though).

## Anacron

One caveat of using cron is that if the computer is powered off or asleep when the cron script should run then it is not executed. For frequent tasks this might be fine, but if a task runs less often, you may want to ensure that it is executed. [anacron](https://linux.die.net/man/8/anacron) works similar to `cron` except that the frequency is specified in days. Unlike cron, it does not assume that the machine is running continuously. Hence, it can be used on machines that aren't running 24 hours a day, to control regular jobs as daily, weekly, and monthly jobs.


## Übung
1. Schreibe ein Skript, dass jede Minute in deinen Downloads-Ordner schaut und für jede Datei, die ein Bild ist (als Tipp schaue mal unter [MIME Typen](https://developer.mozilla.org/en-US/docs/Web/HTTP/Basics_of_HTTP/MIME_types) oder nutze einen RegEx, um Dateiendungen zu matchen) und diese in deinen Bilderordner verschiebt.

2. Schreibe ein Cron-Skript, um wöchentlich nach veralteten Paketen in deinem System zu schauen und dich dazu auffordert diese zu aktualiseren oder diese automatisiert aktualisiert.



{% comment %}

- [fswatch](https://github.com/emcrisostomo/fswatch)
- GUI automation (pyautogui) [Automating the boring stuff Chapter 18](https://automatetheboringstuff.com/chapter18/)
- Ansible/puppet/chef

- https://xkcd.com/1205/
- https://xkcd.com/1319/

{% endcomment %}
