# Matikkaeditorinkääntäjä

## Mikä Ihmeen Matikkaeditorinkääntäjä?

-   Matikkaeditorinkääntäjä on tarkoitettu lukiolaisille (tai yliopistolaisille) jotka opiskelevat matematiikka tai muita matemaattisia aineita.
-   Sovellus ottaa sisääntulona LaTeX [matikkaeditorin](https://math-demo.abitti.fi/) (tai muiden kaavakirjoitusohjelmien kuten L'math) LaTeX -koodia ja kääntää sen cas- laskinohjelmistolle sopivaan muotoon
-   esim. LaTeX input: "\frac{6\cdot 7}{14}" --> käännetty versio: "(6\*7)/(14)"
-   esimerkki oli vain pieni osa, joka voidaan kääntää
    -   käännettävissä mm. yhtälöryhmät, potenssit, summakaavat ja monia muita
    -   jotkin kääntötilat tunnistavat myös yksiköitä esim. km, mol, s, jotka voidaan esimerkiksi poistaa sekoittamasta laskuja
    -   kääntölistat ja tilojen toiminnat voit löytää tiedoston alaosassa olevista linkeistä (mm. "ohjeita ohjelman käyttämiseen" ja "merkkimuutokset")
-   kääntö on suunniteltu Ti -Nspire cx cas -laskentaohjelmistolle, mutta se toimii myös suurimmilta osin GeoGebrassa ja Matlabiss'

## Miksi Käyttää Matikkaeditorinkääntäjää?

-   Voit laskea nopeammin, koska kaikkea ei tarvitse kirjoittaa käsin
-   ei enää laskujen kopioimista matikkaeditorista vihkon kautta laskentaohjelmistoon
-   vähemmän virheitä: kääntöprosessissa ei tule merkkivirheitä

# Ohjeita Matikkaeditorinkääntäjän käyttämiseen.

Täältä saa paljon vinkkejä ja tietoa kehittäjän mielenkulusta

[Julkaistuihin versioihin](https://github.com/henrivain/Matikkaeditorinkaantaja/releases)

## asennusprosessi

1. Lataa `setup.exe` tiedosto GitHubista
   a) Mene [julkaisut -välilehdelle](https://github.com/henrivain/Matikkaeditorinkaantaja/releases)  
   b) valitse uusin version  
   c) Sivun alareunassa löytyy kohta "Assets" => paina MatikkaeditorinkaantajaX.X.XSEtup.exe"  
   d) odota, että tiedosto latautuu

2. Asenna sovellus  
   a) Tuplaklikkaa MatikkaeditorinkääntäjäX.X.XSetup.exe tiedostoa  
   b) Windows todennäköisesti avaa `Windows suojasi laitettasi` - näkymän, joka tulee näkyviin ensimmäisellä käynnistyskerralla, jos koodilla ei ole digitaalista signeerausta. Paina `lisätietoja` - valitse `suorita joka tapauksessa`  
   c) seuraa asennusohjelman ohjeita - asennusohjelmassa kannattaa painaa "luo pikakuvake"

3. Kun asennusohjelma on valmis, voit käynnistää sovelluksen pikakuvakkeesta

## Asetusten muuttaminen

-   sovelluksen asetuksia voi muuttaa painamalla rattaan kuvaa normaalinäkymässä
-   lisää asetuksia löyty asetusvalikon "lisäasetukset" -kohdasta

## Tilat ja niiden toiminta

### Laskentatilat

-   oletuksena päällä on matematiikkatila
-   tilan muuttamiseksi paina vasemmassa yläkulmassa olevaa asetukset kuvaketta
-   eri tilat muuttavat merkkien käännöksiä
-   merkkikäännökset voi tarkistaa editorin mukana tulevasta Excel -tiedostosta

##### Matikkatila

-   kääntää kaiken matikan näkökulmasta
-   ei tunnista eikä poista yksiköitä

##### Fysiikkatila 1

-   tunnistaa useita yksiköitä ja poistaa ne

##### Fysiikkatila 2

-   tunnistaa yksiköt latex-kaavasta ja muuttaa ne sopivaksi Ti-Nspire laskentaohjelmistolle

```
29\cdot 10^{6}\frac{J}{kg}	=> 	29*10^(6)(_J)/(_kg)
```

Nopeuta laskemistasi fysiikkatila 2 avulla!

##### Geometriatila

    - ottaa käyttöön merkit α β γ δ

### Muut tilat

toimintoja jotka helpottavat elämää  
ovat usein oletuksena päällä tai pois

#### Auto Solve

    - lisää annetun kaavan ympärille "solve(kaava,muuttuja)", jos täyttyvät ehdot
    	- kaavasta löytyy jokin merkeistä = >= <= < >
    	- kaavassa on muuttuja x, y tai z
    - jos ehdot eivät täyty ei kaavaan lisätä mitään
    - myös pikanäppäin

#### Auto Derivaatta

    - lisää kaavn ympärille "derivative(kaava, muuttuja)"
    	- jos vähintään yksi muuttuja kaavassa
    	- kaava alkaa isolla D -kirjaimella
    - myös pikanäppäin

##### Pikakääntö

    - toimii "pikakääntö" napista painamalla
    - nopeuttaa laskemista (kaikki toimii yhdellä painalluksella)
    - toiminta:
    	  1) liittää käännettävän LaTeX-koodin leikepöydältä
    	  2) kääntää sen valituissa laskentatiloissa
    	  3) asettaa sen laatikoihin näkyville
    	  4) kopioi käännöksen leikepöydälle

#### Pikanäppäimet

-   pikanäppäimet helpottavat ja nopeuttavat ohjelman käyttämistä
-   tällä hetkellä tuettuina ovat:  
    <kbd>Ctrl</kbd> + <kbd>Shift</kbd> + <kbd>Q</kbd> > pikakääntö  
    <kbd>Ctrl</kbd> + <kbd>Shift</kbd> + <kbd>D</kbd> > pikakääntö + derivaatta  
    <kbd>Ctrl</kbd> + <kbd>Shift</kbd> + <kbd>S</kbd> > pikakääntö + autosolve  
    <kbd>Ctrl</kbd> + <kbd>Shift</kbd> + <kbd>N</kbd> > pikakääntö + oletusasetukset  
    <kbd>Ctrl</kbd> + <kbd>Shift</kbd> + <kbd>F</kbd> > pikakääntö + fysiikkatila 1
    <kbd>Ctrl</kbd> + <kbd>Shift</kbd> + <kbd>W</kbd> > pikakääntö + fysiikkatila 2
    <kbd>Ctrl</kbd> + <kbd>Enter</kbd> + painettuna syötelaatikossa > käännös

#### Lisäasetukset (vähempipätöiset)

##### Poista Aaltosulut

    - poistaa ylijääneet aaltosulut kaavoista
    - kannattaa pitää aina päällä ongelmien välttämiseksi

##### Muuta Erikoismerkit

    - muuttaa vakiot i ja e muotoon @i ja @e (imaginääriyksikkö ja neperin luku)
    - oletuksena pois päältä

##### Viimeistely

    - poistaa tyhjät potenssit ja jakolaskut, jotka jäävät yli fysiikkatilan yksiköiden poistamisen jälkeen
    - oletuksena päällä

## Asetusten Tallentaminen Uusia Versioita Varten

-   voit tallentaa sovelluksen asetukset mek.config.json tiedostoksi valitsemalla
-   asetukset > lisäasetukset > vie mek datasi > vie
-   sovellus tallentaa tällöin haluamasi asetukset local appData -kansioon, josta uusi versio voi lukea ne helposti

## Sovelluksen Poistaminen

    1) sovelluksen voit poistaa etsimällä sen tallennuspaikan
    	- oletus: "C:\Program Files (x86)\Matikkaeditorinkaantaja\unins000.exe"
    2) käynnistä tiedosto "unins000.exe"
    3) seuraa ohjeita

## Ohjeita Ja Muita Tiedostoja

Uusimmat versiot tiedostoista löytyvät aina Githubista

-   Merkkimuutokset löytyvät [täältä](https://docs.google.com/spreadsheets/d/1bi-iejOZ7LSQXTja8hWFj7LcgKMt4z3Aa5pRelak9R8/edit?usp=sharing)
-   Github repo [täällä](https://github.com/henrivain/Matikkaeditorinkaantaja)
-   Raportoi bugeista tai anna ehdotuksia [täällä](https://github.com/henrivain/Matikkaeditorinkaantaja/issues) tai lähetä sähköpostia


#### Yhteystiedot:

Henri Vainio  
Sähköposti: matikkaeditorinkaantaja(at)gmail.com  
Github: https://github.com/henrivain
