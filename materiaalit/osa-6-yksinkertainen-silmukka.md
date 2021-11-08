# Yksinkertainen silmukka

Silmukka eli toistolause on ehtolauseen lisäksi keskeinen ohjausrakenne ohjelmoinnissa. Aloitetaan toistamiseen tutustuminen tarkastelemalla Pythonin `while`-silmukkaa yksinkertaisten esimerkkien kautta.

Silmukan idea on, että samaa koodia voidaan toistaa monta kertaa peräkkäin.

Tarkastellaan esimerkkiä, jossa ohjelma laskee käyttäjän syöttämien lukujen neliöitä (neliö = toinen potenssi), kunnes käyttäjä syöttää luvun -1:

```python
while True:
    luku = int(input("Anna luku, -1 lopettaa: "))

    if luku == -1:
        break

    print(luku ** 2)

print("Kiitos ja moi!")
```

Ohjelman esimerkkisuoritus:

```
Anna luku, -1 lopettaa: 2
4
Anna luku, -1 lopettaa: 4
16
Anna luku, -1 lopettaa: 10
100
Anna luku, -1 lopettaa: -1
Kiitos ja moi!
```

Kuten esimerkistä huomataan, ohjelman kysyy `while`-lauseen ansiosta käyttäjältä useita lukuja. Sitten kun käyttäjän syöte on -1, suoritetaan `break`-komento, jolloin suoritus hyppää ensimmäiselle lohkon jälkeiselle riville.

Silmukoita käytettäessä on oltava tarkkana, että ei jouduta tilanteeseen, missä silmukan suoritus ei koskaan lopu. Muutetaan edellistä esimerkkiä seuraavasti

```python
luku = int(input("Anna luku, -1 lopettaa: "))
while True:
    if luku == -1:
        break

    print(luku ** 2)

print("Kiitos ja moi!")
```

Nyt siis lukua kysytään _silmukan ulkopuolella_. Jos käyttäjä antaa minkä tahansa muun luvun kuin -1:n, ei silmukasta tulla koskaan pois, eli syntyy _ikuinen silmukka_. Tällöin silmukassa olevaa lohkoa suoritetaan ikuisesti:

```
Anna luku, -1 lopettaa: 2
4
4
4
4
4
4
4
4
(jatkuu ikuisesti...)
```

Seuraavassa esimerkkinä ohjelma, joka antaa käyttäjän jatkaa eteenpäin vasta sen jälkeen, kun käyttäjä on syöttänyt oikean PIN-koodin _1234_:

```python
while True:
    koodi = input("Anna PIN-koodi: ")
    if koodi == "1234":
        break
    print("Väärin... yritä uudelleen")

print("PIN-koodi oikein!")
```

```
Anna PIN-koodi: 0000
Väärin... yritä uudelleen
Anna PIN-koodi: 9999
Väärin... yritä uudelleen
Anna PIN-koodi: 1234
PIN-koodi oikein!
```

HUOM! Sama ohjelma voitaisiin kirjoittaa myös seuraavalla tavalla:

```python
while True:
    koodi = input('Anna PIN-koodi')
    if koodi = "1234":
        print('PIN-koodi oikein!')
        break
    else:
        print('Väärin... yritä uudelleen')
```
Kahden edellisen esimerkin toiminnallisuus on sama, mutta jälkimmäisen toiminta voi olla helpompi ymmärtää tässä vaiheessa.

***

## Tehtävä 1

Kirjoita edellä olevaa toistolause-esimerkkiä mukaillen ohjelma, joka tulostaa viestin "moi" ja kysyy käyttäjältä "Jatketaanko?" kunnes käyttäjä syöttää merkkijonon "ei". Tämän jälkeen tulostetaan merkkijono "ei sitten" ja suoritus päättyy.

Esimerkkitulostus

```
moi
Jatketaanko? kyllä
moi
Jatketaanko? yes
moi
Jatketaanko? jawohl
moi
Jatketaanko? ei
ei sitten
```


## Tehtävä 2

Kirjoita ohjelma, joka kysyy käyttäjältä lukuja. Mikäli luku on negatiivinen (eli pienempi kuin nolla), käyttäjälle tulostetaan viesti "Epäkelpo luku" ja käyttäjältä kysytään uutta lukua. Jos taas luku on nolla, lukujen lukeminen lopetetaan ja ohjelma poistuu toistolauseesta.

Mikäli luku on positiivinen, ohjelma tulostaa luvun neliöjuuren käyttäen `sqrt`-funktiota, joka on tuotu ohjelmaan `import`-lauseella. Esimerkki funktion käytöstä:

```python
# Tämä pitää olla ohjelman alussa, jotta sqrt toimii
from math import sqrt

print(sqrt(9))
```

```
3.0
```

Esimerkki ohjelman suorituksesta:

```
Syötä luku: 16
4.0
Syötä luku: 4
2.0
Syötä luku: -3
Epäkelpo luku
Syötä luku: 1
1.0
Syötä luku: 0
Lopetetaan...
```


## Tehtävä 3

Seuraavassa ohjelmassa on virhe. Korjaa ohjelma siten, että se toimii alla olevan esimerkkitulostuksen mukaisesti. Voit kopioida koodin IDLE:n editoriin, niin sinun ei tarvitse kirjoittaa sitä uudestaan.

```python
luku = 5
print("Lähtölaskenta!")
while True:
  print(luku)
  luku = luku - 1
  if luku > 0:
    break

print("Nyt!")
```

Esimerkkitulostus (näin pitäisi toimia)
```
Lähtölaskenta!
5
4
3
2
1
Nyt!
```


## Tehtävä 4

Tee ohjelma, joka kysyy käyttäjältä salasanaa ja tämän jälkeen pyytää toistamaan salasanan niin kauan, kunnes käyttäjä syöttää ensimmäisenä annetun salasanan uudelleen.

Esimerkki ohjelman toiminnasta
```
Salasana: sekred
Toista salasana: salainen
Ei ollut sama!
Toista salasana: enmuistaenää123
Ei ollut sama!
Toista salasana: sekred
Käyttäjätunnus luotu!
```

***

## Silmukka ja apumuuttujat

Tehdään vielä PIN-koodin tarkastavasta ohjelmasta monimutkaisempi versio, joka antaa käyttäjälle vain kolme mahdollisuutta yrittää PIN-koodin syöttämistä.

Ohjelma käyttää nyt kahta apumuuttujaa. Muuttuja `yritykset` pitää kirjaa siitä, montako kertaa käyttäjä on syöttänyt koodin.  Muuttuja `onnistui` saa arvokseen joko `True` tai `False` riippuen siitä, onnistuuko kirjautuminen.

```python
yritykset = 0

while True:
    tunnus = input("Anna PIN-koodi: ")
    yritykset += 1 # Lyhennys merkinnälle yritykset = yritykset + 1

    if tunnus == "1234":
        onnistui = True
        break

    if yritykset == 3:
        onnistui = False
        break

    # tänne tullaan jos väärin JA ei ole jo kolmea yritystä
    print("Väärin... yritä uudelleen")

if onnistui: # Lyhennys merkinnälle if onnistui == True:
    print("PIN-koodi oikein!")
else:
    print("Liian monta yritystä...")
```

```
Anna PIN-koodi: 0000
Väärin... yritä uudelleen
Anna PIN-koodi: 1234
PIN-koodi oikein!
```

```
Anna PIN-koodi: 0000
Väärin... yritä uudelleen
Anna PIN-koodi: 9999
Väärin... yritä uudelleen
Anna PIN-koodi: 4321
Liian monta yritystä...
```

Silmukasta tullaan siis ulos, jos käyttäjä syöttää oikean PIN-koodin _tai_ jos yrityksiä tehdään liian monta. Silmukan jälkeinen if-lause tarkastaa muuttujan `onnistui` arvon perusteella, onko kirjautuminen onnistunut vai ei.

***

## Tehtävä 5

Tee sovellus, joka kysyy käyttäjältä PIN-koodia niin kauan, kunnes käyttäjä antaa oikean PIN-koodin _4321_. Ohjelma kertoo yritysten lukumäärän:

```
PIN-koodi: 3245
Väärin
PIN-koodi: 1234
Väärin
PIN-koodi: 0000
Väärin
PIN-koodi: 4321
Oikein, tarvitsit 4 yritystä

```

Tulostus on hieman erilainen jos PIN-koodi on oikea heti ensimmäisellä yrityksellä:

```
PIN-koodi: **4321**
Oikein, tarvitsit vain yhden yrityksen!
```

## Tehtävä 6

Tee ohjelma, joka kyselee käyttäjältä vuosilukua ja kertoo, milloin on seuraava karkausvuosi.

```
Vuosi: 2019
Vuotta 2019 seuraava karkausvuosi on 2020
```

Jos käyttäjän syöttämä vuosi on karkausvuosi (kuten 2020), ohjelma ei kerro tätä vuotta vaan sitä seuraavan karkausvuoden:

```
Vuosi: **2020**
Vuotta 2020 seuraava karkausvuosi on 2024
```


## Merkkijonon kokoaminen plus-operaattorilla

PIN-koodin tarkastavassa esimerkissä käytimme apumuuttujaa `yritykset` pitämään kirjaa siitä, montako kertaa PIN-koodi on syötetty:

```python
yritykset = 0

while True:
    tunnus = input("Anna PIN-koodi: ")
    yritykset += 1
    # ...
```

Muuttuja saa arvon nolla silmukan ulkopuolella, ja jokainen silmukan suoritus kasvattaa sen arvoa yhdellä.

Vastaava idea toimii myös merkkijonoille. Voisimme laajentaa ohjelmaa siten, että se kokoaa yhteen merkkijonoon kaikki käyttäjän syöttämät PIN-koodit:

```python
tunnukset = ""
yritykset = 0

while True:
    tunnus = input("Anna PIN-koodi: ")
    yritykset += 1
    tunnukset += tunnus + ", "
    # ...
```

Apumuuttuja saa aluksi arvokseen _tyhjän merkkijonon_ eli merkkijonon, jossa ei ole yhtään merkkiä:

```python
tunnukset = ""
```

Silmukan sisällä merkkijonoa kasvatetaan lisäämällä siihen aina silmukassa syötetty tunnus ja pilkku:

```python
    tunnus = input("Anna PIN-koodi: ")
    tunnukset += tunnus + ", "
```

Jos käyttäjä syöttäisi tunnukset _1111 2222 1234_ olisi muuttujan `tunnukset` arvo lopulta

```
1111, 2222, 1234,
```


## Tehtävä 7

### Osa 1

Tee ohjelma, joka pyytää käyttäjää syöttämään sanoja. Kun käyttäjä syöttää sanan `loppu`, ohjelma tulostaa sanoista muodostuneen tarinan ja suoritus päättyy.

```
Anna sana: Olipa
Anna sana: kerran
Anna sana: pieni
Anna sana: talo
Anna sana: preerialla
Anna sana: loppu
Olipa kerran pieni talo preerialla
```

### Osa 2

Muokkaa edellisen tehtävän ohjelmaa niin, että sanojen syöttäminen päättyy, jos käyttäjä syöttää sanan `loppu` tai käyttäjä syöttää saman sanan kaksi kertaa peräkkäin.

```
Anna sana: Alussa
Anna sana: oli
Anna sana: suo
Anna sana: kuokka
Anna sana: ja
Anna sana: Jussi
Anna sana: Jussi
Alussa oli suo kuokka ja Jussi
```


## Tehtävä 8

### Osa 1

Tee ohjelma, joka pyytää käyttäjää syöttämään kokonaislukuja. Ohjelma pyytää lukuja niin kauan kunnes käyttäjä syöttää nollan.

```
Syötä kokonaislukuja, 0 lopettaa:
Luku: 5
Luku: 22
Luku: 9
Luku: -2
Luku: 0
```

### Osa 2: lukumäärä

Lisää edelliseen ohjelmaan toiminto, joka pitää kirjaa syötettyjen lukujen lukumäärästä. Syötteiden loppumisesta kertovaa nollaa ei saa ottaa huomioon lukumäärässä.

Tarvitset tässä uuden muuttujan, jonka avulla pidät kirjaa luettujen lukujen määrästä.

```
Syötä kokonaislukuja, 0 lopettaa:
Luku: 5
Luku: 22
Luku: 9
Luku: -2
Luku: 0
Lukuja yhteensä 4
```

### Osa 2: summa

Laajenna ohjelmaa siten, että se tulostaa syötettyjen lukujen summa. Syötteen loppumisesta kertovaa nollaa ei tule ottaa huomioon summan laskemisessa.

Ohjelman tulostus laajenee seuraavasti:

```
Luku: 5
Luku: 22
Luku: 9
Luku: -2
Luku: 0
Lukuja yhteensä 4
Lukujen summa 34
```

### Osa 4: keskiarvo

Laajenna ohjelmaa siten, että se tulostaa syötettyjen lukujen keskiarvon. Syötteen loppumisesta kertovaa nollaa ei tule ottaa huomioon keskiarvon laskemisessa. Voit olettaa, että käyttäjä syöttää aina vähintään yhden luvun.

```
Luku: 5
Luku: 22
Luku: 9
Luku: -2
Luku: 0
Lukuja yhteensä 4
Lukujen summa 34
Lukujen keskiarvo 8.5
```

### Osa 5: positiiviset ja negatiiviset

Laajenna ohjelmaa siten, että se tulostaa positiivisten ja negatiivisten lukujen lukumäärät

```
Luku: 5
Luku: 22
Luku: 9
Luku: -2
Luku: 0
Lukuja yhteensä 4
Lukujen summa 34
Lukujen keskiarvo 8.5
Positiivisia 3
Negatiivisia 1
```