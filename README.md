# KI-Reiseleiter – Offline-Daten

Aufbereitete Kartendaten für die App „KI-Reiseleiter“ (Android). Die App lädt diese Dateien direkt aus den
Releases dieses Repos. Hier liegen nur Daten, kein Programmcode.

## Katalog
`index.json` listet alle Pakete (id, group, name, file, url, size, km2, date, bbox, license); die App liest ihn
und zeigt die Pakete zur Auswahl. Neues Paket: Datei ins Release hochladen, Eintrag ergänzen, `date` erhöhen
zeigt in der App „Update verfügbar“.

## Releases
- **`laser`** – Laser-Oberfläche entlang von Hauptstraßen, Format KRN2 (1-km-Kacheln, 5-m-Raster, einzeln
  gepackt mit Index). Je Zelle: höchster Punkt (Oberfläche) und mittlere Geländehöhe (Boden), in Dezimetern.
  - `nds-at-brenner.krn` – A12 Kufstein–Innsbruck und A13 Innsbruck–Brenner, ±300 m (253 km²)
  - `nds-by-*.krn` – Bayern: Autobahnen sowie Bundesstraßen je Regierungsbezirk, ±300 m
  - `glo-*.krg` – feines Höhenmodell (Copernicus GLO-30, ~30 m) je Land, Format KRG1: Blöcke à 0,1° × 0,1°,
    Höhen in Metern als 2D-Vorhersage-Rest, einzeln gepackt mit Index (Beschreibung in `dem/build_glo.py`
    der App). Eintrag im Katalog mit `"kind": "dem"`.

## Quellen und Lizenzen
- Höhenmodell (`glo-*.krg`): Copernicus DEM GLO-30 – © DLR e.V. 2010–2014 und © Airbus Defence and Space GmbH
  2014–2018, bereitgestellt unter COPERNICUS durch die Europäische Union und ESA; alle Rechte vorbehalten.
  Abgeleitet (auf ganze Meter gerundet, neu gepackt).
- Österreich: Datenquelle: BEV – Bundesamt für Eich- und Vermessungswesen, ALS-DOM/DGM,
  [CC BY 4.0](https://creativecommons.org/licenses/by/4.0/deed.de). Abgeleitet (auf 5 m vergröbert).
- Bayern: Bayerische Vermessungsverwaltung – www.geodaten.bayern.de,
  [CC BY 4.0](https://creativecommons.org/licenses/by/4.0/deed.de). Abgeleitet.
- Weitere Daten (falls hier veröffentlicht): © OpenStreetMap-Mitwirkende, [ODbL](https://opendatacommons.org/licenses/odbl/);
  ESA WorldCover © ESA, CC BY 4.0.

Die aufbereiteten Dateien stehen unter denselben Lizenzen wie ihre Quellen (Namensnennung wie oben).
