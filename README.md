# Matikkaeditorinkaantaja
MEK -matikkaeditorinkääntäjä-
versio v3.1.9 C#


## Mikä ihmeen matikkaeditorinkääntäjä?
- matikkaeditorinkääntäjä on tarkoitettu lukiolaisille, varsinkin heille jotka opiskelevat pitkää matematiikka tai muita matemaattisia aineita.  
- MEK ottaa sisääntulona [matikkaeditorin](https://math-demo.abitti.fi/) (tai muiden kaavakirjoitusohjelmien kuten L'math) LaTeX -koodia ja kääntää sen cas- laskinohjelmistolle sopivaan muotoon  
- esim. LaTeX input: "\frac{6\cdot 7}{14}" --> käännetty versio: "(6*7)/(14)"  
- esimerkki oli vain pieni osa, joka voidaan kääntää  
	- käännettävissä mm. yhtälöryhmät, potenssit, summakaavat ja monia muita  
	- jotkin kääntötilat tunnistavat myös yksiköitä esim. km, mol, s, jotka voidaan esimerkiksi poistaa sekoittamasta laskuja
	- kääntölistat ja tilojen toiminnat voit löytää tiedoston alaosassa olevista linkeistä (mm. "ohjeita ohjelman käyttämiseen" ja "merkkimuutokset")  
- kääntö on suunniteltu Ti -Nspire cx cas -laskentaohjelmistolle, mutta se toimii myös suurimmilta osin GeoGebrassa   

## Miksi käyttää matikkaeditorinkääntäjää?  
- Voit laskea nopeammin tunnilla, koska kaikkea ei tarvitse kirjoittaa käsin
- ei enää laskujen kopioimista matikkaeditorista vihkon kautta laskentaohjelmistoon
- vähemmän virheitä: kääntöprosessissa ei tule merkkivirheitä


# Ohjeita matikkaeditorinkääntäjän käyttämiseen.
täältä saa paljon vinkkejä ja tietoa kehittäjän mielenkulusta   
   
[Julkaistuihin versioihin](https://github.com/matikkaeditorinkaantaja/Matikkaeditorinkaantaja/releases)
   
## asennusprosessi
	1) Lataa setup.zip tiedosto GitHubista
		a) mene Matikkaeditorinkääntäjän etusivulle GitHubiin (tai paina "Julkaistuihin versioihin" -linkkiä)
		b) sivun oikeassa reunassa näkyy "Releases", paina sen alapuolella olevaan (Latest) Tagia 
		c) Sivun alareunassa löytyy kohta "Assets" => paina "Source code (.zip)"
		d) odota, että selain lataa kansion
	2) Pura ladattu .zip kansio
		a) etsi ladattu kansio tietokoneelta 
			- nimi on Matikkaeditorinkaantaja-versio.zip
			- tallennuspaikka on usein "Ladatut tiedostot" tai "downloads"
		b) tuplaklikkaa kansiota ja valitse yläkulmasta "Pura kaikki"
		c) purettu tiedosto aukeaa ruudulle
		d) tässä vaiheessa voit halutessasi poistaa .zip kansion
	3) Asenna sovellus
		a) Tuplaklikkaa MatikkaeditorinkääntäjäSetup.exe tiedostoa
		b) Windows todennäköisesti avaa Windows suojasi laitettasi
			- näkymä tulee ensimmäisellä käynnistyskerralla, jos koodilla ei ole digitaalista signeerausta
			- paina "lisätietoja"
			- valitse "suorita joka tapauksessa" 
		c) seuraa asennusohjelman ohjeita
			- asennusohjelmassa kannattaa painaa "luo pikakuvake"
	4) Kun asennusohjelma on valmis, voit käynnistää sovelluksen pikakuvakkeesta  
	
## asetusten muuttaminen 
- sovelluksen asetuksia voi muuttaa painamalla normaalinäkymässä 

## Tilat ja niiden toiminta

### Laskentatilat  
- oletuksena päällä on matematiikkatila  
- tilan muuttamiseksi paina vasemmassa yläkulmassa olevaa asetukset kuvaketta  
- eri tilat muuttavat merkkien käännöksiä  
- merkkikäännökset voi tarkistaa editorin mukana tulevasta Excel -tiedostosta

##### Matematiikkatila
	- kääntää kaiken matikan näkökulmasta
	- ei tunnista eikä poista yksiköitä 
        
##### Fysiikkatila 1
	- tunnistaa useita yksiköitä ja poistaa ne 

##### geometriatila
	- ottaa käyttöön merkit α β γ δ

### Muut tilat  
toimintoja jotka helpottavat elämää  
ovat usein oletuksena päällä tai pois
      
#### auto solve
	- lisää annetun kaavan ympärille "solve(kaava,muuttuja)", jos täyttyvät ehdot  
		- kaavasta löytyy jokin merkeistä = >= <= < >
		- kaavassa on muuttuja x, y tai z
	- jos ehdot eivät täyty ei kaavaan lisätä mitään
	- myös pikanäppäin
	
#### auto derivaatta
	- lisää kaavn ympärille "derivative(kaava, muuttuja)"
		- jos vähintään yksi muuttuja kaavassa
		- kaava alkaa isolla D -kirjaimella
	- myös pikanäppäin
		
##### pikakääntö
	- toimii "pikakääntö" napista painamalla
	- nopeuttaa laskemista (kaikki toimii yhdellä painalluksella)
	- toiminta:
		  1) liittää käännettävän LaTeX-koodin leikepöydältä
		  2) kääntää sen valituissa laskentatiloissa
		  3) asettaa sen laatikoihin näkyville
		  4) kopioi käännöksen leikepöydälle
	
#### pikanäppäimet  
- pikanäppäimet helpottavat ja nopeuttavat ohjelman käyttämistä  
- tällä hetkellä tuettuina ovat:  
<kbd>Ctrl</kbd> + <kbd>Shift</kbd> + <kbd>Q</kbd> > pikakääntö  
<kbd>Ctrl</kbd> + <kbd>Shift</kbd> + <kbd>D</kbd> > pikakääntö + derivaatta  
<kbd>Ctrl</kbd> + <kbd>Shift</kbd> + <kbd>S</kbd> > pikakääntö + autosolve  
<kbd>Ctrl</kbd> + <kbd>Shift</kbd> + <kbd>N</kbd> > pikakääntö + oletusasetukset  
<kbd>Ctrl</kbd> + <kbd>Enter</kbd> + painettuna syötelaatikossa > käännös  

#### lisäasetukset (vähempipätöiset)
##### poista aaltosulut
	- poistaa ylijääneet aaltosulut kaavoista
	- kannattaa pitää aina päällä ongelmien välttämiseksi

##### muuta erikoismerkit
	- muuttaa vakiot i ja e muotoon @i ja @e (imaginääriyksikkö ja neperin luku)
	- oletuksena pois päältä

##### viimeistely
	- poistaa tyhjät potenssit ja jakolaskut, jotka jäävät yli fysiikkatilan yksiköiden poistamisen jälkeen
	- oletuksena päällä

## asetusten tallentaminen uusia versioita varten
- voit tallentaa sovelluksen asetukset mek.config.json tiedostoksi valitsemalla 
- asetukset > lisäasetukset > vie mek datasi > vie
- sovellus tallentaa tällöin haluamasi asetukset local appData -kansioon, josta uusi versio voi lukea ne helposti 

## sovelluksen poistaminen
	1) sovelluksen voit poistaa etsimällä sen tallennuspaikan
		- oletus: "C:\Program Files (x86)\Matikkaeditorinkaantaja\unins000.exe"
	2) käynnistä tiedosto "unins000.exe"
	3) seuraa ohjeita
  
  
## päivitykset
	- ohjelmisto ei toistaiseksi päivitä itse itseään tai ilmoita uusista saatavilla olevista päivityksistä
	- uudet versiot tulee ladata Githubista ja asentaa asennusohjelmalla
	- päivitykset kannattaa tarkistaa 1-2 kk välein
	- uudet päivitykset tuovat parannuksia algoritmeihin, käyttöliittymään, sekä sovelluksen toimivuuteen 

## Ohjeita ja muita tiedostoja  

uusimmat versiot tiedostoista löytyvät aina netistä
merkkimuutokset löytyvät [täältä](https://docs.google.com/spreadsheets/d/1bi-iejOZ7LSQXTja8hWFj7LcgKMt4z3Aa5pRelak9R8/edit?usp=sharing)  
käyttöehdot läytyvät [täältä](https://docs.google.com/document/d/1m952YhMxpN6ihcMfVcO7xJ0TYGzwajvvKJLnzftqdz0/edit?usp=sharing)  
visuaalinen versio README tiedostosta [täältä](https://docs.google.com/document/d/1akGTKmWnCJrbmtH4gM1ucTExSKc3ipGZCM-l1wJatUQ/edit)  
tämän tiedoston uusin versio [täältä](https://github.com/matikkaeditorinkaantaja/Matikkaeditorinkaantaja#readme)  
raportoi bugeista tai anna ehdotuksia [täällä](https://github.com/matikkaeditorinkaantaja/Matikkaeditorinkaantaja/issues) tai lähetä sähköpostia
  
  
  
Tiedosto päättyy!   kiitos jos luit!  :) 
  
  
  
#### Yhteystiedot:
  
Henri Vainio  
Sähköposti: matikkaeditorinkaantaja(at)gmail.com  
Github: https://github.com/matikkaeditorinkaantaja
