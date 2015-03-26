# VersaCommerce Theme Boilerplate

Ein einfaches Theme für [VersaCommerce](https://versacommerce.de). Es kann als Einstiegspunkt
für eigene Themes verwendet werden

## Theme Organization

### /assets

Dieser Ordner enthält alle statischen Inhalte, wie Bilder, Stylesheets und Javascript. 
In diesem Fall sind die Dateien aber nicht in Unterordnern, da es bei der geringen Menge an Dateien übersichtlicher ist.

Wenn man assets verwendet, sollte man immer den ['asset_url'-Filter](http://developer.versacommerce.de/themes/filter/url/#asseturl) anwenden!

#### Beispiel

```html
<link rel="stylesheet" href="{{ 'shop.css' | asset_url }}">
<script src="{{ 'shop.js' | asset_url }}"></script>
<img src="{{ 'logo.png' | asset_url }}">
```

### /config

Hier wird das Layout für den Konfigurator in der settings.html hinterlegt. Außerdem liegen hier auch die Festgelegten Voreinstellungen für das Theme in der settings_data.json.

### /include

Das ist der Ort an dem Partials (Teile einer Seite) hinterlegt werden, die mehrfach Verwendet werden. Partials bindet man mit der ['include'-Anweisung](http://developer.versacommerce.de/themes/einfache-befehle/include/#include) ein.

#### Beispiel

```liquid
{% include 'navbar-items' %}
```

### /layout

Hier wird die Layout-Datei für die Shop-Seiten hinterlegt: Die theme.html

In der theme.html sollten Header- und Footerinformationen enthalten sein.

Des Weiteren werden hier auch weitere Layouts, wie zum Beispiel für Emails, hinterlegt.

### /templates

Für jeden Bereich des Shops wird hier ein eigenes Template hinterlegt. Für ein Funktionierendes Theme müssen mindestens folgende Dateien vorhanden sein:

* /templates/index.html
* /templates/collection.html
* /templates/product.html
* /templates/page.html
* /templates/cart.html

#### Startseite

Die Startseite wird durch die index.html repräsentiert. Hier kann beispielsweise eine Produktgruppe mit den aktuellen Tagesangeboten aufgelistet sein.

#### Produktgruppe

Die collection.html zeigt die Inhalte einer Produktgruppe. Auch die Suchergebnisse werden über dieses Template dargestellt.

#### Produkt

Produkte finden ihre Darstellung in der product.html. Hier sollte man darauf achten, dass alle wichtigen Angaben über ein Produkt hier enthalten sind.

* Artikelnummer, Hersteller, Kategorie, Tags
* Anzeige ob ein Produkt Neu und/oder Top ist
* Titel und Untertitel des Produkts
* Produktbeschreibung
* Bilder des Produkts
* Preis, Streichpreis und Grundpreis­berechnung
* »In den Warenkorb«-Button
* Gesonderte Versandkosten (z.B. Lieferung per Spedition)
* Auskunft, ob das Produkt verfügbar ist oder nicht
* Empfehlungen (Produkt, Empfehlungstext)
* Produktvarianten

#### Statische Seiten

Über die page.html werden Seiten mit statischem Inhalt ausgegeben. Dazu zählen zum Beispiel die AGB-Seite, Informationen über den Versand oder das Impressum.

#### Warenkorb

Einem Shop darf der Warenkorb nicht fehlen. Mit der cart.html baut man sich seinen eigenen Warenkorb zusammen.

Auch hier gibt es einige Punkte, die vorhanden sein sollten um dem Kunden das Einkaufserlebnis so angenehm wie möglich zu gestalten.

* Produkte im Warenkorb
* Zwischensumme
* Versandgebühren
* Mehrwertsteuer/Umsatzsteuer
* Menge der Position
* Position löschen (als Button)
* Eingabefeld für Gutscheincodes
* Feld für Bemerkungen zur Bestellung
* "Weiter einkaufen"-Link um zur zuletzt besuchten Seite zurückzukommen
* "Jetzt bezahlen"-Button

#### weitere Templates

Mögliche weitere Templates können folgende sein:

* /templates/article.html
* /templates/blog.html
* /templates/list-collections.html

Will man einen Blog in seinen Shop einbinden, so braucht man eine article.html und blog.html. Um die Artikel eines Blogs darzustellen, braucht man die blog.html. Die article.html dient dann dazu, einen einzelnen Artikel darzustellen.

Die list-collections.html kann dazu verwendet werden, alle Produktgruppen aufzulisten.

Weiter Informationen zum Verzeichnisaufbau gibt es bei [developer.versacommerce.de](http://developer.versacommerce.de/guides/eigenes-theme-erstellen/#der-verzeichnis-aufbau)
