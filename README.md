Lösenordskydda MongoDB
======================

En steg-för-steg guide för att lösenordskydda MongoDB-databasen och kryptera "appSettings" i web.config-filen på Modern Requirements Service-webbplatsen.

Steg 1: Stoppa MongoDB-servern
------------------------------

*   Öppna "cmd"-fönstret som administratör.
*   Stoppa MongoDB-servern genom att skriva "mongod --shutdown".

Steg 2: Skapa en användaradministratör
--------------------------------------

*   Öppna en "cmd"-fönster som administratör och kör kommandot "mongod-dbpath="C:\\Program Files\\MongoDB\\db"".
    
*   Öppna en annan "cmd"-fönster som administratör och kör kommandot "mongo".
    
*   Skapa en användaradministratör med följande kommando:
    
    phpCopy code
    
    `db.createUser({   user: "användarnamn",   pwd: "lösenord",   roles: [{role: 'root', db: "admin"}] });`
    

Steg 3: Lägg till säkerhetskonfiguration
----------------------------------------

*   Öppna "mongod.cfg"-filen (C:\\Program Files\\MongoDB\\Server\\3.4).
    
*   Lägg till följande information:
    
    yamlCopy code
    
    `net:   bindip: localhost   port:27017   systemLog:     destination: file     path: C:\Program Files\MongoDB\log\mongod.log   storage:     dbPath: C:\Program Files\MongoDB\db   security:     authorization: enabled`
    

Steg 4: Starta MongoDB-tjänsten
-------------------------------

*   Starta MongoDB-tjänsten genom att öppna "cmd"-fönstret som administratör och skriva "mongod".

Steg 5: Ställ in anslutningsinformationen i web.config-filen
------------------------------------------------------------

*   Öppna "web.config"-filen på Modern Requirements Service-webbplatsen (C:\\Program Files\\Modern Requirements Service) som administratör.
    
*   Ställ in anslutningsinformationen med följande format:
    
    csharpCopy code
    
    `<add key="MongoDB.ConnectionString" value="mongodb://användarnamn:lösenord@localhost:27017"/>`
    

Steg 6: Kryptera "appSettings" i web.config
-------------------------------------------

*   Öppna "Command Prompt" som administratör.
    
*   Gå till C:\\Windows\\Microsoft.NET\\Framework\\v4.0.30319.
    
*   Kör följande kommando för att kryptera "appSettings" i "web.config":
    
    arduinoCopy code
    
    `ASPNET_REGIIS -pef "appSettings" "C:\Program Files\Modern Requirements\Service"`
    
*   Öppna "web.config"-filen och kontrollera att "appSettings" är krypterad.
    

Steg 7: Testa Modern Requirements filerna i ADO
-----------------------------------------------

*   Testa Modern Requirements-filerna i ADO.

Steg 8: Dekryptera "appSettings"
--------------------------------

*   Öppna "Command Prompt" som administratör.
    
*   Gå till C:\\Windows\\Microsoft.NET\\Framework\\v4.0.30319.
    
*   Kör följande kommando för att dekryptera "appSettings":
    
    arduinoCopy code
    
    `ASPNET_REGIIS -pdf "appSettings" "C:\Program Files\Modern Requirements\Service"`
    

Genom att följa dessa steg kan du
