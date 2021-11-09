---
path: '/osa-3/2-merkkijonojen-kasittely'
title: 'Merkkijonojen käsittely'
hidden: false
---


Tämän osion jälkeen

- Osaat käyttää operaattoreita `+` ja `*` merkkijonojen kanssa
- Osaat laskea merkkijonon pituuden
- Tiedät, mitä tarkoittaa merkkijonon indeksointi
- Osaat etsiä osajonoja merkkijonosta


## Merkkijono-operaatiot

Merkkijonojen yhdistäminen tapahtuu `+`-operaattorin avulla:

```python
alku = "esi"
loppu = "merkki"
sana = alku+loppu
print(sana)
```

```

esimerkki

```

Myös `*`-operaattoria voidaan käyttää merkkijonojen yhteydessä. Jos toinen operandi kertolaskussa on merkkijono ja toinen kokonaisluku, saadaan merkkijonoa monistettua annettu määrä. Esimerkiksi:

```python
sana = "apina"
print(sana*3)
```

```

apinaapinaapina

```

Silmukan ja merkkijono-operaatioiden avulla voimme tehdä ohjelman, joka piirtää pyramidin:

```python
n = 10 # pyramidin kerrosten määrä
rivi = "*"

while n > 0:
    print(" " * n + rivi)
    rivi += "**"
    n -= 1
```

Ohjelman tulostus on seuraava:

```x
          *
         ***
        *****
       *******
      *********
     ***********
    *************
   ***************
  *****************
 *******************
```

Silmukassa oleva `print`-komento tulostaa rivin, jonka alussa on `n` välilyöntiä ja sitten muuttujan `rivi` sisältö. Tämän jälkeen muuttujan `rivi` loppuun lisätään kaksi tähteä ja muuttujan `n` arvo vähenee yhdellä.

## Tehtävä 1

Kirjoita ohjelma, joka kysyy käyttäjältä merkkijonon ja määrän ja tulostaa sitten annettua merkkijonoa annetun määrän. Tulostuksen tulee tapahtua yhdelle riville yhteen pötköön.

Esimerkkisuoritus:

```

Anna merkkijono: **heippa**
Anna määrä: **4**
heippaheippaheippaheippa

```


## Merkkijonon pituus ja indeksointi

Funktio `len` palauttaa kokonaisluvun, joka on merkkijonon pituus merkkeinä. Esimerkiksi `len("moi")` palauttaa 3, koska merkkijonossa `moi` on 3 merkkiä.

Seuraava ohjelma tulostaa käyttäjän syöttämän merkkijonon "alleviivattuna" monistamalla merkkiä `-` syötteen pituuden mukaisen määrän:

```python
mjono = input("Anna merkkijono: ")
print(mjono)
print("-"*len(mjono))
```

```

Anna merkkijono: **Moi kaikki!**

<pre>
Moi kaikki!
-----------
</pre>

```

Pituuteen lasketaan mukaan kaikki merkkijonossa olevat merkit, mukaan lukien välilyönnit. Esimerkiksi merkkijonon `moi moi` pituus on 7.

## Tehtävä 2

Kirjoita ohjelma, joka kysyy käyttäjältä kaksi merkkijonoa ja tulostaa jonoista pidemmän (ts. sen, jossa on enemmän merkkejä). Jos jonot ovat yhtä pitkiä tulostetaan viesti "Jonot ovat yhtä pitkät"

Esimerkkisuorituksia:

```

Anna jono 1: **moi**
Anna jono 2: **heippa**
heippa on pidempi

```

```

Anna jono 1: **moikkelis koikkelis**
Anna jono 2: **heipparallaa**
moikkelis koikkelis on pidempi

```

```

Anna jono 1: **moi**
Anna jono 2: **hei**
Jonot ovat yhtä pitkät

```


Yksittäinen merkkijonon merkki voidaan hakea operaattorin `[]` avulla. Operaattori kirjoitetaan merkkijonon perään, ja hakasulkeiden väliin kirjoitetaan halutun merkin _indeksi_ eli kohta merkkijonossa.

Huomaa, että merkkien indeksointi alkaa nollasta: ensimmäinen merkki on indeksin 0 kohdalla, toinen indeksin 1 kohdalla jne.

<img src="3_2_1.png">

Esimerkiksi:

```python

mjono = input("Anna merkkijono: ")
print(mjono[0])
print(mjono[1])
print(mjono[3])

```

Ohjelma tulostaa:

```

Anna merkkijono: **apina**
a
p
n

```

Koska merkkijonon ensimmäinen merkki on indeksin 0 kohdalla, on viimeinen merkki vastaavasti indeksin _pituus_ – 1 kohdalla. Esimerkiksi seuraava ohjelma tulostaa merkkijonon ensimmäisen ja viimeisen merkin:

```python
mjono = input("Anna merkkijono: ")
print("Ensimmäinen: " + mjono[0])
print("Viimeinen: " + mjono[len(mjono) - 1])
```

```

Anna merkkijono: **testi**
Ensimmäinen: t
Viimeinen: i

```

Seuraava ohjelma puolestaan käy läpi kaikki merkkijonon merkit vasemmalta oikealle silmukan avulla:

```python
mjono = input("Anna merkkijono: ")
kohta = 0
while kohta < len(mjono):
    print(mjono[kohta])
    kohta += 1
```

```

Anna merkkijono: **testi**
t
e
s
t
i

```

Pythonissa merkkeihin voi viitata myös alkaen merkkijonon lopusta käyttämällä negatiivisia indeksejä. Merkkijonon viimeinen merkki on indeksin -1 kohdalla, toiseksi viimeinen indeksin -2 kohdalla jne. Onkin kätevämpi kirjoittaa `mjono[-1]` kuin `mjono[len(mjono) - 1]`.

<img src="3_2_2.png">

Tämän avulla aiempi ohjelma voidaan toteuttaa paremmin näin:

```python
mjono = input("Anna merkkijono: ")
print("Ensimmäinen: " + mjono[0])
print("Viimeinen: " + mjono[-1])
```

```

Anna merkkijono: **testi**
Ensimmäinen: t
Viimeinen: i

```

## IndexError: string index out of range

Merkkijonon käsittelyssä tulee olla tarkkana indeksien kanssa. Jos viitataan merkkijonon ulkopuolelle, on seurauksena virheilmoitus _IndexError: string index out of range_:

```python
mjono = input("Anna merkkijono: ")
print("Kymmenes merkki: " + mjono[9])
```

```

Anna merkkijono: **ohjelmoinnin perusteet**
Kymmenes merkki: n

```

```

Anna merkkijono: **python**

Traceback (most recent call last):
  File "<stdin>", line 1, in <module>
IndexError: string index out of range

```

Joskus virhetilanne johtuu ohjelmointivirheestä. Esimerkiksi merkkijonon viimeistä merkkiä tarkasteltaessa on yleistä indeksoida vahingossa yhtä liian pitkälle:

```python
mjono = input("Anna merkkijono: ")
print("Viimeinen merkki: " + mjono[len(mjono)])
```

Koska merkkijonojen indeksit alkavat nollasta, niin viimeinen merkki on indeksissä `len(mjono) - 1` eikä `len(mjono)`.

On myös tilanteita, joissa ohjelman on syytä varautua siihen, että virheen lähde on käyttäjän antama syöte:

```python
mjono = input("Anna merkkijono: ")
if len(mjono) > 0:
    print("Ensimmäinen merkki: " + mjono[0])
else:
    print("Merkkijono on tyhjä eli ensimmäistä merkkiä ei ole")
```

Tässä koodissa tyhjä syöte (käyttäjä painaa ainoastaan Enter) aiheuttaisi virheen, ellei koodari olisi lisännyt tarkastusta tilanteen varalta.

## Tehtävä 3

Kirjoita ohjelma, joka kysyy käyttäjältä merkkijonon ja tulostaa sitten merkkijonon merkit allekkain käänteisessä järjestyksessä lopusta alkuun.

Esimerkkisuoritus:

```

Anna merkkijono: **heippa**
a
p
p
i
e
h

```


## Tehtävä 4


Tee ohjelma, joka kysyy käyttäjältä sanan ja kertoo, ovatko sen toinen ja toiseksi viimeinen merkki samoja.

```

Anna sana: **python**
Toinen ja toiseksi viimeinen kirjain eroavat

```

```

Anna sana: **pascal**
Toinen ja toiseksi viimeinen kirjain on a

```


## Tehtävä 5

Tee ohjelma, joka piirtää käyttäjän määräämän levyisen risuaitaviivan.

```

Leveys: **3**
<pre>
###
</pre>

```

```

Leveys: **8**
<pre>
########
</pre>

```


## Tehtävä 6

Laajenna edellistä niin, että käyttäjä syöttää myös piirrettävien rivien määrän

```

Leveys: **10**
Korkeus: **3**
##########
##########
##########

```


## Tehtävä 7

Tee ohjelma, joka pyytää käyttäjältä merkkijonoja ja tulostaa kunkin merkkijonon oheisen esimerkin mukaisesti alleviivattuna. Ohjelman suoritus päättyy, kun käyttäjä syöttää tyhjän merkkijonon, eli merkkijonon jonka pituus on 0.

```

Anna merkkijono: **Moi kaikki!**
<pre>
Moi kaikki!
-----------
</pre>
Anna merkkijono: **Tämä on testijono**
<pre>
Tämä on testijono
-----------------
</pre>
Anna merkkijono: **a**
<pre>
a
-
</pre>
Anna merkkijono:

```


## Tehtävä 8

Tee ohjelma, joka kysyy käyttäjältä merkkijonon ja tulostaa sen niin, että tulostetuksi tulee tasan 20 merkkiä. Jos merkkijono on lyhyempi, alkuun tulee tarvittava määrä tähtiä `*`.

Voit olettaa, että syötetyssä merkkijonossa on enintään 20 merkkiä.

```

Sana: **python**
<pre>
**************python
</pre>

```

```

Sana: **pitkämerkkijono**
<pre>
*****pitkämerkkijono
</pre>

```

```

Sana: **tosipitkämerkkijono**
<pre>
*tosipitkämerkkijono
</pre>

```



## Tehtävä 9

Tee ohjelma, joka kysyy käyttäjältä sanaa ja tulostaa sanan tähtiraameihin, joissa sana on keskellä. Raamien leveys on 30 merkkiä, ja voit olettaa, että sana mahtuu raameihin.

Huom! Jos sanan pituus on pariton, voit tulostaa sanan kumpaan tahansa mahdollisista keskikohdista.

```

Sana: **koe**
<pre>
******************************
*            koe             *
******************************
</pre>

```

```

Sana: **python**
<pre>
******************************
*           python           *
******************************
</pre>

```



## Osajonot

Merkkijonon _osajono_ muodostuu peräkkäisistä merkeistä, jotka ovat merkkijonon osana. Esimerkiksi merkkijonon `esimerkki` osajonoja ovat `esi`, `imer` ja `merkki`.

Voimme erottaa halutussa kohdassa olevan osajonon syntaksilla `[a:b]`, mikä tarkoittaa, että osajono alkaa kohdasta `a` ja päättyy juuri ennen kohtaa `b`. Voimme ajatella alku- ja loppukohdan merkkien vasemmalle puolelle piirretyiksi viivoiksi alla olevan kuvan mukaisesti:

<img src="3_2_3.png">

Seuraava esimerkki esittelee osajonojen hakemista:

```python
mjono = "saippuakauppias"

print(mjono[0:3])
print(mjono[4:10])

# jos alkukohta puuttuu, se on oletuksena 0
print(mjono[:3])

# jos loppukohta puuttuu, se on oletuksena merkkijonon pituus
print(mjono[4:])
```

```

sai
puakau
sai
puakauppias

```


Merkkijonojen käsittelyssä väli `[a:b]` on _puoliavoin_ eli alkukohta `a`
kuuluu väliin mutta loppukohta `b` ei kuulu väliin. Miksi näin?

Tähän ei ole syvällistä syytä, vaan kyseessä on käytäntö, joka esiintyy
monessa ohjelmointikielessä.

Yksi etu tästä on, että osajonon pituus saadaan helposti laskettua kaavalla `b-a`.
Toisaalta täytyy aina muistaa, että kohdassa `b` oleva merkki
ei tule mukaan osajonoon.


## Tehtävä 10

Tee ohjelma, joka kysyy käyttäjältä merkkijonon ja tulostaa sitten kaikki sen ensimmäisestä merkistä alkavat osajonot pituusjärjestyksessä.

Esimerkkitulostus:

```

Anna merkkijono: **testi**
t
te
tes
test
testi

```


## Tehtävä 11

Tee ohjelma, joka kysyy käyttäjältä merkkijonon ja tulostaa sitten kaikki sen viimeiseen merkkiin päättyvät osajonot pituusjärjestyksessä.

Esimerkkitulostus:

```

Anna merkkijono: **testi**
i
ti
sti
esti
testi

```


## Osajonon etsiminen

Voimme tutkia `in`-operaattorin avulla, onko merkkijonossa tiettyä osajonoa.
Lauseke `a in b` on tosi, jos merkkijonossa `b` on osajono `a`.

Esimerkiksi

```python
mjono = "testi"

print("t" in mjono)
print("x" in mjono)
print("est" in mjono)
print("ets" in mjono)
```

```

True
False
True
False

```

Seuraava ohjelma antaa käyttäjän etsiä merkkijonon osajonoja:

```python
mjono = "saippuakauppias"

while True:
    osa = input("Mitä etsit? ")
    if osa in mjono:
        print("Löytyi")
    else:
        print("Ei löytynyt")
```

```

Mitä etsit? **kaup**
Löytyi
Mitä etsit? **abc**
Ei löytynyt
Mitä etsit? **ippu**
Löytyi
...

```

## Tehtävä 12

Tee ohjelma, joka kysyy käyttäjältä merkkijonon ja tulostaa sitten tiedon löytyvätkö vokaalit a, e ja o merkkijonosta.

Voit olettaa, että merkkijono on syötetty kokonaan pienillä kirjaimilla. Katso mallia esimerkkitulostuksesta.

Esimerkkitulostus:

```

Anna merkkijono: **heippa sulle**
a löytyy
e löytyy
o ei löydy

```

```

Anna merkkijono: **moi**
a ei löydy
e ei löydy
o löytyy

```



Operaattori `in` palauttaa tiedon osajonon esiintymisestä, muttei tietoa siitä, _mistä_ se löytyy. Tätä varten löytyy Pythonin merkkijonojen _metodi_ `find`, joka saa parametrikseen etsittävän osajonon ja palauttaa joko ensimmäisen indeksin, josta osajono löytyy, tai `-1`, jos osajonoa ei löydy merkkijonosta.

Metodia käytetään seuraavasti:

<img src="3_2_4.png">

Esimerkkejä metodin käyttämisestä:

```python
mjono = "testi"

print(mjono.find("t"))
print(mjono.find("x"))
print(mjono.find("est"))
print(mjono.find("ets"))
```

```

0
-1
1
-1

```

Voimme myös laajentaa hakuohjelmaa näin:

```python
mjono = "saippuakauppias"

while True:
    osa = input("Mitä etsit? ")
    kohta = mjono.find(osa)
    if kohta >= 0:
        print(f"Löytyi kohdasta {kohta}")
    else:
        print("Ei löytynyt")
```

```

Mitä etsit? **kaup**
Löytyi kohdasta 7
Mitä etsit? **abc**
Ei löytynyt
Mitä etsit? **ippu**
Löytyi kohdasta 2
...

```


Merkkijonon sisältä merkkijonoa etsivä `find` on siis _metodi_. Metodit ovat sukua jo meille tutuille asioille eli _funktioille_. Metodit ovatkin eräänlaisia funktioita, mutta niiden suorittama operaatio kohdistuu siihen _olioon_, jonka kautta metodia kutsutaan, eli joka esiintyy metodikutsun alussa ennen metodin nimeä. Metodin `find` tapauksessa oliona on merkkijono, jonka osajonoa etsitään.


## Tehtävä 13

Tee ohjelma, joka kysyy käyttäjältä merkkijonoa ja yksittäistä merkkiä. Ohjelma tulostaa merkkijonosta löytyvän ensimmäisen kolmen merkin pituisen osajonon, jonka alkukirjain on käyttäjän syöttämä merkki. Voit olettaa, että merkkijono on vähintään kolmen merkin pituinen.

```

Sana: **apinatalo**
Merkki: **a**
api

```

```

Sana: **banaani**
Merkki: **n**
naa

```

```

Sana: **tomaatti**
Merkki: **x**

```

```

Sana: **python**
Merkki: **n**

```


## Tehtävä 14

Tee edellisestä ohjelmasta laajennettu versio, joka tulostaa _kaikki merkkijonon sisältämät kolmen merkin pituiset osajonot_, joiden alkukirjain on käyttäjän syöttämä merkki. Voit olettaa, että merkkijono on vähintään kolmen merkin pituinen.

```

Sana: **apinatalo**
Merkki: **a**
api
ata
alo

```

```

Sana: **banaani**
Merkki: **n**
naa

```

**Vihje** seuraava esimerkki saattaa antaa jotain inspiraatiota eräästä tavasta miten tätä tehtävää voi lähestyä

```python
sana = input("Sana: ")
while True:
    if len(sana) == 0:
        break
    print(sana)
    sana = sana[2:]
```

```

Sana: **apinatalo**
apinatalo
inatalo
atalo
alo
o

```


## Tehtävä 15

Tee ohjelma, joka etsii merkkijonosta osajonon toisen esiintymän. Jos toista (tai edes ensimmäistä) esiintymää ei löydy, ohjelma tulostaa tästä tiedon.

Määritellään tässä yhteydessä, että esiintymät _eivät_ voi mennä päällekkäin, merkkijonossa `aaaa` osajonon `aa` toinen esiintymä löytyy siis indeksin 2 kohdalta.

Muutama esimerkkisuoritus:

```

Anna merkkijono: **abcabc**
Anna osajono: **ab**
Osajonon toinen esiintymä on kohdassa 3.

```

```

Anna merkkijono: **saippuakauppias**
Anna osajono: **a**
Osajonon toinen esiintymä on kohdassa 6.

```

```

Anna merkkijono: **aybabtu**
Anna osajono: **ba**
Osajono ei esiinny merkkijonossa kahdesti.

```


<quiz id="6bfa7eab-80de-52e2-afe5-285af914099f"></quiz>
