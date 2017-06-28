# Ammattilaisten roolit ja valtuutus

## Roolit
ODA:ssa on tunnistettu seuraavat pääroolit:
* Organisaation pääkäyttäjä, jolla on oikeus hallita oman organisaationsa työlistoja ja niihin liitettyjä ammattilaisia.
* Sosiaali- ja terveydenhuollon ammattilainen, joka voi olla luvitettuna yhteen tai useampaan työlistaan. Muodostaa hoitosuhteen asiakkaan kanssa, ottaessaan asiakkaan suunnitelman tai yhteydenoton vastuulleen. 
Ammattilaiskäyttäjällä on lisäksi Valviran ammattioikeudet -koodiston mukainen ammattioikeus, joka määrittää käyttöoikeudet tarkemmalla tasolla.
* Asiakas, joka voi olla tunnistautumaton tai tunnistettu.

Käyttäjä toimii aina yhdessä roolissa kerrallaan. Roolin vaihto toteutetaan kuitenkin mahdollisimman helpoksi ja käyttäjäystävälliseksi, jolloin se voidaan tehdä 'lennosta' kun ollaan kirjautuneena ja vahvasti tunnistettuna.
Ammattilaiskäyttäjän rooli on aina organisaatiokohtainen ja se mallinnetaan HL7 FHIR PractitionerRole resurssilla (ODA-PractitionerRole-profile). Roolit listataan ODA-practitionerroles-valueset -nimikkeistössä. 

![](http://www.plantuml.com/plantuml/proxy?src=https://raw.githubusercontent.com/omahoito/rfc/master/ODA-Roles.plantuml?1) 

## Koodistot
* Terhikki/Suosikki rekisterinumero: https://julkiterhikki.valvira.fi ja http://www.valvira.fi/terveydenhuolto/rooli-_ja_attribuuttitietopalvelu
* Terhikki/Suosikki sulkulista http://www.valvira.fi/terveydenhuolto/rooli-_ja_attribuuttitietopalvelu
* Ammattioikeustiedot: https://koodistopalvelu.kanta.fi/codeserver/pages/classification-view-page.xhtml?classificationKey=355&versionKey=433
* Toimipaikkakoodit: http://91.202.112.142/codeserver/pages/classification-view-page.xhtml?classificationKey=421&versionKey=501
* Reseptimääräysoikeudet
* Puolesta-asiointirekisteri
* VRK henkilöiden kotiosoiterekisteri

## Puolesta-asiointi
Kansalainen kirjautuu Suomi.fi palveluun ja saa henkilötunnuksen. Tämän jälkeen kysellään valtuutukset ja puolesta-asioinnin oikeudet, ja saadaan näiden henkilötunnukset.
Ammattilainen kirjautuu toimikortillaan, josta saadaan ammattilaisen henkilötunnus.

## Ammattilaisen metatiedot
AP: Selvitetään tekninen tapa lukea kirjautumisesta Terhikki-rekisterinumero. Jos tämmöistä ei ole, ammattilaisten henkilötunnuksista ja niihin liittyvistä Terhikki-rekisterinumeroista on luotava käyttäjärekisteri.
Ammattilaiselle julkaistaan ne käyttöliittymäobjektit jotka liittyy hänen ammattioikeuksiin.

## Luvitus työjonoon
Työjonoon tulee tietopyyntöjä ja kun ensimmäinen ammattilainen alkaa osallistumaan hoitoon tiketin avatessaan, on tultu potilaaksi.
Toimipaikoille nimetään vastuuhenkilö jolla on valtuutukset avata työjono tai työjonoja, joissa tehdään nimettyjen ammattioikeuksien mukaista call center -työtä. Vastuuhenkilöistä on käyttäjärekisteri. Työjonossa voi tehdä vain niitä töitä johon ammattilaisella on ammattioikeudet.
Lähtökohtaisesti ammattilainen on ODA työjonossa selaimella tai mobiililaitteella.

## Palveluun ohjaaminen
Käyttäjä ohjataan palveluun VRK henkilöiden kotiosoiterekisterin perusteella. Asuinalueesta selvitetään toimipaikka geokoodaamalla. 
Käyttäjällä voi myös olla profiilin metatietoja jossa on väliaikaisia sijainteja, osotteita, preferoituja tuottajaorganisaatioita tai preferoituja ammattilaisia.

## Luvitus dataan
Luvitus dataan perustuu hoitosuhteeseen. Hoitosuhde syntyy, kun ammattilainen osallistuu asiakkaan suunnitelmaan päävastuullisena tai osana hoitotiimiä. Asiakas luvittaa Kantasta ja Omatietovarannosta haetut terveystietonsa hoitoon osallistuville ammattilaisille.

## Kontekstinhallinta
Testataan minimikontekstinhallinta potilastietojärjestelmittäin kun tullaan minimikontekstin kautta.

## Provisiointitapaukset
* Pääkäyttäjän provisiointi toimipaikalle.
* Ammattilaisen provisiointi työjonooon.
* Ammattilaisen mobiililaitteen provisiointi.
* Kansalaisen  mobiililaitteen provisiointi.
* Kansalaisen preferoitujen toimipaikkojen provisiointi.
* Käyttäjien provisiointi, jos käytettävissä ei ole kantaa jossa ilmenee hetu ja Terhikki-koodi.
