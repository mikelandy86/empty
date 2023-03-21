# empty

Viktiga punkter att tänka på vid uppgradering till Azure DevOps Server 2022

Uppgraderingskompatibilitet: Se till att din nuvarande TFS-installation är kompatibel för direkt uppgradering till Azure DevOps Server 2022 (stöds från Azure DevOps Server 2019 eller Team Foundation Server 2015 eller nyare).

Warehouse och Analysis Service: Var medveten om att Warehouse och Analysis Service har tagits bort i Azure DevOps Server 2022 och ersatts av Analytics för rapportering. Planera för eventuell migration till Analytics om det behövs.

Installera patchar: Se till att installera de senaste patcharna för Azure DevOps Server 2022, inklusive Patch 1 och Patch 2, för att säkerställa att din installation är uppdaterad och säker.

Anpassa SSH RSA-algoritmer: Om du har implementerat en lösning för SSH RSA-algoritmer i din .ssh/config-fil, se till att ta bort eller ändra PubkeyAcceptedTypes för att använda RSA-SHA2-256, RSA-SHA2-512 eller båda.

Förbered för nya funktioner: Utforska och förstå de nya funktionerna i Azure DevOps Server 2022, såsom Delivery Plans, förbättrade kontroller för miljövariabler i pipelines, och uppdaterade TFVC-sidor, för att maximera nyttan av din uppdaterade installation.

Genom att vara medveten om dessa viktiga punkter kan du säkerställa en smidig övergång och framgångsrik uppgradering till Azure DevOps Server 2022.
