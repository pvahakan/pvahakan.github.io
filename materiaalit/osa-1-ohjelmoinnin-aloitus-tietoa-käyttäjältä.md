# Ohjelmoinnin aloittaminen Python-ohjelmointikielellä

Tämä opas ja tehtävät perustuvat Helsingin yliopiston avoimeen mooc-verkkokurssiin Ohjelmoinnin perusteet ja jatkokurssi 2021 (https://ohjelmointi-21.mooc.fi/). Kurssimateriaalin ja tehtävät ovat tehneet Erkki Kaila, Antti Laaksonen ja Matti Luukkainen. Muutama kurssin tehtävistä on Arto Hellaksen (né Vihavainen) käsialaa.

Kaikki tietokoneohjelmat muodostuvat komennoista, joita tietokone suorittaa yksi kerrallaan. Yksi hyvin yksinkertainen komento on ``print``, joka tulostaa tekstiä näytölle.

### Esimerkki

Seuraava komento tulostaa tekstin "hei" näytölle.

```python
print('hei')
``` 

Komento on oltava juuri samalla tavalla, jotta Python-tulkki ymmärtää mitä me haluamme tehdä. Jos esimerkiksi yritämme suorittaa komennon

```python
print(hei)
```

seurauksena on virheilmoitus. Komento ei toimi, koska ``hei`` ei ole määritelty merkkijonoksi ja Python-tulkki ei ymmärrä sen olevan tekstiä. Merkkijonot pitää laittaa lainausmerkkien tai heittomerkkien sisään: ``'hei'`` ja ``"hei"`` käsitellään merkkijonona.

## Ohjelman eteneminen

Ohjelmat koostuvat useista komennoista. Komennot suoritetaan järjestyksessä ylhäältä alaspäin. Esimerkiksi ohjelma 

```python
print('moi')
print('mitä')
print('kuuluu')
```

tulostaa sanat "moi", "mitä" ja "kuuluu" näytölle allekkain tässä järjestyksessä.

## Laskutoimitukset

Pythonia voidaan käyttää myös laskimena. Jos ``print``-komennon sisään laitetaan laskutoimitus, ohjelma tulostaa näytölle laskun vastauksen.

```python
print(2 + 2)
print(3 * 3)
print(2 + 3 * 5)
```

tulostaisi näytölle

```
4
9
17
```

Huomaa, että nyt numeroiden ympärillä ei ole lainausmerkkejä, koska ne ovat numeroita eikä merkkijonoja.

```python
print(2 + 2 * 10)
print('2 + 2 * 10')
```

Yllä olevat komennot tulostuvat näytölle muodossa

```
12
2 + 2 * 10
```

Toisessa komennossa kyse on merkkijonosta, joten se tulostetaan merkki kerrallaan näytölle. Merkkijono tulostetaan siis sellaisenaan riippumatta sen sisällöstä.

## Kommentit

Kommentit ovat tärkeä osa ohjelman toimintaa. Jos rivin alussa on ``#``, kyseinen rivi käsitellään kommenttina eikä sen sisältö vaikuta ohjelman suoritukseen. **Kommentteja kannattaa käyttää riittävän paljon**, jotta ohjelman toimintaa olisi mahdollisimman helppo ymmärtää.

```python
print('Vuodessa on tunteja')
print(365 * 24) # 365 päivää ja päivässä 24 h
```

Nyt ylläolevan ohjelman lasku on helpompi ymmärtää, kun se on kommentilla selitetty. Huomaa, että kommentti voi sijaita myös komennon perässä kuten yllä. Tällöin ennen kommenttimerkkiä oleva ohjelma suoritetaan normaalisti. Jos kommenttimerkki on rivin alussa, koko rivi käsitellään kommenttina.

***

## Tehtäviä

Kun teet tehtäviä, luo kansio, jonka nimi on sama kuin otsikko yllä, tässä ohjelmoinnin_aloittaminen.Tee jokainen tehtävä **omana tiedostona** kansion sisään. Tiedostojen nimeäminen voi perustua tehtävän sisältöön tai numerointiin, esim. tehtävä_1.py. **Python-tiedostot nimetään .py -päätteellä**!

1. Kirjoita ohjelma, joka tulostaa ruudulle hymiön ``:-)``.
2. Alla olevan ohjelman tarkoitus on tulostaa seitsemän veljeksen nimet aakkosjärjestyksessä. Ohjelma ei toimi kuitenkaan niinkuin halutaan. Korjaa ohjelma, jotta se toimii oikein.
```python
print('Simeoni')
print('Juhani')
print('Eero')
print('Lauri')
print('Aapo')
print('Tuomas')
print('Timo')
```
3. Tee ohjelma, joka tulostaa minuuttien määrän vuorokaudessa. Käytä minuuttien laskemisessa Pythonia. Lisää myös tulostus, jossa näkyy lasku, jolla sait laskettua minuuttien määrän.

***

# Tietoa käyttäjältä

Sana *syöte* tarkoittaa tietoa, joka pyydetään käyttäjältä. Pythonissa on komento ``input``, jonka avulla voimme pyytää käyttäjältä syötettä.

```python
nimi = input('Kirjoita nimesi: ')
print('Moi ' + nimi)
```

Ohjelman suoritus voisi näyttää seuraavalta. Esimerkkitulostuksessa nimi Pekka Puupää on käyttäjän kirjoittama nimi ohjelman suorituksen aikana.

```
Kirjoita nimesi: Pekka Puupää
Moi Pekka Puupää
```

Ohjelmassa esintyvä ``nimi`` on muuttuja. Muuttujat ovat hyvin tärkeitä ohjelmoinnissa, sillä ne ovat paikkoja, jonne voidaan tallettaa jokin arvo kuten merkkijono tai numero. Muuttujasta voidaan myöhemmin lukea arvo tai muuttaa sitä. Muuttujien nimeämisessä kannattaa käyttää kuvaavia ilmaisuja. Esimerkiksi edellisessä esimerkissä muuttuja ``nimi`` kuvaa hyvin mitä se pitää sisällään.

## Muuttujaan viittaaminen

Muuttujan sisältämää arvoa voidaan käyttää ohjelmassa useasti. Tällöin puhutaan muuttujaan viittaamisesta.

```python
nimi = input('Kirjoita nimesi: ')
print('Moi ' + nimi + '!')
print(nimi + ' on aika kiva nimi.')
```
Esimerkkitulostus voisi näyttää tältä: (Pekka Puupää on käyttäjän kirjoittama nimi.)

```
Kirjoita nimesi: Pekka Puupää
Moi Pekka Puupää!
Pekka Puupää on aika kiva nimi.
```

Tulostuskomennossa annetaan merkkijono ja muuttuja ``+``-operaattorilla yhdistettynä. Merkkijonojen tapauksessa ``+``-operaattori yhdistää kaksi annettua merkkijonoa peräkkäin yhdeksi uudeksi merkkijonoksi. ``+``-operaattori on yksi tapa, jolla merkkijonoja voidaan yhdistää Pythonissa.

## Useampi syöte

Ohjelma voi kysyä käyttäjältä useita eri syötteitä. 

```python
nimi = input('Anna nimesi: ')
sposti = input('Anna sähköpostiosoitteesi: ')
lempinimi = input('Anna lempinimesi: ')

print('Nimesi: ' + nimi)
print('Sähköpostiosoitteesi: ' + sposti)
print('Lempinimesi: ' + lempinimi)
```

Huomaa, että jokainen ``input``-komennolla kysytty merkkijono talletetaan omaan muuttujaan! Muuttujan nimet kuvaavat hyvin, mitä missäkin muuttujassa on. Esimerkkitulostus voisi näyttää seuraavalta:

```
Anna nimesi: Pekka Puupää
Anna sähköpostiosoitteesi: pekka.puupaa@sahkoposti.fi
Anna lempinimesi: Pepu

Nimesi: Pekka Puupää
Sähköpostiosoitteesi: pekka.puupaa@sahkoposti.fi
Lempinimesi: Pepu
```

Jos samaan muuttujaan luetaan monta syötettä, uusi syöte ylikirjoittaa aina vanhan syötteen.

```python
osoite = input('Anna osoite: ')
osoite = input('Anna uusi osoite: ')
print('Osoite on nyt ' + osoite)
```

Esimerkkitulostus

```
Anna osoite: Koodarikuja 1 B 8
Anna uusi osoite: Bugitie 2 B 4
Osoite on nyt Bugitie 2 B 4
```

***

## Tehtäviä

Tee taas uusi kansio, jonka nimi on nyt tietoa_käyttäjältä ja kansion sisään jokaiselle tehtävälle oma python-tiedosto. Muista, että tiedoston nimen perässä on .py -pääte!

1. Kirjoita ohjelma, joka kysyy käyttäjältä nimen. Sen jälkeen ohjelma tulostaa nimen kahteen kertaan peräkkäisille riveille. Esimerkkitulostus:
```
Anna nimesi: Pekka
Pekka
Pekka
```
2. Kirjoita ohjelma, joka kysyy käyttäjältä nimen. Sen jälkeen ohjelma tulostaa nimen kahteen kertaan samalle riville. Rivin alussa, nimien välissä ja rivin lopussa on huutomerkit. Esimerkkitulostus:
```
Anna nimesi: Pekka
!Pekka!Pekka!
```
3. Kirjoita ohjelma, joka kysyy käyttäjän nimen ja osoitteen. Ohjelma tulostaa käyttäjän syöttämät tiedot. Esimerkkitulostus:
```
Etunimi: Pekka
Sukunimi: Puupää
Katuosoite: Koodarikuja 2
Postinumero ja kaupunki: 99999 Pythonila
Pekka Puupää
Koodarikuja 2
99999 Pythonila
```
4. Tee ohjelma, joka tulostaa alla olevan tarinan. Tarinaan on upotettu käyttäjän antama nimi ja vuosi. Tulostuksen pitää muuttua käyttäjän syöttämien tietojen mukaan. Esimerkkitulostus
```
Anna nimi: Pekka
Anna vuosi: 1572

Pekka on urhea ritari, syntynyt vuonna 1572. Eräänä aamuna Pekka heräsi kovaan meluun: lohikäärme lähestyi kylää. Vain Pekka voisi pelastaa kylän asukkaat.
```

***