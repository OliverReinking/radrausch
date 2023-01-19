# Das Fahrradgeschäft RadRausch

## Buch **Business Intelligence - Eine Einführung**

Die in diesem Repository hinterlegten Daten und Bilder werden im Buch **Business Intelligence - Eine Einführung** von Oliver Reinking ausführlich beschrieben. 

![Buchcover](/public/images/cover/Business_Intelligence_Cover.jpg)

## RadRausch

Das Fahrradgeschäft RadRausch hat drei Shops in München, Hamburg und Berlin.
Die Geschäftsleitung hat folgende Fragen:
- wie war die Umsatzentwicklung in den letzten 5 Jahren?
- wie war die Umsatzentwicklung der drei Shops in den letzten fünf Jahren?
- wie hat sich der Umsatz auf die beiden Produktgruppen Fahrräder und Fahrradzubehör verteilt?
- wie war der Umsatz der Produktgruppe Fahrräder bezüglich
  - der Hersteller?
  - der Farbe des verkauften Fahrrades?

### Das ER-Modell

![ER-Modell](/public/images/screenshots/Datenmodell.jpg)

#### Die Faktentabelle "Verkauf"

Die Faktentabelle "Verkauf" findest du im Verzeichnis datawarehouse unter dem Namen fact_sales.csv.  

Unser Fahrradgeschäft RadRausch besitzt eine Faktentabelle1 mit folgenden Informationen:
- Verkaufsdatum
- Verweis auf das verkaufte Produkt
- Anzahl des verkauften Produktes
- Verweis auf den Käufer (Kunde)
- Verweis auf den Verkaufsort (Shop)
- Preis ohne Mehrwertsteuer
- Preis mit Mehrwertsteuer

Unsere Faktentabelle hat also Verweise auf vier Dimensionstabellen, die jetzt vorgestellt werden.

#### Die Dimensionstabelle "Produkt"

Unsere Dimensionstabelle Produkt besitzt folgende Informationen:
- Name
- Hersteller
- Modell
- Größe
- Farbe
- Typ
- Nettopreis in Euro
- Mehrwertsteuer in Prozent

Du findest die Daten im Verzeichnis datawarehouse unter dem Namen dim_products.csv

#### Die Dimensionstabelle "Kunden"

Die Dimensionstabelle Kunde besitzt folgende Informationen:
- Name
- Mailadresse
- Postleitzahl

Du findest die Daten im Verzeichnis datawarehouse unter dem Namen dim_customers.csv

#### Die Dimensionstabelle "Shop"

Die Dimensionstabelle Shop besitzt folgende Informationen:
- Name des Shops
- Stadt
- Postleitzahl
- Adresse

Du findest die Daten im Verzeichnis datawarehouse unter dem Namen dim_shops.csv

#### Die Dimensionstabelle "Zeit"

Die Dimensionstabelle Zeit besitzt folgende Informationen:

- date
  - 2018-01-01
- monthly_value
  - 1
    - Monat als Zahl (1,...,12)
- quartely_value
  - 1
    - Quartal als Zahl (1,...,4)
- yearly_value
  - 2018
    - Jahr als Zahl
- quarter_id
  - 2018001
    - Jahr x 1000 + Quartal
- month_id
  - 2018001
    - Jahr x 1000 + Monat
- month
  - Januar
    - Monat als Wort
- quarter_year_name
  - 1 Qu 2018
- month_year_name
  - Jan 2018

Du findest die Daten im Verzeichnis datawarehouse unter dem Namen dim_times.csv

### Power BI

#### 1. Screenshot

Die ersten beiden Tabellen wurden in Power BI importiert.    
![ER-Modell](/public/images/screenshots/PowerBI_Screenshot_001.png)

#### 2. Screenshot

Das Datenmodell für unser Fahrradgeschäft in Power BI.  
![ER-Modell](/public/images/screenshots/PowerBI_Screenshot_002.png)


#### 3. Screenshot

Wie war die Umsatzentwicklung in den letzten 5 Jahren?   
![ER-Modell](/public/images/screenshots/PowerBI_Screenshot_003.png)

#### 4. Screenshot

Wie war die Umsatzentwicklung der drei Shops in den letzten fünf Jahren?   
![ER-Modell](/public/images/screenshots/PowerBI_Screenshot_004.png)


#### 5. Screenshot

Wie hat sich der Umsatz auf die beiden Produktgruppen Fahrräder und Fahrradzubehör verteilt? 
![ER-Modell](/public/images/screenshots/PowerBI_Screenshot_005.png)

#### 6. Screenshot

Wie war der Umsatz der Produktgruppe Fahrrad bezüglich der Hersteller? 
![ER-Modell](/public/images/screenshots/PowerBI_Screenshot_006.png)

#### 7. Screenshot

Wie war der Umsatz der Produktgruppe Fahrrad bezüglich der Farben? 
![ER-Modell](/public/images/screenshots/PowerBI_Screenshot_007.png)

#### Die Power BI Lösung

Im Verzeichnis PowerBI_Analyse.pbix findest du die von mir entwickelte Lösung für das Fahrradgeschäft **RadRausch**. 
Du kannst dir gerne diese Datei und auch die Dateien aus dem Verzeichnis datawarehouse herunterladen.

Allerdings musst du folgendes beachten: Wenn du diese Dateien auf deinen Computer herunterlädst, funktioniert die Verknüpfung der fünf importierten CSV-Dateien nicht mehr.   
Um diese Pfade zu aktualisieren klicke in der Anwendung Power BI in der Menüleiste auf File und dann auf Options an settings und hier schließlich auf Data Source Settings.  
Hier kannst du jetzt die Pfade der fünf CSV-Dateien anpassen.



