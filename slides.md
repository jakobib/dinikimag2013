## Bibliotheken sind mehr als Titeldaten

* Dokumente
* Bibliotheken
* Dienstleistungen
* Nutzer und Nutzerkonten

## Document Service Ontology (DSO)

Welche Arten von Dienstleistungen können von einer Bibliotheken (u.Ä.
Einrichtungen) bezogen auf ein Dokument erbracht werden?

Ausleihe
  ~ http://purl.org/ontology/dso#**Loan**
Ansicht
  ~ http://purl.org/ontology/dso#**Presentation**
Fernleihe (gebend)
  ~ http://purl.org/Ontology/dso#**Interloan**
Verweis auf frei zugängliche Quelle
  ~ http://purl.org/Ontology/dso#**OpenAccess**
Digitalisierung
  ~ http://purl.org/ontology/dso#**Digitization**
Identifizierung
  ~ http://purl.org/ontology/dso#**Identification** (?)
...
  ~ ... (?)

## Simple Service Status Ontology (SSSO)

* Mikro-Ontologie zur Definition von **Service**
* Ein Service ist ein Ereignis mit Provider und Consumer
* Mehrere Service-Status (reserved, provided, executed...)

~~~ {.ditaa .size110}
                                   nextService / previousService
                                              ------
                                             |      |
                                             v      v
   +-----------------+   provided     +--------------------+   consumedBy   +-----------------+
   | ServiceProvider |--------------->|     Service        |--------------->| ServiceConsumer |
   |                 |<---------------|                    |<---------------|                 |
   +-----------------+   providedBy   |   ReservedService  |   consumed     +-----------------+
                                      |   PreparedService  |
                                      |   ProvidedService  |
                                      |   ExecutedService  |
                                      |   RejectedService  |
                                      |                    |
                                      | ServiceFulfillment |
                                      +-----^--------------+
                                            |      ^
                                            |      |
                                             ------
                               dcterms:hasPart / dcterms:partOf
~~~


## Patrons Account Information API (PAIA) Ontology

* Zugriff auf ein Benutzerkonto\
  (Ausleihen, Vormerkungen, Gebühren etc.)
* Bislang nur als API-Spezifikation\
  Ontologie muss noch spezifiziert werden
* Basiert u.A. auf SSSO\
  Eine Ausleihe ist z.B. ein ExecutedService.

## Document Availability Information API (DAIA) Ontology

Aktuelle Verfügbarkeit eines Dienstes für ein Dokument

    [ a bibo:Document ] daia:availableFor [ a dso:Service ] .

    [ a bibo:Document ] daia:unavailableFor [ a dso:Service ] .

Zusätzlich bei Bedarf weitere Details

    $s a dso:Service ;
        daia:limitedBy [ a daia:Limitation ] ;
        daia:delay      $Verzoegerung ;
        daia:expected   $Wartezeit ;
        daia:queue      $Warteschlange ;
        daia:perform    $URLzumLoslegen .

DAIA 1.0 wird noch spezifiziert: <http://gbv.github.com/daiaspec/daia.html>

## Links

Document Service Ontology (DSO)
  ~ <http://gbv.github.com/dso/dso.html>

Simple Service Status Ontology (SSSO)
  ~ <http://purl.org/ontology/ssso> 

Patrons Account Information API (PAIA) Ontology
  ~ <http://purl.org/ontology/paia>

Document Availability Information API (DAIA)
  ~ <http://purl.org/NET/DAIA> bzw. <http://gbv.github.com/daiaspec/daia.html>

Diese Folien unter <https://github.com/jakobib/dinikimag2013> (Quelltext)

