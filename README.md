# Matikkaeditorinkääntäjä

## Mikä Ihmeen Matikkaeditorinkääntäjä?

- Matikkaeditorinkääntäjä on tarkoitettu lukiolaisille (tai yliopistolaisille) jotka opiskelevat matematiikka tai muita matemaattisia aineita.
- Sovellus ottaa sisääntulona LaTeX [matikkaeditorin](https://math-demo.abitti.fi/) (tai muiden kaavakirjoitusohjelmien kuten L'math) LaTeX -koodia ja kääntää sen cas- laskinohjelmistolle sopivaan muotoon
- esim. LaTeX input: `\frac{6\cdot 7}{14}` -> käännetty versio: `(6\*7)/(14)`
- esimerkki oli vain pieni osa, joka voidaan kääntää
    - käännettävissä mm. yhtälöryhmät, potenssit, summakaavat ja monia muita
    - jotkin kääntötilat tunnistavat myös yksiköitä esim. km, mol, s, jotka voidaan esimerkiksi poistaa sekoittamasta laskuja
    - kääntölistat ja tilojen toiminnat voit löytää tiedoston alaosassa olevista linkeistä (mm. "ohjeita ohjelman käyttämiseen" ja "merkkimuutokset")
- kääntö on suunniteltu `Ti -Nspire cx cas` -laskentaohjelmistolle, mutta se toimii myös suurimmilta osin `GeoGebrassa` ja `Matlabissa`.

## Miksi Käyttää Matikkaeditorinkääntäjää?

- Voit laskea nopeammin, koska kaikkea ei tarvitse kirjoittaa käsin
- ei enää laskujen kopioimista matikkaeditorista vihkon kautta laskentaohjelmistoon
- vähemmän virheitä: kääntöprosessissa ei tule merkkivirheitä

## Asentaminen

1. Lataa `setup.exe` tiedosto GitHubista  
   a) Mene [julkaisut -välilehdelle](https://github.com/henrivain/Matikkaeditorinkaantaja/releases).  
   b) Valitse uusin version.  
   c) Sivun alareunassa löytyy kohta "Assets" => paina MatikkaeditorinkaantajaX.X.XSEtup.exe".  
   d) Odota, että tiedosto latautuu.

2. Asenna sovellus  
   a) Tuplaklikkaa `MatikkaeditorinkääntäjäX.X.XSetup.exe` -tiedostoa  
   b) Windows todennäköisesti avaa `Windows suojasi laitettasi` -näkymän\*. Paina `lisätietoja` -> valitse `suorita joka tapauksessa`  
   c) Seuraa asennusohjelman ohjeita: Asennusohjelmassa kannattaa painaa "luo pikakuvake"

3. Kun asennusohjelma on valmis, voit käynnistää sovelluksen pikakuvakkeesta

<br>

\*Näkymä tulee esille ensimmäisellä käynnistyskerralla, koska koodilla ei ole digitaalista signeerausta (minulla ei ole koska ne maksavat satoja euroja).

## Ohjeita Matikkaeditorinkääntäjän käyttämiseen.

Täältä saa paljon vinkkejä ja tietoa kehittäjän mielenkulusta. Ohjelmiston pitäisi tarjota päivitykset automaattisesti, mutta toisinaan voi olla järkevää tarkistaa ne [täältä](https://github.com/henrivain/Matikkaeditorinkaantaja/releases).

Sovelluksesta löytyy useita asetuksia, joiden avulla kääntämistä voi personoida omiin tarkoituksiin. Sovelluksen asetuksia voi muuttaa painamalla rattaan kuvaa normaalinäkymässä. Lisää asetuksia löyty asetusvalikon `lisäasetukset` -kohdasta

### Laskentatilat

- oletuksena päällä on matematiikkatila
- tilan muuttamiseksi paina vasemmassa yläkulmassa olevaa asetukset kuvaketta
- eri tilat vaikuttavat merkkien ja symboleiden käännöksiin
- merkkikäännökset voit tarkistaa [täältä](https://docs.google.com/spreadsheets/d/1bi-iejOZ7LSQXTja8hWFj7LcgKMt4z3Aa5pRelak9R8/edit?usp=drive_link)

#### Matikkatila

kääntää kaiken matematiikan näkökulmasta
ei tunnista eikä poista yksiköitä

#### Fysiikkatila 1

Tämän tilan ideana on poistaa laskuista fysiikan yksiköt, jotta voidaan keskittyä vain laskutoimitukseen.

#### Fysiikkatila 2

Tämä tila tunnistaa yksiköt latex-kaavasta ja muuttaa ne sopivaksi Ti-Nspire laskentaohjelmistolle.

```
29\cdot 10^{6}\frac{J}{kg}	=> 	29*10^(6)(_J)/(_kg)
```

Tehosta fysiikan laskentaasi yksikkötarkastelulla fysiikkatila 2 avulla!

#### Käyttäjän Merkkimuunnokset _**UUTTA!**_

`Asetukset > Lisäasetukset > Symbolimuutokset`

Asetus avaa ikkunan, jossa käyttäjä voi määrätä staattisen merkkimuutoksen (staattisella tarkoitetaan, että se on merkkijono muutos toiseen). Esimerkiksi, 'g' -kirjaimen saa muutettua TI-Nspire putoamiskiihtyvyydeksi '\_g' kirjoittamalla ikkunaan `g -> _g`.

#### Geometriatila

Ottaa käännöksessä käyttöön merkit α β γ δ

### Muut Tilat

#### Auto Solve

- lisää annetun kaavan ympärille "solve(kaava,muuttuja)", jos täyttyvät ehdot
    - kaavasta löytyy jokin merkeistä = >= <= < >
    - kaavassa on muuttuja x, y tai z
- jos ehdot eivät täyty ei kaavaan lisätä mitään
- Saatavilla [pikanäppäin](#pikanäppäimet)

#### Auto Derivaatta

- lisää kaavan ympärille "derivative(kaava, muuttuja)"
    - jos vähintään yksi muuttuja kaavassa
    - kaava alkaa isolla D -kirjaimella
- Saatavilla [pikanäppäin](#pikanäppäimet)

#### Pikakääntö

- toimii "pikakääntö" napista painamalla
- nopeuttaa laskemista (kaikki toimii yhdellä painalluksella)
- toiminta:
    1. liittää käännettävän LaTeX-koodin leikepöydältä
    2. kääntää sen valituissa laskentatiloissa
    3. asettaa sen laatikoihin näkyville
    4. kopioi käännöksen leikepöydälle

## Pikanäppäimet

Pikanäppäimet helpottavat ja nopeuttavat ohjelman käyttämistä

| Näppäinyhdistelmä                                  | Toiminto                     |
| -------------------------------------------------- | ---------------------------- |
| <kbd>Ctrl</kbd> + <kbd>Shift</kbd> + <kbd>Q</kbd>  | pikakääntö                   |
| <kbd>Ctrl</kbd> + <kbd>Shift</kbd> + <kbd>D</kbd>  | Pikakääntö + Autoderivaatta  |
| <kbd>Ctrl</kbd> + <kbd>Shift</kbd> + <kbd>S</kbd>  | Pikakääntö + Autosolve       |
| <kbd>Ctrl</kbd> + <kbd>Shift</kbd> + <kbd>N</kbd>  | Pikakääntö oletusasetuksilla |
| <kbd>Ctrl</kbd> + <kbd>Shift</kbd> + <kbd>F</kbd>  | Pikakääntö + Fysiikkatila 1  |
| <kbd>Ctrl</kbd> + <kbd>Shift</kbd> + <kbd>W</kbd>  | Pikakääntö + Fysiikkatila 2  |
| <kbd>Ctrl</kbd> + <kbd>Enter</kbd> syötelaatikossa | Käännä napin painallus       |

## Lisäasetukset (vähempipätöiset)

| Asetus              | Vaikutus                                                                                                                        | Päällä Oletuksena |
| ------------------- | ------------------------------------------------------------------------------------------------------------------------------- | ----------------- |
| Poista Aaltosulut   | Poistaa parittomat aaltosulut kaavoista. <br>Kannattaa pitää päällä, koska puhdistaa <br>mahdolliset virheet pois käännöksestä. | On                |
| Muuta Erikoismerkit | Muuttaa vakiot `i` ja `e` laskimen muotoon<br> `@i` ja `@e` (imaginääriyksikkö ja neperin luku).                                | Ei                |
| Viimeistely         | Poistaa tyhjät potenssit ja jakolaskut, <br>jotka jäävät jäljelle fysiikkatilan <br>yksikönpoistojen jälkeen                    | On                |

## Asetusten Tallentaminen Uusia Versioita Varten

`Asetukset > Lisäasetukset > Vie MEK datasi > Vie`

Voit tallentaa sovelluksen asetukset `mek.config.json` tiedostoksi. Suorittamalla asetusten viennin, sovellus tallentaa haluamasi asetukset local appData -kansioon, josta uusi versio voi lukea ne helposti. Asetustiedosto tallennetaan kansioon `C:\Users\%USER%\AppData\Local\Matikkaeditorinkaantaja`.

## Sovelluksen Poistaminen

1. sovelluksen voit poistaa etsimällä sen tallennuspaikan
    - oletus: "C:\Program Files (x86)\Matikkaeditorinkaantaja\unins000.exe"
2. käynnistä tiedosto "unins000.exe"
3. seuraa ohjeita

## Ohjeita Ja Muita Tiedostoja

Uusimmat versiot tiedostoista löytyvät aina Githubista

- Merkkimuutokset löytyvät [täältä](https://docs.google.com/spreadsheets/d/1bi-iejOZ7LSQXTja8hWFj7LcgKMt4z3Aa5pRelak9R8/edit?usp=sharing)
- Github repo [täällä](https://github.com/henrivain/Matikkaeditorinkaantaja)
- Raportoi bugeista tai muuta palautetta voi antaa [täällä](https://github.com/henrivain/Matikkaeditorinkaantaja/issues) tai lähetämällä sähköpostia.

### Yhteystiedot:

Henri Vainio  
Sähköposti: matikkaeditorinkaantaja(at)gmail.com  
Github: https://github.com/henrivain
