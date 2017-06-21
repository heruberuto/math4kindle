# Rešerš převodu matematických výukových textů do Kindle a šablonový převod linal2.tex

Rešeršně-aplikovaný projekt odevzdávaný veřejně jako semestrální práce pro předmět [Typografie a TeX](http://petr.olsak.net/typotex.html)

## Úvod, cíle práce
Amazon Kindle a jiné čtečky e-knih obstály v testu časem, je třeba je brát na vědomí
jako významné médium (neřkuli platformu budoucnosti) pro typografii jako takovou.

Cílem projektu je prozkoumat možnosti návrhu sazby pro matematické skriptum (nebo zadání D.Ú., zápisy z přednášek,..).
Ideálně najít šablonové (a částečně Ad hoc) řešení na převod existujícího materiálu v TeXu do Kindle. 

Vedlejším cílem je aplikace získaných poznatků na převod existujících skript 
[Lineární algebra 2](http://petr.olsak.net/ftp/olsak/linal/linal2.pdf) od RNDr. Petra Olšáka do autorova zařízení Amazon Kindle.

## Motivace
Mnoho studentů matematických oborů vlastní čtečku e-knih, nebo mobilní zařízení schopné podávat sazbu podobným způsobem,
avšak výukové materiály vyžadující kvalitní matematickou sazbu tuto platformu téměř nikdy nepodporují.

Z toho plyne nutnost existující dokumenty zoomovat, pohybovat se po stránce zleva doprava (na každém řádku znovu) a jiné nevýhody, které dělají
tento způsob studia takřka nepoužitelným.

Sám autor projektu zápasí s dlouhými hodinami času ztraceného na cestách mezi svým domovem, Prahou a jinými destinacemi,
kde by bylo vítáno přečíst si zajímavé materiály a zároveň osvěžit své znalosti, ale málokdy si vozí skripta.

Většina výukových materiálů používajících matematickou sazbu je psána v (La)TeXu a autoři zdrojový kód na požádání uvolní čtenáři.
K tomu se skripta a výuka, která čtenáře zajímá, velmi rychle mění a časově se mu nevyplácí každý materiál ad hoc převádět.
Ideálním výstupem projektu by tedy bylo šablonové řešení, které umožní snadno přeformátovat existující materiál v TeXu snadno a
 rychle do formátu příjemně čitelného v Kindle.
 
## Otázky k prozkoumání
- Je možno použít nativní Kindle formát k publikaci matematických materiálů?
- Jak dobře zvládá Kindle formát PDF? (odkazy, obsah, meta-tagy)
- Je možný šablonový převod, nebo je újma na čitelnosti neúnosná?

## Objevené problémy
### Nativní formáty čteček a matematická sazba
Přestože jsou formáty .epub a .mobi skvěle provázané s vnitřní funkcionalitou zařízení (odkazy uvnitř fungují, obrázky se natahují dle rozměrů, na obsah lze skočit tlačítkem),
o matematickou sazbu se příliš nestarají.

Po několika pokusech a kontrolách [komunity](https://forums.createspace.com/en/community/message/164683) vyplývá najevo, že
nativním *best practice* řešením je převod vší matematické sazby na obrázky. To by bylo dobré řešení při snaze o profesionální převod
*jednoho* daného skripta, ale pro agilní převod mnoha materiálů je to příliš práce.

### Kindle a PDF
Možnosti čtení PDF v Kindle jsou oproti nativním formátům výrazně ořezaná. Dokumenty lze listovat, automaticky se oříznou prázdné okraje,
ovšem [odkazy](https://www.mobileread.com/forums/showthread.php?t=122219) a navigaci v dokumentu většina zařízení při četbě PDF naprosto zablokuje (možno je jen skočit na číslo stránky).

Čitelnost klesá se stoupající velikostí formátu dokumentu (samozřejmě), součástí *GUI* čteček je číslo stránky, zbytečně zdvojuje
číslo, které je součástí dokumentu.

Matematické výpočty mají tendenci táhnout se "do šířky", velikost Kindlu (zhruba A6) je v otočení na výšku často nepoužitelná.

### Náklady na převod existujícího materiálu
Převod mnohastránkového skripta v TeXu na tak malý formát při zachování profesionální typografie vyžaduje příliš mnoho času.

## Zvolená řešení
### Formát
PDF umožní pokročilou matematickou sazbu, to je pro nás zásadní.
## Produkty

## Závěr

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

///Přestože jsou čtečky a jejich vstupní formáty vybaveny desítkami funkcionalit
   jak pro kvalitu sazby, tak pro uživatelskou přívětivost (ligatury, odkazy, skoky podle názvů kapitol aj.)
   matematickou sazbu stále neumějí.