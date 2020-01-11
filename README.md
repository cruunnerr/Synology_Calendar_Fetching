# Synology_Calendar_Fetching
HowTo fetch *.ics File from WebCal


1. Über das Webinterface auf den Kalender der Synology zugreifen.
2. Rechts das DropDown Menu vom gewünschten Kalender aufrufen und auf "CalDav-Konto" klicken
3. Aus dem "Thunderbird"-Link den letzten Teil hinter dem Benutzernamen kopieren

Befehl lautet dann:

wget --user=user --password="passwort" https://server_url:PORT/caldav/USER/KOPIERTER_TEIL?export && cp KOPIERTER_TEIL?export ics_name.ics && rm KOPIERTER_TEIL?export


# Wichtig: Passwort muss in Anführungszeichen stehen, wenn Sonderzeichen benutzt werden!



Das ganze auf einem Webserver via bash-skript und crontab (als sudo) regelmäßig ausführen.

So kann eine *.ics Datei aus den Kalendern generiert werden und von anderen Diensten (z.B. MagicMirror) genutzt werden.
