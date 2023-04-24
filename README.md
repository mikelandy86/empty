För att ta bort autentiseringen och förbereda för nedgradering av MongoDB, följ dessa steg:

1. Öppna MongoDB Shell genom att öppna cmd som administratör och skriv `mongo`.
2. Skriv `use admin`.
3. Autentisera med `db.auth("användarnamn", "lösenord")`.
4. Ta bort användaren med `db.dropUser("användarnamn")`.

Efter att ha tagit bort användaren i MongoDB, stoppa MongoDB-servern genom att skriva `db.shutdownServer()`.

Följ sedan dessa steg för att uppdatera anslutningssträngen i Modern Requirements web.config-fil:

1. Hitta web.config-filen på denna sökväg: `C:/Blablabla/gblals`.
2. Dekryptera filen genom att navigera till följande mapp i cmd: `C:/7feieibg/geugeg`.
3. Skriv följande kommando: `AspNET DECRUPTSFAS`.
4. Öppna web.config-filen och ändra anslutningssträngen till detta: `mongodb string connecitonsas`.

Gör sedan följande ändringar i MongoDB:s config-fil:

1. Hitta config-filen på angiven sökväg.
2. Ta bort raden: `Autensigering enabledgag`.

Starta MongoDB-servern igen genom att använda tjänster (services).

Kontrollera att MR4DevOps-funktionerna fungerar i ADO och därefter kan du påbörja nedgraderingsprocessen enligt dokumentationen.
