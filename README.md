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
