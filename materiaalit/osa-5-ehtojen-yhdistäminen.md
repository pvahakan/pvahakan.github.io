# Tulostaminen f-merkkijonon avulla

Kun aiemmin tulostimme lukuja ja merkkijonoja, käytimme joko ``+``-operaattoria tai erotimme tulostettavat elementit pilkulla. Pythonissa on vielä kolmas hyvin joustava tapa tulostaa erityyppisiä muuttujia.

Esimerkiksi tulostuskomento

```python
luku = 20
print('Kirjoitit luvun', luku)
```

voitaisiin kirjoittaa f-merkkijonon avulla muodossa

```python
luku = 20
print(f'Kirjoitit luvun {luku}')
```

Molemmissa tulostus näyttää ihan samalta, voit kokeilla tätä itse.

F-merkkijonot ovat helppo tapa tulostaa tekstiä, johon pitää liittää monta eri muuttujaa. Riittää, että muuttujat kirjoitetaan aaltosulkeiden sisään f-merkkijonossa.

```python
luku1 = 12
luku2 = 29
luku3 = 1800
print(f'Muuttujien arvot ovat {luku1}, {luku2} ja {luku3}')
```

Edellinen tulostus kirjoittaa näytölle

```
Muuttujien arvot ovat 12, 29 ja 1800
```

# Loogiset operaattorit

Ehtoja voidaan yhdistää käyttämällä loogisia operaattoreita `and` ja `or`.
Operaattori `and` vaatii, että useampi ehto pätee samaan aikaan,
ja operaattori `or` vaatii, että yksi tai useampi ehdoista pätee.

Esimerkiksi ehto `luku >= 5 and luku <= 8` vaatii,
että luku on samaan aikaan ainakin 5 ja enintään 8.
Toisin sanoen luvun tulee olla välillä 5 -- 8.

```python
luku = int(input("Anna luku: "))
if luku >= 5 and luku <= 8:
    print("Luku on välillä 5 -- 8")
```

Ehto `luku < 5 or luku > 8` puolestaan vaatii,
että luku on alle 5 tai yli 8.
Toisin sanoen luku ei saa olla välillä 5..8.

```python
luku = int(input("Anna luku: "))
if luku < 5 or luku > 8:
    print("Luku ei ole välillä 5..8")
```

Voimme käyttää ehdoissa myös operaattoria `not`, joka muuttaa totuusarvon
käänteiseksi.

Esimerkiksi voisimme toteuttaa äskeisen koodin myös näin:

```python
luku = int(input("Anna luku: "))
if not (luku >= 5 and luku <= 8):
    print("Luku ei ole välillä 5..8")
```


Ehto `x >= a and x <= b` on tavallinen tapa testata,
onko luku `x` välillä `a`..`b`.
Tällainen ehto toimii samalla tavalla eri ohjelmointikielissä.

Python-kielen erikoisuutena on, että myös lyhyempi ehto
`a <= x <= b` toimii, eli ehtoja on mahdollista ketjuttaa.
Tällaisia ehtoja käytetään kuitenkin melko harvoin,
ehkä tottumuksesta muihin ohjelmointikieliin.


## Lisää ehtoja

Seuraava ohjelma kysyy käyttäjältä neljä lukua ja selvittää sitten
luvuista suurimman ehtojen avulla:

```python
n1 = int(input("Anna luku 1: "))
n2 = int(input("Anna luku 2: "))
n3 = int(input("Anna luku 3: "))
n4 = int(input("Anna luku 4: "))

if n1 > n2 and n1 > n3 and n1 > n4:
    suurin = n1
elif n2 > n3 and n2 > n4:
    suurin = n2
elif n3 > n4:
    suurin = n3
else:
    suurin = n4

print(f" {suurin} on suurin luku.")
```

```

Anna luku 1: 2
Anna luku 2: 4
Anna luku 3: 1
Anna luku 4: 1
4 on suurin luku.

```

Esimerkissä ensimmäinen ehto `n1 > n2 and n1 > n3 and n1 > n4` on tosi vain, mikäli kaikki kolme ehtoa ovat tosia.

***

## Tehtävä 1

Tee ohjelma, joka kysyy käyttäjän ikää. Jos ikä ei ole uskottava (se on alle 5 tai mahdoton luku iälle), antaa ohjelma siihen liittyvän kommentin.

Vinkki: tarkastele esimerkkisuorituksia löytääksesi oikean vastineen eri vaihtoehdoille.

Esimerkkitulostuksia:

```
Kerro ikäsi? 13
Ok, olet siis 13-vuotias
```

```
Kerro ikäsi? 2
En usko, että osaat kirjoittaa...
```

```
Kerro ikäsi? -4
Taitaa olla virhe
```


## Tehtävä 2

Tee ohjelma, joka kysyy käyttäjän nimeä. Jos nimeksi syötetään Tupu, Hupu tai Lupu, ohjelma tunnistaa käyttäjän Aku Ankan veljenpojaksi.

Jos nimeksi annetaan Mortti tai Vertti, ohjelma vastaavasti tunnistaa käyttäjän Mikki Hiiren veljenpojaksi.

Esimerkkitulostuksia:

```
Anna nimesi: Mortti
Olet luultavasti Mikki Hiiren veljenpoika.
```

```
Anna nimesi: Hupu
Olet luultavasti Aku Ankan veljenpoika.
```

```
Anna nimesi: Keijo
Et ole kenenkään tuntemani hahmon veljenpoika.
```


## Tehtävä 3

Alla oleva taulukko kuvaa erään kurssin arvosanan muodostumista. Tee ohjelma, joka ilmoittaa kurssiarvosanan annetun taulukon mukaisesti.

pistemäärä   | arvosana
:--:|:----:
< 0 |  mahdotonta!
0-49 | hylätty
50-59 | 1
60-69 | 2
70-79 | 3
80-89| 4
90-100 | 5
\> 100 |  mahdotonta!

Esimerkkitulostuksia:

```
Anna pisteet [0-100]: 37
Arvosana: hylätty
```

```
Anna pisteet [0-100]: 76
Arvosana: 3
```

```
Anna pisteet [0-100]: -3
Arvosana: mahdotonta!
```


## Tehtävä 4

Ohjelma kysyy käyttäjältä lukua. Jos luku on jaollinen kolmella, tulostetaan Fizz. Jos luku on jaollinen viidellä, tulostetaan Buzz. Jos luku on jaollinen sekä kolmella, että viidellä, tulostetaan FizzBuzz.

Muista, että jaollisuutta voi tutkia jakojäännösoperaattorilla ``%``.

Esimerkkitulostuksia:

```
Luku: 9
Fizz
```

```
Luku: 7
```

```
Luku: 20
Buzz
```

```
Luku: 45
FizzBuzz
```


# Sisäkkäiset ehtolauseet

Ehtolauseita voidaan kirjoittaa toistensa sisään. Esimerkiksi seuraava ohjelma tunnistaa positiivisista luvuista parittomat ja parilliset:

```python
luku = int(input("Anna luku: "))

if luku > 0:
    if luku % 2 == 0: # Luvun jakojäännös jaettaessa luvulla 2 on nolla
        print("Luku on parillinen")
    else:
        print("Luku on pariton")
else:
    print("Luku on negatiivinen")
```

Esimerkkitulostus kolmella eri syötteellä:

```
Anna luku: 3
Luku on pariton

Anna luku: 18
Luku on parillinen

Anna luku: -4
Luku on negatiivinen

```

Sisäkkäisiä ehtolauseita käytettäessä on tärkeä muistaa oikeat sisennykset. Esimerkiksi `else`-haara yhdistetään oikeaan `if`-lauseeseen juuri saman sisennyksen perusteella.

***

## Tehtävä 5

Vuosi on karkausvuosi, jos se on jaollinen 4:llä. Kuitenkin jos vuosi on jaollinen 100:lla, se on karkausvuosi vain silloin, kun se on jaollinen myös 400:lla.

Tee ohjelma, joka lukee käyttäjältä vuosiluvun, ja tarkistaa, onko vuosi karkausvuosi.

```
Anna vuosi: 2011
Vuosi ei ole karkausvuosi.
```

```
Anna vuosi: 2020
Vuosi on karkausvuosi.
```

```
Anna vuosi: 1800
Vuosi ei ole karkausvuosi.
```


## Tehtävä 6

[Verottajan mukaan](https://www.vero.fi/henkiloasiakkaat/omaisuus/lahja/) lahja tarkoittaa sitä, että omaisuus siirtyy toiselle henkilölle ilman korvausta. Lahjasta pitää maksaa lahjaveroa, jos samalta lahjanantajalta saatujen lahjojen arvo on kolmen vuoden aikana 5 000 euroa tai enemmän.

Kun lahja tulee lähimmiltä sukulaisilta, lahjaveron määrä määräytyy seuraavan taulukon [mukaan](https://www.vero.fi/henkiloasiakkaat/omaisuus/lahja/lahjaverolaskuri/):

Lahja	| Vero alarajalla|	Veroprosentti ylimenevästä
:--:|:----:|:----:
5 000 — 25 000 |	100	|8
25 000 — 55 000	| 1 700|	10
55 000 — 200 000|	4 700	|12
200 000 — 1 000 000	|22 100|	15
1 000 000 —	|142 100|	17

Esimerkiksi 6000 euron lahjasta tulee maksaa veroa 180 euroa (100 + (6000-5000) * 0.08) ja 75000 euron lahjasta tulee maksaa veroa 7100 euroa (4700 + (75000-55000) * 0.12).

Tee ohjelma, joka laskee lahjaveron lähimpien sukulaisten antamalle lahjalle. Alla on muutama esimerkki ohjelman toiminnasta.

```
Lahjan suuruus? 3500
Ei veroa!
```

```
Lahjan suuruus? 5000
Vero: 100.0 euroa
```

```
Lahjan suuruus? 27500
Vero: 1950.0 euroa
```