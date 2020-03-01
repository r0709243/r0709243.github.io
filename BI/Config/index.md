---
layout: default
title: Grafana Configureren 
author: Lance T.

---

{% include nav-breadcrumbs.html %}

## Configuratie Grafana

Voordat u alle functionaliteiten van Grafana kunt gebruiken in de applicatie, moeten nog enkele configuraties aangepast worden.

Deze instellingen dienen aangemaakt te worden in de configuratiefile van Grafana. Deze kunt u vinden op de plaats waar u Grafana geïnstalleerd hebt. Deze file heeft als extensie ```.ini```.

Hieronder vindt u de instellingen die veranderd moeten worden.

### Auth.anonymous

enabled false --> veranderen naar 'enabled true'

### Auth.Proxy

enabled false --> veranderen naar 'enabled true'

### Security

allow_embedding false --> veranderen naar 'allow_embedding true'

U kan controleren of de instellingen juist zijn aangepast door in de webinterface van Grafana naar het volgende te gaan: 'server admin -> settings'. Hier zult u een lijst vinden van alle settings en configuraties van Grafana.

_de webinterface bereikt u in uw browser via 'http://host-ip:3000'_

![Grafana_settings](/{{site.RepoName}}/media/bi/grafana-settings.png)

## Datasource instellen

Voordat u begint te werken met uw eigen database, moet u het juiste pad instellen zodat de applicatie verbinding kan maken met de gemeten data.

Dit kan onder het menu 'Configuration -> Data Sources'. Hier maakt u een nieuwe datasource.

Bij 'MySQL Connection' vul je het volgende in: 
```
Host: ip adres van de database
Database: naam van de database
User: gebruikersnaam om in te loggen
Paswoord: paswoord van deze gebruiker
```

## Visualisatie maken

Eerst klikt u in het menu p het + icoontje. Vervolgens kiest u voor 'new dashboard'. Om een grafiek toe te voegen, klikt u bovenaan de pagina op 'add panel' ![Grafana-add](/{{site.RepoName}}/media/bi/grafana-add.png)

Een nieuw paneel zal verschijnen. Wanneer u op 'choose visualisation' klikt, kunt u de keuze maken tussen een reeks grafieken om uw data te tonen. Als u deze selecteert, zullen er allerlei opties verschijnen om de grafiek verder te personaliseren.

Als u met uw eigen data source wilt werken, moet u op het linkse icoontje klikken:
![Grafana-icoon](/{{site.RepoName}}/media/bi/grafana-icoon.png)
Vervolgens kiest u in het Query veld in de drop down list de data source die je net aangemaakt hebt.

De app zal er als volgt uitzien:

![Grafana-query](/{{site.RepoName}}/media/bi/grafana-query.png)

Je kan deze blokken slepen en toevoegen om zo het achterliggende SQL-script aan te passen. In het project hebben we ervoor gekozen om dit zelf te schrijven. Dit kunt u doen door onderaan op de blok 'Edit SQL' te klikken. Nu kunt u aan de hand van SQL queries de grafiek aanpassen. Bijvoorbeeld:

![Grafana-sql](/{{site.RepoName}}/media/bi/grafana-sql.png)

Verder op de knop van general kunt u de naam en descriptie van deze grafiek aanpassen.

![Grafana-general](/{{site.RepoName}}/media/bi/grafana-general.png)

Wanneer je een paneel toevoegt of bewerkt, is het altijd belangrijk om alles op te slaan door rechtsboven de pagina op het volgende icoon te klikken: 
![Grafana-opslaan](/{{site.RepoName}}/media/bi/grafana-opslaan.png)

Ten slotte kunt u ook nog het tijdslot kiezen vanaf wanneer je data wilt zien. Alle data dat buiten dit slot valt, zal niet getoond worden.
![Grafana-tijdslot](/{{site.RepoName}}/media/bi/grafana-tijdslot.png)

## Panelen exporteren naar website

We hebben voor ons project bewust gekozen voor Grafana omdat deze het zeer eenvoudig maakt om uw visualisaties te exporteren. Wanneer je op de titel van een paneel klikt, zal een menu tevoorschijn komen. Hier kiest u voor 'share':
![Grafana-share](/{{site.RepoName}}/media/bi/grafana-share.png)

Er zal een nieuw venster te zien zijn met verschillende opties om het paneel te delen. Kies hier bovenaan voor de optie 'embed'. De code die tevoorschijn komt, kan rechtstreeks in het html-gedeelte van de website gekopieerd worden zoals hieronder getoond. De huidige instellingen van dit paneel zullen allemaal mee overgedragen worden naar het paneel in de web applicatie. Het zal dus ook updaten om dezelfde ingestelde intervallen.
![Grafana-delen](/{{site.RepoName}}/media/bi/grafana-delen.png)

![Grafana-web](/{{site.RepoName}}/media/bi/grafana-web.png)









{% include footer.html %}
