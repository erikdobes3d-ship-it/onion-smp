# onion SMP

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
- **Každé SMP je jeden sloupec** na hlavní stránce. Sloupce se posouvají do strany a kliknutím na „Otevřít“ se SMP otevře na celou stránku.

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
