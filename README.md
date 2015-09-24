# Tykkäys 2.0

Aamukahvilla 24.9.2015 puhuttiin uusista asiakkuuksista. Kyselin sitä, että kuinka nopeasti saamme uuden verkkopalveluprojektin pystyyn, ja tämä taitaa olla noin 5-10 päivää.

Kuvitellaan, että uusi asiakkuus haluaisi uuden tykkäys 2.0 -mikropalvelun nykyiseen verkko- ja mobiilipalveluunsa. Kuvitellaan, että tekninen toteutustapa on Python + PostgreSQL, ja ensimmäinen iteraatio kohti toimivaa palvelua on tässä:

 
#!/usr/bin/env python
print "Content-Type: text/html"
print
print """\
<html>
<body>
<h2>Hello World!</h2>
</body>
</html>
"""

Seuraavaksi:

1. Tarvitaan versionhallintaan kaksi repoa: toinen oheiselle Python-koodille ja toinen ajoympäristön konfiguraatiolle (Ansible + Vagrant)
2. Skripti dev-scripts/init-db.sh, joka käynnistää tietokannan
3. Skripti dev-scripts/init-app.sh, joka käynnistää sovelluksen osoitteeseen http://localhost:8080
4. CI-ympäristö e2e-testeineen, joka triggeröityy versionhallinnan muutoksista
5. CD-ympäristö, ja tämä palvelu ajoon osoitteeseen http://test.tykkays20.solita.fi jollekin pilvialustalle
