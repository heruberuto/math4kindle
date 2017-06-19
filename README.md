# Matematická sazba a TeX vs. Kindle

Rešeršně-aplikovaný projekt odevzdávaný veřejně jako semestrální práce pro předmět [Typografie a TeX](http://petr.olsak.net/typotex.html)

## Motivace
Amazon Kindle a kapesní čtečky knih obstály mezi ostatními technickými výstřelky v testu časem, je třeba je brát na vědomí jako významné médium (neřkuli platformu budoucnosti) pro typografii jako takovou.

Přestože jsou čtečky a jejich vstupní formáty vybaveny desítkami funkcionalit,
jak pro kvalitu sazby, tak pro uživatelskou přívětivost (ligatury, odkazy, skoky podle názvů kapitol aj.)
matematickou sazbu stále neumějí.

Cílem je navrhnout sazbu pro matematické skriptum (nebo zadání domácího úkolu, zápis z přednášky aj.),
které bude brát co možná nejvíce z vlastností žádoucích pro čtení v Kindlu (čitelnost na malé obrazovce, úzké okraje,
 správné meta-informace, kontextové vyhledávání aj.) při zachování kvalitní matematické sazby TeXu.

Vedlejším cílem je převod existujících skript [Lineární algebra 2](http://petr.olsak.net/ftp/olsak/linal/linal2.pdf) od RNDr. Petra Olšáka
pro prozkoumání rozšiřitelnosti takové sazby na existující matematickou literaturu v TeXu.
## Náplň projektu
Prozkoumat možnosti, jak udělat PDF co nejpřívětivější pro čtení v různých kapesních čtečkách a navrhnout konkrétní TeX vzor,
který těchto možností využívá a je snadné převést do něj existující texty.
### Možnosti Kindle k prozkoumání
- GUI kindle vypisuje číslo stránky, umí také začít s číslováním až po obsahu a obálce (stránka 1 je na 7. obrazovce) - lze toto s PDF?
- GUI kindle zobrazuje "progress-bar" (lištu vybarvující se podle toho, jak daleko v knize čtenář je) se zarážkami dle kapitol - lze v PDF?
- Kindle umožňuje skočit na Obsah - Lze v PDF?
- PDF dokumenty stažené do Kindle tradičně nemají dostatečné meta-informace (Název knihy = název PDF souboru, autor = neznámý), jak je zadávat?
- Existující matematická skripta mohou používat složitá vlastní formátování, obrázky, tabulky, makra. Lze položit univerzální makra, která by
je umožnila co možná jednoduše přeformátovat?

## Licenční ujednání
GNU General Public License, prvky kódu, nikoli však skript p. Olšáka, může využívat každý dle libosti.
Účelem je osvěta, nikoli zisk.