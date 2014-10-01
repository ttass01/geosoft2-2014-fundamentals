Referat
Geodatenformate
von Simon Schulte und Tobias Tasse


Häufige Schnittstellen:

WMS
WFS
SWE Common

Geodatenformate die,...

...XML basiert sind,

O&M
tagged data
GML
KML
Atom+geo
RSS+geo

...Daten zu Geometrien enthalten,

Shapefiles
Simple Features
GeoPackage

...Bilddaten enthalten,

GeoTIFF
JPEG/GeoJPEG

…und JSON basiert sind.

GeoJSON













Häufige Schnittstellen:


WMS

OpenGIS Wep Map Service (WMS)
definiert vom Open Geospatial Consortium (OGC)
Spezialfall eines Web Services

Exkurs Web Service:
ist eine Softwareanwendung, die über ein Netzwerk für die direkte Maschine-zu-Maschine-Interaktion bereitgestellt wird
jeder Webservice besitzt einen Uniform Resource Identifier (URI), über den er eindeutig identifizierbar ist
besitzt Schnittstellenbeschreibung in maschinenlesbarem Format (XML-Artefakt, meist WSDL), wodurch definiert wird wie mit Webservice zu interagieren ist
Kommunikation läuft meist über Protokolle aus dem Internetkontext wie HTTP und ist XML-basiert
		
Visualisierung von Geodaten in Browser
HTTP-Schnittstelle zum Abrufen von Auszügen aus Landkarten, die von einer oder mehreren geo-räumlichen Datenbanken bereitgestellt werden
die WMS Anfrage definiert den gewünschten Bereich und die geographischen Layer die verarbeitet werden sollen
die Anfrage liefert Kartenmaterial, dass, meist wiedergegeben in Dateiformaten wie JPG, PNG, etc., in einer Browser-Anwendung dargestellt wird

Geodatenformate:
 zur Kommunikation → XML


Quellen und hilfreiche Links:
http://de.wikipedia.org/wiki/Web_Map_Service (letzter Aufruf am 01.10.2014)
http://www.opengeospatial.org/standards/wms (letzter Aufruf am 01.10.2014)
http://de.wikipedia.org/wiki/Webservice (letzter Aufruf am 01.10.2014)
http://de.wikipedia.org/wiki/Open_Geospatial_Consortium (letzter Aufruf am 01.10.2014)















WFS

OpenGIS Web Feature Service (WFS)
definiert vom Open Geospatial Consortium (OGC)
internetgestützter Zugriff auf Geodaten innerhalb eines verteilten GIS
beschränkt sich ausschließlich auf Vektordaten, wie sie in Datenbanken abgelegt werden können
im Rahmen der Spezifikationen des OGC ermöglicht ein WFS den Zugriff auf geographische Features in Datenbanken und gibt Ergebnis mindestens als unabhängiges Dateiformat Geography Markup Language (GML) zurück
Hier:
Feature – allgemeine Abstraktion eines realen Faktums
Feature Type – ist Darstellung mithilfe eines Namens, weiteren Attributen
geographische Feature Types - + Geometrie
Beispiel: Feature Type „Fluss“, Instanz eines Features ist ein konkreter Fluss

Technischer Hintergrund:
HTTP-Anfrage vom Client an WFS gesendet
es gibt sechs Operationen, die von einem Benutzer angefragt werden können;
für uns interessant:
GetCapabilities – liefert XML-Dokument mit allgemeinen Angaben zum Anbieter des WFS, abgefragte Feature Types und mögliche Operationen
GetGmlObject – liefert einzelne Elemente aus der GML-Datei per Xlink

Geodatenformate:
GML
XML

Quellen und hilfreiche Links:
http://de.wikipedia.org/wiki/Web_Feature_Service (letzter Aufruf am 01.10.2014)
http://www.opengeospatial.org/standards/wfs (letzter Aufruf am 01.10.2014)
http://www.weichand.de/2011/11/30/grundlagen-web-feature-service-wfs-2-0/ (letzter Aufruf am 01.10.2014)


















Geodatenformate, die...

...XML basiert sind:


Observations and Measurements (O&M)

OGC und ISO Standard
spezifierzt eine XML-Implementation für das OGC und ISO O&M conceptual model (OGC Observations and Measurements v2.0 und ISO/DIS 19156), inklusive einem Schema für Sampling Features
d.h. es ist ein Standard zur Modellierung von Observationen und zur Beschreibung des Zusammenhangs zwischen dem räumlichen Zielobjekt das observiert wird, der gemessenen „properties & measurement procedure“ und den erfassten Daten, die aus der Observation resultieren
basiert auf Geography Markup Language (GML)
wichtig für Sensor Web Enablement (SWE Framework), SensorML und Sensor Observation Service (SOS)

Quellen und hilfreiche Links:
http://www.opengeospatial.org/standards/om (letzter Aufruf am 01.10.2014)
http://www.ogcnetwork.net/om (letzter Aufruf am 01.10.2014)
http://www.spatineo.com/2012/02/what-is-an-om-observation-and-why-should-you-care/ (letzter Aufruf am 01.10.2014)



























Tagged data

Auszeichnung eines Datenbestandes mit zusätzlichen Informationen
Zu finden in Auszeichnungssprachen wie SGML, HTML oder auch XML
Dateiformate
Ein Tag bezeichnet in der Speicherung von Daten in Dateien eine Meta- oder Zusatzinformation, die der Datei angefügt wird
Beispiele:
ID3-Tag bietet in Musikdateien Informationen über Titel, Genre, etc.
TIFF, wo spezielle Daten zur Georeferenz zusätzlich zu den sichtbaren Rasterdaten in die Bilddatei eingebettet werden
Zur zusätzlichen Auszeichnung von beliebigen Daten, meist Fotos, gibt es Exif

Beispiel:

Aus XML-Beispiel

<Kreditkarte
  Herausgeber="Xema"
  Nummer="1234-5678-9012-3456"
  Deckung="2e+6"
  Waehrung="EURO">
  <Inhaber
    Name="Mustermann"
    Vorname="Max"
    maennlich="true"
    Alter="42"
    Partner="null">
    <Hobbys>
      <Hobby>Reiten</Hobby>
      <Hobby>Golfen</Hobby>
      <Hobby>Lesen</Hobby>
    </Hobbys>
    <Kinder />
  </Inhaber>
</Kreditkarte>
Tags sind hier zum Beispiel <Inhaber></Inhaber> und <Hobbys></Hobbys>.



Quellen und hilfreiche Links:
http://en.wikipedia.org/wiki/Tag_%28metadata%29 (letzter Aufruf am 01.10.2014)

GML

Geography Markup Language (GML)
OGC(Entwickler) und ISO Standard
basierend auf XML
ist eine XML Grammatik, d.h. Text, um geographische Objekte zu beschreiben und auszutauschen
Softwareunabhängiger Austausch von geographischen Informationen (Geometrie und Eigenschaften des Features) zwischen Computersystemen
dient sowohl als Modellierungssprache für Geographische Systeme wie auch als offenes Austauschformat für räumliche Transaktionen über das Internet
generisches Objektmodell, das nicht nur konventionelle Vektordaten oder einfache Objekte beinhaltet, sondern auch multidimensionale Rasterdaten und einige Elemente von Sensordaten
nützlich, weil Fähigkeit, alle Arten von räumlichen Informationen zu integrieren

Warum GML und kein anderer Encoding Standard für geographische Objekte wie etwa COGIF, SAIF, oder Sonstige?

Ist ein einfaches textbasiertes Encoding von geographischen Features
Ist ein OGC und ISO Standard, der weltweit anerkannt ist
basiert auf XML
wichtig weil:
1. XML bietet Methode zum Überprüfen von Datenvollständigkeit/Datenrichtigkeit
2. XML Dokumente können schon von einem einfach Text Editor gelesen und bearbeitet werden
3. XML ist einfach zu transformieren (via XSLT, Java, C++, etc.)

Beispiel:
Schulgebäude

<Feature   fid="142" featureType="school" > 
   <Description>Balmoral Middle School</Description>> 
   <Property Name="NumFloors" type="Integer" value="3"/> 
   <Property Name="NumStudents" type="Integer" value="987"/> 
       <Polygon  name="extent" srsName="epsg:27354"> 
            <LineString  name="extent" srsName="epsg:27354"> 
                <CData> 
                  491888.999999459,5458045.99963358 491904.999999458,5458044.99963358 
                  491908.999999462,5458064.99963358 491924.999999461,5458064.99963358 
                  491925.999999462,5458079.99963359 491977.999999466,5458120.9996336 
                  491953.999999466,5458017.99963357 </CData> 
        </LineString> 
    </Polygon> 
</Feature>
Quellen und hilfreiche Links:
http://www.w3.org/Mobile/posdep/GMLIntroduction.html(Punkt 3.0, letzter Aufruf am 01.10.2014)
http://live.osgeo.org/de/standards/gml_overview.html (letzter Aufruf am 01.10.2014)
KML

Keyhole Markup Language (KML)
.kml, .kmz
Entwickelt von Google Inc. und bekannt geworden durch Google Earth
Erweiterung von XML
Heute OGC Standard 
Auszeichnungssprache zur Beschreibung von Geodaten
Steht für die Visualisierung geographischer Informationen und kann verwendet werden um GML-Inhalte darzustellen
KML-Dokumente können Geodaten sowohl in Vektor- wie auch in Rasterform enthalten
Vektorobjekte (Punkt, Linie, etc.) werden als Placemark-Elemente modelliert
Placemark-Elemente können enthalten: Geometrie, Name, Beschreibung, vordefinierten Stil, Zeitstempel etc.
Luft- und Satellitenbilder werden als GroundOverlay-Elemente modelliert
GroundOverlay-Elemente können ähnliches enthalten, nur anstelle der Geometrie muss ein Koordinatenausschnitt zur Georeferenzierung der Rasterdaten definiert werden

Beispiel:
KML-Code für ein einfaches Placemark:

<?xml version="1.0" encoding="UTF-8"?>
<kml xmlns="http://www.opengis.net/kml/2.2">
  <Placemark>
    <name>Simple placemark</name>
    <description>Attached to the ground. Intelligently places itself 
       at the height of the underlying terrain.</description>
    <Point>
      <coordinates>-122.0822035425683,37.42228990140251,0</coordinates>
    </Point>
  </Placemark>
</kml>



Quellen und hilfreiche Links:
http://de.wikipedia.org/wiki/Geography_Markup_Language (letzter Aufruf am 01.10.2014)
http://de.wikipedia.org/wiki/Keyhole_Markup_Language(letzter Aufruf am 01.10.2014)
https://developers.google.com/kml/documentation/kml_tut?hl=de (Tutorial)(letzter Aufruf am 01.10.2014)
http://www.opengeospatial.org/standards/kml (letzter Aufruf am 01.10.2014)












...Daten zu Geometrien enthalten:


Shapefiles

Dateiformat für Geodaten, dass ursprünglich für die Software ArcView der Firma ESRI entwickelt wurde
heute im Desktop-GIS-Umfeld verbreitet
Support von freien sowie kommerziellen Programmen ist nirgends so gut wie beim Shapefile
Shapefile besteht aus mindestens drei Dateien:
.shp – zur Speicherung der Geometriedaten
.dbf – Sachdaten im dBASE-Format
.shx – Index der Geometrie zur Verknüpfung der Sachdaten (auch Attributdaten)
weitere Dateien: siehe http://de.wikipedia.org/wiki/Shapefile /Aufbau/Optionale Dateien
in einer Shapefile können jeweils nur Elemente eines Typs enthalten sein (Punkt, Linie, Fläche(Polygone) oder Multi-Punkte
es können sowohl 2D als auch 3D Geometrien erfasst werden
Optional kann das Design eines Shapefiles in einer Legendendatei .avl oder .lyr(neuer) gespeichert werden und nach dem Einladen einer Shapefile als Themeneigenschaft hinzugefügt werden
Größe der Shp- und DBF-Dateien darf 2 GB nicht überschreiten

Beispiele zu Shapefiles:
http://www.geofabrik.de/de/data/shapefiles.html (letzter Aufruf am 01.10.2014)
(Beispiele enthalten verschiedene Layer mit Punkten, Linien, Flächen und Multi-Punkten)


Quellen und hilfreiche Links:
http://de.wikipedia.org/wiki/Shapefile (letzter Aufruf am 01.10.2014)





















...Bilddaten enthalten:


GeoTIFF

.geotiff oder auch nur .tif
Spezialform eines TIFF-Bildes
Open Standard
Entwickelt von Aldus Corporation
Datenformat zur Speicherung und zum Austausch von Bilddaten
Durch verlustfreie Speicherung, eignet sich das TIF-Format gut zur Verarbeitung von geographischen Daten, da es bei Satelliten- und Luftbildern bzw. anderen Rasterdaten oft auf hohe Abbildungsgenauigkeit ankommt
Sinnvoll für Bilder bzw. Rasterdaten mit hoher Abbildungsgenauigkeit
Unterschied zu normalen TIF-Format ist, dass spezielle Daten zur Georeferenz zusätzlich zu den sichtbaren Rasterdaten in die Bilddatei eingebettet werden
Datei enthält spezifische Angaben über das Koordinatenreferenzsystem
Informationen werden im Vergleich zu GeoJPEG nicht in externer World File Datei gespeichert, sondern direkt in den Metatags des Bildes
GeoJPEG:
Ist ein georeferenziertes JPEG

Beispiel:
Es erlaubt, etwa bei Kartenbildern, Luftbildern und ähnlicen Informationen, anzugeben, wo auf der Erde die im Bild dargestellte Situation exakt koordinatenbezogen liegt.

Katalog von Beispiel GeoTIFF Bildern:
http://www.landesvermessung.sachsen.de/inhalt/produkte/lika/alk/alk_download.html (letzter Aufruf am 01.10.2014)


Quellen und hilfreiche Links:
http://de.wikipedia.org/wiki/GeoTIFF (letzter Aufruf am 01.10.2014)
http://de.wikipedia.org/wiki/Tagged_Image_File_Format (letzter Aufruf am 01.10.2014)
 

















…und JSON basiert sind:


GeoJSON

open standard (für jeden kostenlos zugänglich und nutzbar)
GIS File Format
.json, .geojson
größter Unterschied zu anderen GIS Standards ist, dass es kein formaler Standard einer Organisation ist, sondern von einer Gruppe von Entwicklern geschrieben wurde
zum Kodieren von einfachen geographischen Featuren oder auch von Feature Collections
GeoJSON besteht immer aus einem Objekt
dieses repräsentiert:
Geometrie – Punkt, Linie, Polygon, MultiPunkt, MultiLinie oder MultiPolygon
Feature – enthält Geometrie + Properties
Feature Collection Objects – enthält mehrere Features

Beispiel:
Feature Collection
{
  "type": "FeatureCollection",
  "features": [
    {
      "type": "Feature",
      "geometry": {
        "type": "Point",
        "coordinates": [102.0, 0.6]
      },
      "properties": {
        "prop0": "value0"
      }
    },
    {
      "type": "Feature",
      "geometry": {
        "type": "LineString",
        "coordinates": [
          [102.0, 0.0], [103.0, 1.0], [104.0, 0.0], [105.0, 1.0]
        ]
      },
      "properties": {
        "prop1": 0.0,
        "prop0": "value0"
      }
    },
    {
      "type": "Feature",
      "geometry": {
        "type": "Polygon",
        "coordinates": [
          [
            [100.0, 0.0], [101.0, 0.0], [101.0, 1.0], [100.0, 1.0],
            [100.0, 0.0]
          ]
        ]
      },
      "properties": {
        "prop1": {
          "this": "that"
        },
        "prop0": "value0"
      }
    }
  ]
}


nutzt JavaScript Object Notation (JSON); ist eine Erweiterung dessen

JSON ist ein kompaktes Datenformat in einer einfach lesbaren Textform zum Zweck des Datenaustausches zwischen Anwendungen
Programmiersprachen unabhängig
Ersatz für XML in Bereichen, wo Ressourcen (Speicherplatz, CPU-Leistung) sparsam eingesetzt werden sollen
Beispiel: Bei der Entwicklung von desktopähnlichen Webanwendungen

Unterschied zu XML:
Syntax von JSON ist einfacher gestaltet und erscheint daher oft lesbarer + leichter schreibbar
XML ist eine Auszeichnungssprache (Gliederung und Formatierung von Texten und anderen Daten) und somit vielseitiger einsetztbar als JSON, das ein Datenaustauschformat ist


JSON-Code:

{
  "Herausgeber": "Xema",
  "Nummer": "1234-5678-9012-3456",
  "Deckung": 2e+6,
  "Waehrung": "EURO",
  "Inhaber": {
    "Name": "Mustermann",
    "Vorname": "Max",
    "maennlich": true,
    "Hobbys": [ "Reiten", "Golfen", "Lesen" ],
    "Alter": 42,
    "Kinder": [],
    "Partner": null
  }
}
XML-Code:

<Kreditkarte
  Herausgeber="Xema"
  Nummer="1234-5678-9012-3456"
  Deckung="2e+6"
  Waehrung="EURO">
  <Inhaber
    Name="Mustermann"
    Vorname="Max"
    maennlich="true"
    Alter="42"
    Partner="null">
    <Hobbys>
      <Hobby>Reiten</Hobby>
      <Hobby>Golfen</Hobby>
      <Hobby>Lesen</Hobby>
    </Hobbys>
    <Kinder />
  </Inhaber>
</Kreditkarte>


Quellen und hilfreiche Links:
http://en.wikipedia.org/wiki/GeoJSON (letzter Aufruf am 01.10.2014)
http://geojson.org/geojson-spec.html (letzter Aufruf am 01.10.2014)
http://de.wikipedia.org/wiki/JavaScript_Object_Notation (letzter Aufruf am 01.10.2014)
http://de.wikipedia.org/wiki/Auszeichnungssprache (letzter Aufruf am 01.10.2014)
