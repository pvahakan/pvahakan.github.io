# Ehtorakenne

Tähän mennessä kaikki kirjoittamamme koodi on suoritettu peräjälkeen. Hyvin usein ohjelmoinnissa tulee vastaan tilanne, että jokin tietty koodinpätkä pitää suorittaa vain tietyssä tilanteessa. Tähän tarkoitukseen ohjelmointikielissä on kehitetty ehtolause.

Seuraavan esimerkin ohjelma tutkii, onko henkilö täysi-ikäinen.

```python
ika = int(input('Kuinka vanha olet? '))

if ika > 17:
    print('Olet täysi-ikäinen.')

print('Seuraava asiakas, kiitos!')
```

Ohjelman tulostus näyttää seuraavalta, kun käyttäjä syöttää iäksi 18 vuotta:

```
Kuinka vanha olet? 18
Olet täysi-ikäinen!
Seuraava asiakas, kiitos!
```

Jos käyttäjän syöttämä ikä on 16 vuotta, tulostus on seuraavan kaltainen:

```
Kuinka vanha olet? 16
Seuraava asiakas, kiitos!
```

Huomataan, että syötteenä annettu lukuarvo vaikuttaa siihen, mitkä osat ohjelmasta suoritetaan. Esimerkkiohjelmassa käytetään ehtorakennetta, jonka sisällä oleva koodi suoritetaan vain jos annettu ehto on tosi.

Ehtolauseessa käytetään avainsanaa ``if``. Sitä seuraa aina jokin ehto, esimerkiksi vertaillaan kahta lukua keskenään. Jos ehto on totta, suoritetaan seuraava koodi. On tärkeää huomata, että ehtolauseessa ensimmäisen rivin lopussa on kaksoispiste. Seuraavassa esimerkissä kaksoispiste puuttuu.

```python
ika = int(input('Kuinka vanha olet? '))

# kaksoispiste unohtui
if ika > 17
    print('Olet täysi-ikäinen.')

print('Seuraava asiakas, kiitos!')
```

Kun suoritamme yllä olevan koodin, tulostuu virheilmoitus:
```
File "ohjelma.py", line 3
    if ika > 17
               ^
SyntaxError: invalid syntax
```

``SyntaxError`` tarkoittaa, että koodin syntaksissa, eli kirjoitusasussa on jotakin pielessä. Pythonissa on paljon erilaisia virheilmoituksia, jotka tulevat varmasti tutuiksi ohjelmoinnin yhteydessä.

## Vertailuoperaattorit

Ehtolauseissa hyvin yleinen tilanne on vertailla kahta eri arvoa keskenään. Pythonissa on olemassa kuusi erilaista vertailuoperaattoria, jotka ovat lueteltu alla.

|Operaattori | Merkitys | Esimerkki|
|:-----------|:---------|:--------|
|`==`        | Yhtä suuri | `a == b`|
|``!=``      | Erisuuri | `a != b`|
|`>`      | Suurempi kuin | `a > b`|
|`>=`      | Suurempi tai yhtä suuri | `a >= b`|
|`<`      | Pienempi kuin | `a < b`|
|`<=`      | Pienempi tai yhtä suuri | `a <= b`|

Seuraava esimerkkiohjelma tutkii, onko käyttäjän syöttämä luku negatiivinen, positiivinen vai nolla:

```python
luku = int(input('Anna luku: '))

if luku < 0:
    print('Luku on negatiivinen.')

if luku > 0:
    print('Luku on positiivinen.')

if luku == 0:
    print('Luku on nolla.')
```

Kun ohjelma suoritetaan eri syötteillä, saadaan seuraavat tulostukset:

```
Anna luku: 15
Luku on positiivinen.
```
```
Anna luku: -20
Luku on negatiivinen.
```
```
Anna luku: 0
Luku on nolla.
```

## Sisentäminen

Kuten varmaan huomasit, esimerkeissä ehtolauseen ensimmäisen rivin jälkeiset rivit ovat sisennetty. Pythonissa koodin sisentäminen on erityisen tärkeää, koska **Python tunnistaa ehtorakenteen sisällä olevan koodin sisennyksestä**. Jokaisella sisennetyllä rivillä tulee olla yhtä paljon tilaa. Sisennys tehdään tabulaattorilla (caps lock -näppäimen yläpuolella oleva näppäin) Yleensä tekstieditorit osaavat kyllä sisentää koodin automaattisesti, kun kaksoispisteen jälkeen painetaan entteriä. Sisennys loppuu backspace-näppäimellä (enterin yläpuolella oleva, se jolla pyyhitään tekstiä).

***

## Tehtäviä

1. Kirjoita ohjelma, joka kysyy käyttäjältä kokonaisluvun ja tulostaa merkkijonon "Orwell" jos luku on täsmälleen 1984. Muuten ohjelma ei tulosta mitään.

Esimerkkitulostus:
```
Anna luku: 2021
```
```
Anna luku: 1984
Orwell
```

2. Kirjoita ohjelma, joka laskee itseisarvon käyttäjän syöttämästä luvusta. Ohjelma kysyy käyttäjältä ensin kokonaisluvun. Jos luku on pienempi kuin 0, ohjelma tulostaa luvun kerrottuna luvulla -1. Muuten ohjelma tulostaa käyttäjän syöttämän luvun.

Esimerkkitulostus:
```
Anna luku: -7
Luvun itseisarvo on 7
```
```
Anna luku: 12
Luvun itseisarvo on 12
```

3. Kirjoita ohjelma, joka kysyy käyttäjän nimen. Jos nimi on mikä tahansa muu kuin "Pauli", ohjelma kysyy ruoka-annosten lukumäärän ja kertoo tilauksen kokonaishinnan. Yksi annos maksaa 5,90.

Esimerkkitulostus:
```
Mikä on nimesi: Keke
Kuinka monta ruoka-annosta? 2
Kokonaishinta on 11.8
Seuraava!
```
```
Mikä on nimesi: Pauli
Seuraava!
```

4. Kirjoita ohjelma, joka kysyy luvun ja kertoo sitten sen suuruusluokan kuten seuraavassa esimerkissä.

```
Anna luku: 940
Luku on pienempi kuin 1000
Kiitos hei!
```
```
Anna luku: 24
Luku on pienempi kuin 1000
Luku on pienempi kuin 100
Kiitos hei!
```
```
Anna luku: 3
Luku on pienempi kuin 1000
Luku on pienempi kuin 100
Luku on pienempi kuin 10
Kiitos hei!
```
```
Anna luku: 1239
Kiitos hei!
```

***

## Totuusarvot

Ehtorakenteessa käytettävä ehto saa totuusarvon `True` (tosi) tai `False` (epätosi). Esimerkiksi ehto `a < 5` on tosi jos `a` on alle 5 ja epätosi jos `a` on 5 tai suurempi.

Ohjelmoinnissa totuusarvoja kutsutaan usein boolean-arvoiksi matemaatikko George Boolen kehittämän algebrallisen rakenteen mukaan. Pythonissa totuusarvoja käsitellään `bool`-tietotyypin avulla, ja `bool`-tyyppisillä muuttujilla voi olla vain kaksi eri arvoa: `True` tai `False`. 

Voimme asettaa ehdon tuloksen muuttujan arvoksi samaan tapaan kuin laskutoimituksen tuloksen:

```python
a = 3
ehto = a < 5
print(ehto)
if ehto == True:
    print("a on pienempi kuin 5")
```

```
True
a on pienempi kuin 5
```

Huom! Esimerkissä oleva `if ehto == True:` voitaisiin kirjoittaa myös näin `if ehto:`

***

## Tehtäviä

1. Tee ohjelma, joka kysyy käyttäjältä lämpötilan celsius-asteina, ja tulostaa sitten lämpötilan Kelvin-asteina. Jos lämpötila celsius-asteina on pienempi kuin 0, ohjelma tulostaa lisäksi viestin "Paleltaa!". Celsiusasteet muutetaan Kelvineiksi lisäämällä celsiusasteisiin 273. 


Kaksi esimerkkisuoritusta:

```
Anna lämpötila (C): 101
101 celsius-astetta on 374 Kelvin-astetta
```
```
Anna lämpötila (C): -15
-15 celsius-astetta on 258 Kelvin-astetta
Paleltaa!
```



<in-browser-programming-exercise name="Palkka" tmcname="osa01-27_palkka">

2. Tee ohjelma, joka kysyy tuntipalkkaa, työskenneltyjen tuntien määrää ja viikonpäivää. Ohjelma tulostaa palkan, joka on tuntipalkka kertaa tuntien määrä muina päivinä paitsi sunnuntaisin, jolloin tuntipalkka on kaksinkertainen.

```
Tuntipalkka: 8.5
Työtunnit: 3
Viikonpäivä: maanantai
Palkka 25.5 euroa
```
```
Tuntipalkka: **12.5**
Työtunnit: **10**
Viikonpäivä: **sunnuntai**
Palkka 250.0 euroa
```


3. Tee ohjelma, joka kysyy huomisen sääennusteen ja suosittelee sen mukaista pukeutumista. Suositus vaihtelee sen mukaan, onko lämpötila yli 20 astetta, yli 10 astetta vai yli 5 astetta. Myös sade vaikuttaa suositukseen.

Ohjelma toimii seuraavasti:

```
Kerro huominen sääennuste:
Lämpötila: 21
Sataako (kyllä/ei): ei
Pue housut ja t-paita
```

```
Kerro huominen sääennuste:
Lämpötila: 11
Sataako (kyllä/ei): ei
Pue housut ja t-paita
Ota myös pitkähihainen paita
```

```
Kerro huominen sääennuste:
Lämpötila: 7
Sataako (kyllä/ei): ei
Pue housut ja t-paita
Ota myös pitkähihainen paita
Pue päälle takki
```

```
Kerro huominen sääennuste:
Lämpötila: 3
Sataako (kyllä/ei): kyllä
Pue housut ja t-paita
Ota myös pitkähihainen paita
Pue päälle takki
Suosittelen lämmintä takkia
Kannattaa ottaa myös hanskat
Muista sateenvarjo!
```

***


# Lisää ehtolauseita

Tarkastellaan ohjelmaa, joka tulostaa tiedon siitä, onko käyttäjän syöte negatiivinen vai positiivinen tai nolla:

```python
luku = int(input("Anna luku: "))

if luku < 0:
    print("Luku on negatiivinen")

if luku >= 0:
    print("Luku on positiivinen tai nolla")
```

Ohjelma on hiukan kömpelö. Jokaisen mahdollisen syötteen kohdalla halutaan suorittaa vain toinen lohkoista, koska aina pätee joko `luku < 0` tai `luku >= 0`. Ensimmäinen vertailu sisältää tavallaan kaiken olennaisen: jos tulos on tosi, luku on negatiivinen, ja jos se on epätosi, luku on positiivinen tai nolla.

Toisen vertailun sijasta onkin usein näppärämpää luoda vaihtoehtoinen haara, joka suoritetaan, _jos ehto on epätosi_. Tätä tarkoitusta varten käytetään `else`-lausetta.

Edellinen esimerkki kirjoitettuna uudestaan:

```python
luku = int(input("Anna luku: "))

if luku < 0:
    print("Luku on negatiivinen")
else:
    print("Luku on positiivinen tai nolla")
```

Kun käytetään if-else-rakennetta, suoritetaan vaihtoehtoisista lohkoista aina jompikumpi. Huomaa, että else-haaraa ei voi olla olemassa ilman edeltävää if-haaraa.

Seuraavassa esimerkissä tutkitaan, onko käyttäjän syöttämä luku parillinen vai pariton. Parillisuuden selvittämiseen käytetään jakojäännösoperaattoria `%`. Jakojäännöksellä on kätevä testata luvun parillisuutta: jos luvun jakojäännös kahdella on nolla, luku on parillinen, ja muuten pariton.

```python
luku = int(input("Anna luku: "))

if luku % 2 == 0:
    print("Luku on parillinen")
else:
    print("Luku on pariton")
```

Esimerkkitulostus:
```
Anna luku: 5
Luku on pariton
```

Kolmas esimerkki, jossa vertaillaan, ovatko kaksi merkkijonoa samat.

```python
oikea = "kissa" # Tämä on siis oikea salasana
salasana = input("Anna salasana: ")

if salasana == oikea:
    print("Tervetuloa")
else:
    print("Pääsy kielletty")
```

Kaksi esimerkkisuoritusta eri syötteillä:

```
Anna salasana: kissa
Tervetuloa
```

```
Anna salasana: apina
Pääsy kielletty
```

## Vaihtoehtoiset haarat elif-lauseella

Usein vaihtoehtoja on kuitenkin enemmän kuin kaksi. Esimerkiksi jalkapallo-ottelun lopputulosta käsitellessä olisi hyvä varautua kolmeen vaihtoehtoiseen lopputulokseen kotijoukkueen kannalta: voitto, häviö tai tasapeli.

Ehtolausetta voidaan laajentaa `elif`-haaralla. Se on lyhenne sanoista "else if", ja tarkoittaa nimensä mukaisesti vaihtoehtoa alkuperäiselle ehdolle.

Tarkastellaan esimerkkiä, jossa selvitetään ottelun voittaja:

```python
maalit_koti = int(input("Kotijoukkueen maalimäärä: "))
maalit_vieras = int(input("Vierasjoukkueen maalimäärä: "))

if maalit_koti > maalit_vieras:
    print("Kotijoukkue voitti!")
elif maalit_vieras > maalit_koti:
    print("Vierasjoukkue voitti!")
else:
    print("Tasapeli!")
```

Kolme esimerkkitulosta eri syötteillä:

```
Kotijoukkueen maalimäärä: 4
Vierasjoukkueen maalimäärä: 2
Kotijoukkue voitti!
```

```
Kotijoukkueen maalimäärä: 0
Vierasjoukkueen maalimäärä: 6
Vierasjoukkue voitti!
```

```
Kotijoukkueen maalimäärä: 3
Vierasjoukkueen maalimäärä: 3
Tasapeli!
```

Esimerkissä ehtolauseessa on siis kolme vaihtoehtoista haaraa, joista suoritetaan aina yksi. Ehtolauseessa `elif`-haaroja voi olla useampia, eikä `else`-haara ole pakollinen.

Esimerkiksi:

```python
print("Joulukalenteri")
pvm = input("Mikä päivä nyt on? ")

if pvm == "24.12.":
    print("Nyt on jouluaatto")
elif pvm == "25.12.":
    print("Nyt on joulupäivä")
elif pvm == "26.12.":
    print("Nyt on tapaninpäivä")

print("Kiitos ja hei.")
```

Esimerkkitulostus
```
Joulukalenteri
Mikä päivä nyt on? 25.12.
Nyt on joulupäivä
Kiitos ja hei.
```

Huomaa, että ehtolauseessa ei edellisessä esimerkissä ole ollenkaan else-haaraa. Jos käyttäjä syöttää jonkin sellaisen päivämäärän, jota ei täytä ehtoa jossain `if`- tai `elif`-lauseessa, ohjelmassa ei suoriteta mitään ehtolauseen kolmesta lohkosta.

```
Joulukalenteri
Mikä päivä nyt on? 1.1.
Kiitos ja hei.
```

***

## Tehtäviä

1. Tee ohjelma, joka kysyy käyttäjän ikää ja kertoo, onko tämä täysi-ikäinen (eli 18-vuotias tai vanhempi).

Esimerkkitulostuksia:

```
Kuinka vanha olet? 12
Et ole täysi-ikäinen!
```

```
Kuinka vanha olet? 32
Olet täysi-ikäinen!
```

2. Tee ohjelma, joka kysyy käyttäjältä kaksi kokonaislukua ja tulostaa niistä suuremman. Jos luvut ovat yhtä suuret, ohjelma huomaa myös tämän.

Esimerkkitulostuksia:

```
Anna ensimmäinen luku: 5
Anna toinen luku: 3
Suurempi luku: 5
```

```
Anna ensimmäinen luku: 5
Anna toinen luku: 8
Suurempi luku: 8
```

```
Anna ensimmäinen luku: 5
Anna toinen luku: 5
Luvut ovat yhtä suuret!
```

3. Tee ohjelma, joka kysyy kahden henkilön nimen ja iän ja tulostaa vanhemman henkilön nimen.

Esimerkkisyötteitä

```
Henkilö 1:
Nimi: Teppo
Ikä: 26
Henkilö 2:
Nimi: Tiina
Ikä: 27
Vanhempi on Tiina
```

```
Henkilö 1:
Nimi: Antti
Ikä: 1
Henkilö 2:
Nimi: Venla
Ikä: 1
Antti ja Venla ovat yhtä vanhoja
```