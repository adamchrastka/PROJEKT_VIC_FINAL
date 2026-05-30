Povedly se mi velmi špatný věci s tím udělat tak jsem radši smazal celý repozitář, protože to github nechtěl zpracovat. 


Puvodni slozka na projekt: https://github.com/adamchrastka/projekt_1
presunul jsem to kvuli xampp, abych mohl zaroven mit zapnute veci v hodinach a zaroven projekt a nemusel nic predelavat ve slozkach.

Projekt mám celou dobu uložený na svém notebooku, tedy lokálně. V několika hodinách to mohl i vyučující,
i ostatní žáci postřehnout. Github jsem používal pouze ze začátku, během doby kdy jsem neměl notebook a 
pracoval částečně ve škole přes Horizon a částečně na mém dočasném notebooku. 



Dokumentace projektu - Autoskola system
Autor: Adam Chrastka

Tady budu psát poznámky k projektu.

Webová aplikace napsaná v PHP, HTML a CSS
Běží na XAMPP, nebo na webu

Co tento projekt řeší?
Projekt je navržen jako záznamový a informační systém pro žáky a instruktory autoškoly.


Struktura souborů
<img width="424" height="622" alt="obrazek" src="https://github.com/user-attachments/assets/f0440c17-93c9-4100-8521-c2bc12e110fe" />

Spusteni

1. Spustit XAMPP (Apache + MySQL)
2. Zkopírovat složku projektu do C:/xampp/htdocs/
3. Otevřít prohlížeč a jít na http://localhost:80 a doklepat se do požadované složky
4. Databáze se vytvoří sama při prvním načtení - není potřeba nic importovat


PRIHLASOVANI

Heslo tady psát nebudu. Děkuju, nestojím o návštevu
Defaultne je heslo admin k adminovi a user k uzivateli

Databáze se jmenuje "autoskola" a vytvoří se automaticky.

Tabulky:
- users       ... uživatelé systému (admini a uživatelé)
- students    ... studenti autoškoly (jméno, příjmení, datum narození, tel, email, prospěl)
- instructors ... instruktoři (jméno, příjmení, tel, email)
- vozidla     ... vozový park (značka, model, SPZ, rok výroby, barva, palivo, převodovka)
- jizdy       ... záznamy jízd (student, instruktor, vozidlo, datum, čas)

ID studentů zůstává beze změn i po vymazání studenta.
Pokud by došlo ke změně, tak bude student zmatený a databáze taky.

Při smazání studenta, instruktora nebo vozidla se automaticky smažou
i všechny jejich jízdy.
<img width="1296" height="1023" alt="obrazek" src="https://github.com/user-attachments/assets/f79e59dd-f681-4d2a-9de0-86dca7cc27bc" />


ROLE A OPRAVNENI

Všechny stránky jsou ověřené přes session a role pro jednotlivé uživatele,
a tyto role určují, co uživatel uvidí. Zabezpečují, že se do systému nedostanete i pouze přes link.

Uživatelé vidí pouze tabulky s vozidly, jízdami a instruktory.

Administrátoři vidí tabulky s vozidly, jízdami atd. a u nich také
možnost smazat či upravit danou část.

Funkce
Instruktoři (admin) mohou přidávat / odebírat / upravovat jednotlivé věci v závislosti na stránce kde právě jsou.
Studenti (user) si mohou zobrazit tabulky s pro ně užitečnými informacemi
PREHLED STRANEK

Ukázky stránek
LOGIN
<img width="2559" height="1466" alt="obrazek" src="https://github.com/user-attachments/assets/a1e3c647-1843-400b-8c14-0ad63a95b548" />
Admin panel
<img width="2559" height="1473" alt="obrazek" src="https://github.com/user-attachments/assets/b6942d90-2733-4077-8f96-55f27fd55d91" />
Uživatelská stránka
<img width="2559" height="1471" alt="obrazek" src="https://github.com/user-attachments/assets/fda0a017-fd87-4e97-a413-0b75b586a093" />



index.php       přihlašovací stránka
admin.php       hlavní stránka administrátora
students.php    správa studentů (jen admin)
uzivatele.php   správa uživatelů systému (jen admin)
instructors.php správa instruktorů
vozidla.php     správa vozidel
jizdy.php       správa jízd
db.php          připojení k databázi + automatické vytvoření tabulek

POZNAMKY
- Projekt je školní, hesla jsou jednoduchá záměrně
- CSS styly jsou sdílené pro celý projekt (styles.css). Neviděl jsem důvod, dělat pro každou stránku zvlášť.
- Projekt běží lokálně na XAMPPu, není nasazený na server.
