---
layout: post
title: Grafiikan piirtäminen
date: 27.11.2021
---

## Grafiikan piirtäminen Turtle-kirjastolla

Pythonissa on esiasennettuna kirjasto turtle, jolla voi piirtää yksinkertaista grafiikkaa. Sen ajatus on ikään kuin liikutella kilpikonnaa näytöllä, joka piirtää kulkemansa reitin näkyviin. Puhutaan jatkossa kuitenkin kynästä, sillä se on lyhyempi sana ja ehkä helpompi hahmoittaa.

Jotta kynää voi liikutella, täytyy se ensin luoda. Lisäksi meidän täytyy ottaa turtle-kirjasto käyttöön import-komennolla. Kynän luonti toimii siis seuraavalla tavalla:

```python
import turtle

kyna = turtle.Turtle()
```

Nyt meillä on käytössä ``kyna``-objekti, jolle voimme antaa komentoja ja se osaa piirtää meille sillä tavalla, kuten olemme sitä komentaneet. Jos haluamme liikuttaa kynää eteenpäin, käytämme komentoa ``forward(matka)``. ``matka``-parametri on luku, joka kertoo kynän kulkeman matkan. Jos kirjoitamme ohjelman


```python
import turtle

kyna = turtle.Turtle()

kyna.forward(30)
```

kynä siirtyy eteenpäin 30 askelta. Muita yleisiä komentoja ovat ``left(kulma)``, ``right(kulma)`` ja ``backward(matka)``. ``left`` ja ``right`` nimensä mukaisesti kääntävät kynän kulkusuuntaa vasemmalle tai oikealle ``kulman`` verran, missä ``kulma`` on annettu asteina. Esimerkiksi neliö voitaisiin piirtää seuraavalla ohjelmalla:


```python
import turtle

kyna = turtle.Turtle()

kyna.forward(30)
kyna.left(90)
kyna.forward(30)
kyna.left(90)
kyna.forward(30)
kyna.left(90)
kyna.forward(30)
kyna.left(90)
```

Ympyrän piirtämiselle on oma komentonsa ``circle(säde)``, missä ``säde`` on ympyrän säteen mitta. Seuraava ohjelma piirtäisi ympyrän.

```python
import turtle

kyna = turtle.Turtle()

kyna.circle(50)
```

Kynää voidaan kontrolloida, eli se voidaan nostaa ja laskea. Jos kynä nostetaan, se ei luonnollisesti piirrä viivaa. Nostaminen tehdään komennolla ``penup()`` ja laskeminen komennolla ``pendown()``. Seuraavassa esimerkissä piirretään neljä viivaa peräkkäin ja jokaisen viivan väliin jää tyhjä alue.

```python
import turtle

kyna = turtle.Turtle()

# Piirtäminen
kyna.forward(30)

# Kynä ylös ja siirto
kyna.penup()
kyna.forward(30)

# Piirtäminen
kyna.pendown()
kyna.forward(30)

# Kynä ylös ja siirto
kyna.penup()
kyna.forward(30)

# Piirtäminen
kyna.pendown()
kyna.forward(30)

# Kynä ylös ja siirto
kyna.penup()
kyna.forward(30)

# Piirtäminen
kyna.pendown()
kyna.forward(30)
```

Piirtämiseen saa uusia ulottuvuuksia, kun käyttää toistorakennetta. Esimerkiksi ``while``-silmukalla voi toistaa jotakin kuviota pienillä muutoksilla, ja lopputulos voi olla hyvin mielenkiintoinen. Seuraavassa esimerkissä piirretään ympyrä useaan kertaan, ja joka kerta ympyrän sädettä ja aloituspistettä siirretään.

```python
import turtle

kyna = turtle.Turtle()

sade = 10

# Toistetaan samaa piirtoa, kunnes ympyrän säde on 100.
while sade <= 100:
    # Piirretään ympyrä, jonka säde on sade-muuttujan arvo
    kyna.circle(sade)

    # Nostetaan kynä, käännetään sitä 10 astetta vasemmalle ja liikutaan 10 askelta eteenpäin
    kyna.penup()
    kyna.right(10)
    kyna.forward(10)

    # Lasketaan kynä, jotta piirtäminen onnistuu
    kyna.pendown()

    # Lisätään säteen arvoon 10, jotta ympyrän säde kasvaa edelliseen verrattuna
    sade += 10
```

## Väriä elämään

Mustavalkoiset kuvat ovat pidemmän päälle hieman tylsiä, mutta onneksi väriä pystyy muuttamaan. Kynän väriä voidaan muuttaa funktiolla ``pencolor(väri)``, missä annetaan argumenttina haluttu väri. Värin voi antaa esimerkiksi englannin kielisellä sanalla. Esimerkiksi seuraava piirtäisi vihreällä viivalla neliön. Kynän paksuutta on myös muutettu ``pensize``-funktiolla, jotta väri erottuu paremmin.

```python
import turtle

kyna = turtle.Turtle()

kyna.pensize(10) # Muutetaan kynän paksuus
kyna.pencolor('green') # Muutetaan väri

# Piirretään neliö
kyna.forward(50)
kyna.left(90)
kyna.forward(50)
kyna.left(90)
kyna.forward(50)
kyna.left(90)
kyna.forward(50)
```

Kuvoita voi myös värittää ``begin_fill()`` ja ``end_fill()`` -komentojen avulla. Nimensä mukaisesti ``begin_fill()`` aloittaa seuraavaksi piirrettävän kuvion värittämisen ja ``end_fill()`` päättää värittämisen. Täytön väriä kontrolloidaan ``fillcolor(väri)``-funktiolla. Esimerkiksi seuraavassa piirretään punainen ympyrä, joka on väritetty siniseksi. Hieman eri paikkaan on piirretty värittämätön keltainen ympyrä.

```python
import turtle

kyna = turtle.Turtle()

kyna.pensize(5) # Muutetaan kynän koko
kyna.pencolor('red') # Muutetaan kynän väri
kyna.fillcolor('blue') # Muutetaan täytön väri

# Aloitetaan täyttö, piirretään ympyrä ja lopetetaan täyttö
kyna.begin_fill()
kyna.circle(20)
kyna.end_fill()

# Siirretään kynää
kyna.penup()
kyna.forward(200)
kyna.pendown()

# Vaihdetaan kynän kokoa ja väriä ja piirretään täyttämätön ympyrä
kyna.pensize(10)
kyna.pencolor('yellow')
kyna.circle(50)
```


## Tekstin kirjoittaminen

Turtlen grafiikkaikkunaan voi kirjoittaa myös tekstiä ``write``-komennolla. Tekstin sijainti määräytyy oletusarvoisesti siten, että kynän kohdalle tulee tekstin alun alanurkka. Kynä täytyy siis ensin siirtää haluttuun kohtaan ja sen jälkeen kirjoitetaan haluttu teksti.

```python
import turtle

kyna = turtle.Turtle()

# Kirjoitetaan tekstiä
kyna.write('Moi')

# Siirretään kynää ilman, että piirretään mitään
kyna.penup()
kyna.right(90)
kyna.forward(200)
kyna.left(90)

# Kirjoitetaan uudestaan eri kohtaan
kyna.write('Moi taas!')
```

Oletusarvoisesti teksti on aika pienellä, mutta sitä voidaan muuttaa. ``write``-funktioon voidaan antaa muitakin parametreja, jotka määräävät esimerkiksi tekstin fonttia ja keskittämistä. Seuraavassa kirjoitetaan teksti 'Moi', mutta sen fonttikokoa on muutettu ja teksti kirjoitetaan kynän kohdalle keskitettynä (eli kynä ei jää tekstin alun alareunaan, vaan tekstin keskikohdan alareunaan).

```python
import turtle

kyna = turtle.Turtle()

# Kirjoitetaan tekstiä
kyna.write('Moi', align='center', font=('Arial', 24, 'bold'))
```

``write``-funktiossa kohta ``align='center'`` käskee keskittämään tekstin. ``font=('Arial', 24, 'bold')`` muuttaa fontin tyypin Arialiksi, fonttikooksi 24 ja lihavoi tekstin (bold on lihavointi englanniksi). Huomaa, että fontin määrityksessä nämä kolme asiaa pitää antaa tuossa järjestyksessä sulkuihin kirjoitettuna ja pilkulla erotettuna.

Turtlella voi tehdä paljon muutakin. Lisätietoa löytyy englanninkielisestä dokumentaatiosta [linkki dokumentaatioon][https://docs.python.org/3/library/turtle.html].

***

## Tehtävä 1

Piirrä 10 neliötä, jotka ovat kaikki hieman eri paikassa. Käytä tehtävässä ``while``-silmukkaa, jotta koodia ei tarvitse kirjoittaa niin paljoa.

## Tehtävä 2

Piirrä joulukortti ja lähetä se Katille Wilman kautta. Kirjoita korttiin myös tekstiä. Tässä tehtävässä voit käyttää luovuutta mahdollisimman paljon. Voit käyttää huoletta aikaa tämän tekemiseen. Piirtämistä voi helpottaa se, että mietit ruutupaperille mitä tulee mihinkin kohtaan. Näin osaat liikuttaa kynää haluaamaasi paikkaan helpommin.