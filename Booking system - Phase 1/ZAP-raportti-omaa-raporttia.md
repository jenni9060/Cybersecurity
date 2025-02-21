# Penetraatiotestaus

## Johdanto

Tämän raportin tarkoituksena oli suorittaa booking system ohjelmaan penetraatio testausta. Työssä käytettiin Zaproxy-ohjelman manuaalisia
ja automaattisia testausmenetelmiä. Lisäksi testaaja itse tutki ohjelmaa ja pyrki etsimään siitä heikkouksia.
Testaus suoritettiin 20.02.2025 ja testausympäristönä toimi virtuaalikoneeseen asennettu KaliOS. Kaliin asennettiin Zaproxy-ohjelma ja
ohjelmassa käytettiin myös HUD-työkalua.

## Yhteenveto

**Keskeisiä löydöksiä**

- Salasanoja ei oltu salattu tietokannassa
- SQL injektio mahdollinen
- Polun kulkuhaavoittuvuus

Edellä mainittuihin haavoittuvuuksiin tulisi kiinnittää välittömästi huomiota parantaakseen palvelun tietoturvaa. Jos hyökkääjä
esimerkiksi tekee SQL injektiohyökkäyksen, hän voi helposti saada käsiinsä käyttäjien salasanat, jotka eivät ole edes salattuja,
joten niitä olisi helppo sen jälkeen käyttää ja päästä käsiksi salassapidettäviin tietoihin.

Mielestäni tietoturvan tila ei ole hyvä näiden puutteiden vuoksi.




### Haavoittuvuudet

**Korkea riski - Punainen**

- Salasanoja ei ole salattu tietokannassa
    * Jos tietokanta vuotaa (esim. SQL-injektion kautta), hyökkääjä voi saada suoraan selkokieliset salasanat haltuunsa. Myös pahantahtoiset työntekijät tai muut, joilla on pääsy tietokantaan, voivat helposti lukea ja väärinkäyttää käyttäjätietoja.

- Polun kulkuhaavoittuvuus (Path Traversal)
    * Polun kulkuhaavoittuvuuden avulla hyökkääjä voi päästä käsiksi tiedostoihin, hakemistoihin ja komentoihin, jotka sijaitsevat mahdollisesti verkkodokumenttien juurihakemiston ulkopuolella. Hyökkääjä voi manipuloida URL-osoitetta siten, että verkkosivusto suorittaa tai paljastaa minkä tahansa palvelimella sijaitsevan tiedoston sisällön. Kaikki HTTP-pohjaista käyttöliittymää käyttävät laitteet voivat olla alttiita tälle haavoittuvuudelle.


- SQL Injektio
    * SQL-injektio voi olla mahdollinen. Parametrin arvoa muokattaessa sitä ei poistettu HTML-lähtötiedosta vertailun yhteydessä. Alkuperäiselle parametriarvolle palautettiin dataa. Haavoittuvuus havaittiin, kun onnistuttiin rajoittamaan alun perin palautettua dataa manipuloimalla parametria.

   

**Keskisuuri riski - Keltainen**

- Content Security Policy (CSP) -otsaketta ei ole asetettu
    * Content Security Policy (CSP) on suojaustoiminto, joka auttaa estämään hyökkäyksiä, kuten Cross Site Scripting (XSS) ja tietojen injektoinnin, määrittelemällä luotettavat sisällön lähteet. Ilman CSP-otsaketta sovellus on haavoittuvainen näille hyökkäyksille, jolloin haitallinen sisältö voi suorittua tai tulla injektoiduksi. Tämä voi johtaa tietovarkauksiin, verkkosivun turmeltumiseen tai haittaohjelmien levittämiseen.

- Puuttuva Anti-clickjacking-otsake
    * Vastaus ei suojaa ’ClickJacking’-hyökkäyksiä vastaan. Sen tulisi sisältää joko Content-Security-Policy, jossa on ’frame-ancestors’-direktiivi, tai X-Frame-Options.


### Poikkeamat

**Matala riski - Vihreä**

- Sovelluksen virheilmoitusten paljastaminen
    * Sivulla on virhe-/varoitusviesti, joka saattaa paljastaa arkaluontoisia tietoja, kuten sen tiedoston sijainnin, joka tuotti käsittelemättömän poikkeuksen. Tätä tietoa voidaan käyttää hyökkäyksien kohdentamiseen verkkosovellusta vastaan. Tämä varoitus voi olla väärä hälytys, jos virheilmoitus löytyy dokumentaatiosivulta.
    
- X-Content-Type-Options-otsake puuttuu
    * Anti-MIME-sniffing-otsaketta X-Content-Type-Options ei ole asetettu arvoon ’nosniff’. Tämä mahdollistaa vanhempien Internet Explorer- ja Chrome-versioiden suorittaman MIME-sniffauksen vastauksen sisällöstä. Tämä voi johtaa siihen, että sisältö tulkitaan ja esitetään eri sisältötyyppinä kuin mikä on ilmoitettu. Nykyiset (vuoden 2014 alun) ja vanhemmat Firefox-versiot käyttävät ilmoitettua sisältötyyppiä (jos sellainen on asetettu) MIME-sniffauksen sijaan.












