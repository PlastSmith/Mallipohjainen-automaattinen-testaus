# Mallipohjainen-automaattinen-testaus
Intel fmbt model based tesing course work<br>

TTY ohjelmistojen testauksen kurssin vapaaehtoinen harkkatyö, jossa testattiin linux galculator laskinta. Harjoituksessa rakennettiin automatisoitu mallipohjainen testisetti intelin fMBT työkalulla. FMBT:llä voidaan rakentaa tilakonemaisia kokonaisuuksia python ja aal komentokielen avulla. Näitä tiloja hyödyntäen ohjelma testaa mahdollisten tilavaihtoehtojen toiminta. Ohjelma testaa +, -, / ja * laskut syöttämällä ne laskimelle ja tarkistamalla että tulokset vastaavat taustalla laskettuja tuloksia. Ohjelma näyttää reaaliaikaisesti testin etenemisen ja kuinka toiminnot reagoivat painalluksiin. Lisäksi siihen ohjelmoin sen näyttä mään välituloksia ja tulostamaan tiedostoon luvut jotka tunnistettiin oikein ja väärin. Tämä siksi että fMBT:n OCR tunnistaa huonosti lukuja ja saatua tulosta pystyi hyödyntämään testimallin rakennus vaiheessa. Vaikka harjoituksesta täydet pisteet sainkin ei se kuitenkaan toimi täysin halutulla tavalla. fMBT:n aiheuttamien hankaluuksien vuoksi en kerennyt saamaan laskusääntojä tarkistussumineen toimimaan täysin oikein.<br>

Testit tehty Linux ubuntu käyttöjärjestelmässä.<br><br>

YMPÄRISTÖN ASENTAMINEN JA VARMENTAMINEN<br>
fMBT asennus (https://01.org/fmbt)<br>
sudo apt-add-repository ppa:antti-kervinen/fmbt-devel; sudo apt-get update; sudo apt-get install fmbt<br>

Xephyr ikkunointien hallintaan<br>
Sudo apt-get install xserver-xephyr<br>

Varmistetaan asennettujen komponenttien toimivuus ajamalla komennot.<br>
Xephyr -screen 1100/220x900/180 :177351 &<br>
Env DISPLAY=:177351 gedit &<br>
Python<br>
Import fmbtx11<br>
s=fmbtx11.Screen(‘:177351’)<br>
Virheitä ei saa tulostua<br>
help(s) ja dir(s) näyttävät luodun olion toiminnallisuuksia.<br>
Tulkin voi sulkea(ctrl+d) ja Xephyr ikkunan voi sulkea.<br><br>

TESTIEN AJAMINEN<br>
Ladataan tiedostot gitistä.<br>
Navigoidaan kansioon, jossa galculator.py.aal ja laaja.conf tiedostot sijaitsevat terminaalissa.<br>
Suoritetaan komento fmbt laaja.conf<br><br>

TESTIEN TARKASTELU<br>
fMBT omat työkalut testien rakentamiseen ja tarkasteluun<br>
fmbt-editor galculator.py.aal laaja.conf<br>

galculator.py.aal tiedostoa voi muokata millä tahansa editorilla, mutta editori kannattaa kuitenkin aukaista taustalle vivulla -P. Tällöin tilakonemallia voidaan edelleen hyödyntää.<br>
fmbt-editor -P galculator.py.aal laaja.conf<br>
