# Mallipohjainen-testaus-harkka
Intel fmbt model based tesing course work

TTY ohjelmistojen testauksen kurssin vapaaehtoinen harkkatyö, jossa testattiin linux galculator laskinta. Harjoituksessa rakennettiin automatisoitu mallipohjainen testisetti intelin fMBT työkalulla. FMBT:llä voidaan rakentaa tilakonemaisia kokonaisuuksia python ja aal komentokielen avulla. Näitä tiloja hyödyntäen ohjelma testaa mahdollisten tilavaihtoehtojen toiminta. Ohjelma testaa +, -, / ja * laskut syöttämällä ne laskimelle ja tarkistamalla että tulokset vastaavat taustalla laskettuja tuloksia. Ohjelma näyttää reaaliaikaisesti testin etenemisen ja kuinka toiminnot reagoivat painalluksiin. Lisäksi siihen ohjelmoin sen näyttä mään välituloksia ja tulostamaan tiedostoon luvut jotka tunnistettiin oikein ja väärin. Tämä siksi että fMBT:n OCR tunnistaa huonosti lukuja ja saatua tulosta pystyi hyödyntämään testimallin rakennus vaiheessa. Vaikka harjoituksesta täydet pisteet sainkin ei se kuitenkaan toimi täysin halutulla tavalla. fMBT:n aiheuttamien hankaluuksien vuoksi en kerennyt saamaan laskusääntojä tarkistussumineen toimimaan täysin oikein.

Testit tehty Linux ubuntu käyttöjärjestelmässä.

YMPÄRISTÖN ASENTAMINEN JA VARMENTAMINEN
fMBT asennus (https://01.org/fmbt)
sudo apt-add-repository ppa:antti-kervinen/fmbt-devel; sudo apt-get update; sudo apt-get install fmbt

Xephyr ikkunointien hallintaan
Sudo apt-get install xserver-xephyr

Varmistetaan asennettujen komponenttien toimivuus ajamalla komennot.
Xephyr -screen 1100/220x900/180 :177351 &
Env DISPLAY=:177351 gedit &
Python
Import fmbtx11
s=fmbtx11.Screen(‘:177351’)
Virheitä ei saa tulostua
help(s) ja dir(s) näyttävät luodun olion toiminnallisuuksia.
Tulkin voi sulkea(ctrl+d) ja Xephyr ikkunan voi sulkea.

TESTIEN AJAMINEN
Ladataan tiedostot gitistä.
Navigoidaan kansioon, jossa galculator.py.aal ja laaja.conf tiedostot sijaitsevat terminaalissa.
Suoritetaan komento fmbt laaja.conf

TESTIEN TARKASTELU
fMBT omat työkalut testien rakentamiseen ja tarkasteluun
fmbt-editor galculator.py.aal laaja.conf

galculator.py.aal tiedostoa voi muokata millä tahansa editorilla, mutta editori kannattaa kuitenkin aukaista taustalle vivulla -P. Tällöin tilakonemallia voi edelleen hyödyntää.
fmbt-editor -P galculator.py.aal laaja.conf
