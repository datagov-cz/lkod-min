# Minimalistický lokální katalog otevřených dat
Toto je minimalistická verze lokálního katalogu otevřených dat, která celá běží na GitHubu, a tedy zdarma.
Je kompatibilní s [rozhraním DCAT-AP Dokumenty](https://ofn.gov.cz/rozhraní-katalogů-otevřených-dat/2021-01-11/#dcat-ap-dokumenty) dle [Otevřené formální normy Rozhraní katalogů otevřených dat: DCAT-AP-CZ](https://ofn.gov.cz/rozhraní-katalogů-otevřených-dat/2021-01-11/).
Pro její zprovoznění stačí tento repozitář [forknout](https://docs.github.com/en/github/getting-started-with-github/fork-a-repo) a upravit [šablonu katalogu](katalog-šablona.jsonld).

## Záznamy datových sad
Pro přidání či editaci záznamu použijte [formulář NKOD v režimu LKOD](https://data.gov.cz/formulář/registrace-datové-sady).
Režim se přepíná ikonou ozubeného kolečka vedle tlačítka stažení vyplněného záznamu.
Tam je také potřeba vyplnit IRI poskytovatele a IRI datové sady. Výsledný soubor uložte do repozitáře.
Uložení automaticky spustí [GitHub Action](https://github.com/features/actions), která repozitář projde, a vytvoří [soubor katalogu](katalog.jsonld) na základě [šablony](katalog-šablona.jsonld) a nalezených datových sad.

### IRI datových sad
Je třeba se ujistit, že IRI datové sady vyplněné v záznamu na tento záznam po jeho uložení do repozitáře povede.
V tomto repozitáři je vzorová datová sada, jejíž IRI je `https://raw.githubusercontent.com/opendata-mvcr/lkod-min/main/datové-sady/datová-sada.jsonld`.
Toto IRI zjistíte po kliknutí na tlačítko `Raw` při prohlížení souboru přes rozhraní GitHub.
Skládá se vždy z `https://raw.githubusercontent.com/`, `organizace/`, `repozitář/`, `jméno-větve/`, `cesta k souboru v repozitáři`.

Tato IRI datových sad lze také použít pro opětovné načtení záznamu do [formuláře NKOD](https://data.gov.cz/formulář/registrace-datové-sady) pro jeho editaci.
Ve formuláři staří v prvním kroku dole kliknout na "Načíst záznam z URL", a IRI datové sady tam vyplnit.

### IRI katalogu
Při [registraci lokálního katalogu do NKOD](https://data.gov.cz/formulář/registrace-lokálního-katalogu) pak stačí zvolit jako Typ API lokálního katalogu `DCAT-AP Dokumenty` a do URL LKOD API vyplnit URL [souboru katalogu](katalog.jsonld) podobně, jako pro datové sady, tedy např. `https://raw.githubusercontent.com/opendata-mvcr/lkod-min/main/katalog.jsonld`

## GitHub Pages
Pokud by takováto IRI datových sad nevyhovovala, lze tuto minimalistickou variantu LKOD rozšířit o [GitHub Pages](https://pages.github.com/), které umožňují použít vlastní IRI katalogu a datových sad, dokonce i s vlastní doménou, např. `https://data.organizace.cz/zdroj/datové-sady/1.jsonld`.

GitHub pages zároveň umožňují hostovat i webovou prezentaci, jejíž součástí pak LKOD může být.
