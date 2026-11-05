# minecraft SMP

Sdílená video knihovna bez vlastního serveru. Každý hráč má videa ve své složce a ostatní si je přehrávají přímo z jeho počítače (WebRTC přes PeerJS).

## Zveřejnění zdarma na GitHub Pages

1. Na github.com si založ nový veřejný repozitář, třeba `onion-smp`.
2. Nahraj do něj soubor `index.html` (Add file → Upload files → Commit).
3. Settings → Pages → Source: „Deploy from a branch“, Branch: `main`, složka `/ (root)` → Save.
4. Za minutu bude aplikace na adrese `https://<tvuj-ucet>.github.io/onion-smp/`.

Aplikace musí běžet přes https (GitHub Pages to splňuje). Z disku přes `file://` spolehlivě nepoběží.

## První spuštění

- **Ty (zakladatel):** otevři adresu, zvol „Založit skupinu“, zadej jméno, název skupiny a kód admina, vyber složku. Pak v Nastavení zkopíruj pozvánku.
- **Ostatní hráči:** otevřou pozvánku, zadají jméno a vyberou svou složku. Při prvním připojení musí mít pozvávající aplikaci otevřenou.
- **Práva admina:** tlačítko Admin → zadat kód. Admin si může založit **vlastní SMP** (sloupec „Založit moje SMP“), dát mu obrázek na pozadí a nahrávat do něj videa. Hráči bez kódu se jen dívají.
- **Až 3 vlastní SMP:** každý hráč se schváleným SMP si jich může založit nejvýš 3 a kdykoli je smazat (Otevřít → Upravit SMP → Smazat SMP).
- **Super admin erik3d:** admin se jménem `erik3d` se při prvním přihlášení jako admin zapíše do skupiny jako super admin. Může smazat cizí SMP, sekce i videa. Tuhle roli pak už nikdo jiný převzít nemůže.
- **Vzhled:** moderní rozhraní s bočním menu a stínovanými pixelovými ikonami. V Nastavení si každý vybere **Tmavý** nebo **Světlý** vzhled a jednu z 5 barev (Zlatá, Smaragdová, Diamantová, Rudá, Ametystová). Výchozí je Tmavý a Smaragdová. Volba platí jen pro jeho prohlížeč.
- **Vzhled vlastního SMP:** majitel SMP otevře své SMP → „Vzhled SMP“. Nahoře vybere motiv (Výchozí, Les, Nether, End, Jeskyně, Sníh, Oceán) a dole doladí hlavní barvu, pozadí (Světlé, Tmavé, Barevné, Obrázek), písmo názvu, rozložení videí (Dlaždice, Velké, Seznam), obrázek a efekt v hlavičce (sníh, listí, uhlíky, částice, bubliny). Vpravo je živý náhled stránky i karty. Vzhled se uloží do podepsaného záznamu SMP a uvidí ho všichni hráči. Ukládají se jen předem dané volby a barvy, žádný vlastní kód.
- **Rozložení stránky SMP přetažením:** v editoru vzhledu (krok 3) jde myší nebo prstem přetáhnout bloky stránky (Videa a sekce, O tomhle SMP, Admin, Naposledy přidané) mezi Hlavní část, Boční panel a Skryté. Boční panel jde dát vlevo nebo vpravo a přetažením se mění i pořadí sekcí (záložek). Videa skrýt nejdou. Na klávesnici: šipky nahoru a dolů mění pořadí, doleva a doprava přesouvají blok jinam.
- **Postavička super admina:** erik3d si v Nastavení načte skin (PNG 64 × 64 px jako v Minecraftu). Postavička stojí ve 3D vlevo nahoře vedle názvu „minecraft SMP“ a jemně se pohupuje (skin erik3d je vestavěný jako výchozí) a když kdokoli stahuje nebo nahrává video, běží po liště načítání.
- **Offline režim:** SMP hráče, který není přihlášený, vidí všichni dál. Přehrát z něj jdou videa, která má hráč uložená u sebe (💾 uloženo u tebe), nebo která má uložená někdo, kdo je online. Ve sloupci je vidět „offline · X z Y jde přehrát“ a v SMP je filtr „Jen co jde přehrát“.
- **Každé SMP je jedna karta** na hlavní stránce. Kliknutím na obrázek nebo „Otevřít“ se SMP otevře na celou stránku. Pod kartami jsou Naposledy přidaná videa ze všech SMP a Hráči.

## Jak to funguje

- Ve složce hráče vznikne `videos/` (jeho nahraná videa), `cache/` (přehraná videa od ostatních) a `onion-smp.json` (záloha katalogu).
- Katalog (sekce, seznam videí, hráči) má každý u sebe a při spojení se synchronizuje.
- Každý hráč má vlastní digitální klíč. Své SMP, jeho sekce a videa může měnit jen jeho majitel a ostatní počítače podvržené změny zahodí.
- Kód admina odemyká klíč skupiny, který potvrzuje, kdo je admin a smí mít vlastní SMP.
- Video jde přehrát, když je online jeho autor nebo někdo, kdo už ho má uložené.
- Výběr složky umí Chrome, Edge a Opera. Ve Firefoxu a Safari se videa ukládají do prohlížeče.
- K navázání spojení se používá bezplatný server PeerJS Cloud. Videa přes něj nejdou.

## Aktualizace na novou verzi

Na GitHubu v repozitáři: Add file → Upload files → přetáhnout nový `index.html` → Commit changes. Za 1–2 minuty všichni obnoví stránku (Ctrl+Shift+R).
