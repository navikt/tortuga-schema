Avro Schemas
============

Denne modulen inneholder Avro-filer som beskriver hvordan meldingene serialiseres og 
deserialiseres på kafka topicene mellom tortuga-hiv, tortuga-hoi, og tortuga-loot.

- Topic mellom tortuga-hiv og tortuga-hoi benytter `src/main/avro/Hendelse.avsc`
- Topic mellom tortuga-hoi og tortuga-loot benytter `src/main/avro/HendelseKey.avsc` som key, 
og `src/main/avro/PensjonsgivendeInntekt.avsc` som value

Java-koden blir generert i `generate-sources`-fasen.

Topic config
============

`src/main/topicconfig/` inneholder konfigurasjonsfilene som ble brukt til å opprette topicene.
Dersom man har behov for å gjenopprette topics så gjør man følgende:
- Gå til swagger siden for [kafka-adminrest](https://kafka-adminrest-q4.nais.preprod.local/api/v1/apidocs/index.html?url=swagger.json#/)
- Naviger til "oneshot"
- Kopier json fra config filen til ønsket topic
- Paste json inn og trykk execute
- Sjekk responskode/output

NB! Dersom man sletter og gjenoppretter topics må man huske å legge til riktige personer i KM gruppen.
