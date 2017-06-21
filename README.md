# Rešerše převodu matematických výukových textů do Kindle a šablonový převod linal2.tex

Rešeršně-aplikovaný projekt [**Herberta Ullricha**](mailto:herbert.ullrich@yeti-studio.cz) odevzdávaný veřejně jako semestrální práce pro předmět [Typografie a TeX](http://petr.olsak.net/typotex.html)

## Úvod, cíle práce
Amazon Kindle a jiné čtečky e-knih obstály v testu časem, je třeba je brát na vědomí
jako významné médium (neřkuli platformu budoucnosti) pro typografii jako takovou.

Cílem projektu je prozkoumat možnosti návrhu sazby pro matematické skriptum (nebo zadání D.Ú., zápisy z přednášek,..).
Ideálně najít šablonové řešení na převod existujícího materiálu v TeXu do Kindle. 

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
Ovšem skripta a výuka, která čtenáře zajímá, se velmi rychle mění a časově se mu nevyplácí každý materiál ad hoc převádět.

Ideálním výstupem projektu by tedy bylo šablonové řešení, které umožní snadno přeformátovat existující materiál v TeXu snadno a
 rychle do formátu příjemně čitelného v Kindle.
 
## Otázky k prozkoumání
- Je možno použít nativní Kindle formát k publikaci matematických materiálů?
- Jak dobře zvládá Kindle formát PDF? (odkazy, obsah, meta-tagy)
- Je možný šablonový převod, nebo je újma na čitelnosti neúnosná?

## Problémy
### Nativní formáty čteček a matematická sazba
Přestože jsou formáty *.epub* a *.mobi* skvěle provázané s vnitřní funkcionalitou zařízení (odkazy uvnitř fungují, obrázky se natahují dle rozměrů, na obsah lze skočit tlačítkem),
o matematickou sazbu se příliš nestarají.

Po několika pokusech a kontrolách [komunity](https://forums.createspace.com/en/community/message/164683) vyplývá najevo, že
nativním *best practice* řešením je převod vší matematické sazby na obrázky. To by bylo dobré řešení při snaze o profesionální převod
*jednoho* daného skripta, ale pro agilní převod mnoha materiálů je to příliš práce.

### Kindle a PDF
Možnosti čtení PDF v Kindle jsou oproti nativním formátům výrazně ořezané. Dokumenty lze listovat, automaticky se oříznou prázdné okraje,
ovšem [odkazy](https://www.mobileread.com/forums/showthread.php?t=122219) a navigaci v dokumentu většina zařízení při četbě PDF naprosto zablokuje (možno je jen skočit na číslo stránky).

Čitelnost klesá se stoupající velikostí formátu dokumentu (samozřejmě), součástí *GUI* čteček je číslo stránky, zbytečně zdvojuje
číslo, které je součástí dokumentu.

Matematické výpočty mají tendenci táhnout se "do šířky", velikost Kindlu (zhruba A6) je v otočení na výšku často nepoužitelná.

### Náklady na převod existujícího materiálu
Převod mnohastránkového skripta v TeXu na tak malý formát při zachování profesionální typografie vyžaduje příliš mnoho času.

### Nemožnost šablonového řešení
Každý typograf sází jinak, převod je vždy nutno dělat jinak, nebo bude výsledek suboptimální.
## Použitelné technologie
Vzhledem k selhání nativních formátů při sázení matematiky bude nutno se spokojit pouze s úpravami rozložení textu.
### PDF
- TeX je přímo generuje
- Kvalitní mat. sazba je prioritou oproti spolupráci s uživatelským rozhraním čtečky
- Nutnost pracovat na šířku, ignorovat okraje, čísla stránek
### Makra vyňatá z [OPMac](http://petr.olsak.net/opmac.html)
- Vhodně implementují změnu formátu stránky
- Při tvorbě nových materiálů použit OPMac jako celek, usnadňuje psaní zápisu aj.

## Produkty
Při rešerši vzniklo několik experimentálních produktů. Najdete je ve složkách [tex](tex) a 
[pdf](pdf).
### Makra [kindlify.tex](tex/kindlify.tex)
Poskytují několik nástrojů, jak si jednoduše vynutit základní Kindle uživatelskou přívětivost.
- `\input kindlify` lze vložit těsně nad začátek textu Lineární algebry, čímž se přepíšou nehodící se makra na prázdná
- `\kindlify{portrait}` změní velikost dokumentu na rozměry Kindle obrazovky na stojato. Podobně fungují `\kindlify{landscape}`, `\kindlify{kindleDXportrait}`, a `\kindlify{kindleDXlandscape}`.
- `\setauthor{JMENO}` nastaví tag autor (jediná metadata, která Kindle čte) na hodnotu `JMENO`

### Zápisový vzor [template.tex](tex/template.tex)
V podstatě převzaté demo OPMacu, nápadem bylo vyzkoušet takovou šablonu zbudovat pro vertikální zobrazení v Kindlu 
(je příjemnější na obracení stránek) a inspirovat čtenáře-zapisovatele možnostmi, jaké v tomto rozvolněném formátu má.

- Výsledek TeXu v [template.pdf](pdf/template.pdf)
- Lze používat OPMac
- Lze měnit formát stránky dle různých čteček
- Nebyl řádně testován, představa je taková, že tvůrce bude znát limity zobrazení na Kindlu a tvořit podle nich

### Existující skriptum [linal2.tex](tex/linal2.tex)
Účelem bylo pozměnit existující skriptum tak, že pouhým odkomentováním jednoho řádku se totožný sobour vykreslí pro Kindle, 
naopak jeho zakomentováním bude vykreslován pro svůj standardní formát
- Výsledek TeXu pro `\kindletrue` v [linal2.pdf](pdf/linal2.pdf)
- Vyžaduje opravy. Suboptimální řešení. Spousta `underfull` a `overfull` hlášení, některé chyby bijí do očí
- Původní záměr skriptum profesionálně převést se mi nezdařil, bylo by to velmi náročné
- Přesto lze poměrně slušně použít k učení se na kindlu 
- Ponechána barevnost skript, je velmi užitečná při čtení na smartphone

## Závěr
Portovat existující skripta do Kindle je velmi náročné. Spokojíme-li se se suboptimálním řešením, je možno ho pomocí produktů této rešerše získat velmi rychle.

Také se ukazuje, že listování velkým množstvím informací, které na sebe referují
je na pomalé čtečce lehce neohrabané. Eventuelní řešení by mohlo spočívat v exportu stručnějších výcuců nebo přednáškových archů.
Existující výcuc `linal-s.tex` se bohužel mezi produkty k přeformátování nedostal, neboť vykazuje chyby při vykreslování.

Produktem práce jsou tedy bohužel především informace o omezeních a ústupcích, které je třeba udělat.