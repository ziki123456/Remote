# Arduino IDE code
Prepnuti chytre domacnosti lze prepnout na strance "remote.tode.cz", na strance to lze prepnout bez jakehokoliv pripjeni instalace nebo cehokoliv staci stabilni pripojeni arduina k wifi.

## Postup zapojení zařízení

## Napájení
- Síťové napětí **230 V AC** připojte přes **jistič** a **přepěťovou ochranu**.
- Výstup z jističe zapojte na vstup **impulsního relé** (Eaton Z-S230/S).

## Ovládání relé
- Výstupní kontakty impulsního relé připojte na **zásuvku nebo spotřebič** (např. žárovku).
- Cívku impulsního relé spínejte buď:
  - klasickým **vypínačem**, nebo
  - pomocí **relé modulu** ovládaného z NodeMCU.

## ESP8266 (NodeMCU)
Připojte podle následujícího schématu:
- `D1 (GPIO5)` → ovládání relé 1 (např. žárovka)
- `D2 (GPIO4)` → volitelně druhé relé
- **Napájení**: 5V z USB nebo adaptéru

## Relé modul
- Signální vodiče z ESP připojte přes **dupont kabely** na vstupy `IN1`, `IN2`...
- `GND` a `VCC` relé modulu propojte s `GND` a `5V` na NodeMCU.

## Wi-Fi připojení
- NodeMCU se automaticky připojí k Wi-Fi podle údajů nastavených ve firmwaru.

## Server a skripty
- Na webový server (např. **XAMPP** nebo hosting s PHP a MySQL) nahrajte připravené **PHP skripty**.
- V databázi vytvořte potřebné tabulky dle přiloženého SQL souboru.
- Zařízení každé **3 sekundy** komunikuje se serverem, zpracovává příkazy a aktualizuje jejich stav.
