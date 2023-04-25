# MongoDB Kommandon och Instruktioner

Detta dokument innehåller MongoDB-kommandon och instruktioner för att använda i mongo shell och fungerar med MongoDB version 5.0.

## Starta MongoDB-Shell CMD

```
mongo
```

*Beskrivning*: Öppnar mongo shell.

## Kolla MongoDB-Version

```
mongod --version
```

*Beskrivning*: Visar den installerade versionen av MongoDB.

## Kolla vilka databaser som finns

```
mongo
use admin
show dbs
```

*Beskrivning*: Visar en lista över tillgängliga databaser på servern.

## Kolla vilka användare som är skapade

```
mongo
db.getUsers()
```

*Beskrivning*: Visar en lista över alla användare i databasen.

## Kontrollera CompatibilityVersion

```
mongo
db.adminCommand({ getParameter: 1, featureCompatibilityVersion: 1 })
```

*Beskrivning*: Visar nuvarande kompatibilitetsversion för MongoDB.

## Ändra CompatibilityVersion

```
mongo
use admin
db.adminCommand({ setFeatureCompatibilityVersion: "Versionsnumret" })
```

*Exempel*: `db.adminCommand({ setFeatureCompatibilityVersion: "4.0" })`

*Beskrivning*: Ändrar kompatibilitetsversionen för MongoDB till det angivna versionsnumret.

## Logga in med autentisering

```
mongo
use admin
db.auth("adminTfs13", "Lösenordet")
```

*Beskrivning*: Loggar in med den angivna användaren och lösenordet.

## Stoppa MongoDB Server

```
Öppna MongoShell och skriv: db.adminCommand({ shutdown: 1 })
```

*Beskrivning*: Stänger av MongoDB-servern.

## Skapa användare med root-behörighet

```
db.createUser({user: "användarnamn", pwd: "Lösenord", roles: [{role: "root", db: "admin"}]})
```

*Beskrivning*: Skapar en ny användare med root-behörighet för databasen "admin".

## 26. Avsluta mongo shell

```
exit
```

*Beskrivning*: Avslutar mongo shell och återgår till kommandotolken.

## 27. Hjälp

```
help
```

*Beskrivning*: Visar en lista över tillgängliga kommandon och deras beskrivningar i mongo shell.

## 28. Visa nuvarande databas

```javascript
db
```

*Beskrivning*: Visar namnet på den aktuella databasen som du arbetar med i mongo shell.

## 29. Skapa och lägga till ett dokument samtidigt

```javascript
db.<collection_name>.insert({field1: "value1", field2: "value2"})
```

*Beskrivning*: Om samlingen inte finns, skapar den angivna samlingen och lägger till ett nytt dokument i den.

## 30. Uppdatera flera dokument samtidigt

```javascript
db.<collection_name>.updateMany({field1: "value1"}, {$set: {field2: "new_value2"}})
```

*Beskrivning*: Uppdaterar alla dokument som matchar sökkriteriet med de angivna värdena.

## 31. Ta bort flera dokument samtidigt

```javascript
db.<collection_name>.deleteMany({field1: "value1"})
```

*Beskrivning*: Tar bort alla dokument som matchar det angivna sökkriteriet.

## 32. Byta databas

```javascript
use <database_name>
```

*Beskrivning*: Byter till den angivna databasen eller skapar en ny om den inte finns.
