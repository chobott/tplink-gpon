# TP-Link GPON Repository

Tento repozitář obsahuje firmware a dokumentaci pro TP-Link GPON ONT/ONU zařízení.

## 📦 Obsah repozitáře

### Firmware

- **firmware/XX230v/** - Firmware pro model XX230v
  - `XX230v_v1_0.16.0_3.0.0_release-250423.zip` - Firmware verze 0.16.0 / 3.0.0 (release z 23.4.2025)

### Dokumentace

- `release notes.txt` - Poznāmky k vyd
- `LICENSE` - Licence

## 🌐 Co je GPON?

**GPON** (Gigabit-capable Passive Optical Network) je standard pro optické²² s ítě, který umožňuje přenos dat rychlostí²² až 2,5 Gbps downstream a 1,25 Gbps upstream.

## 📡 TP-Link GPON Zařízení

### Přehled

TP-Link vyrůbí²² řadu GPON ONT/ONU zařízen pro připojen k optické²² s ti ISP (Internet Service Provider).

### Typické²² modely

- **XX230v** - GPON ONT s 1 GE portem
- **TX-VG1530** - GPON router s Wi-Fi
- **TL-GP112** - GPON termin
- **XM60A** - GPON ONU SFP modul

## ⚙️ Konfigurace

### Připojen k zařízení

1. Připojte počítač k GPON terminu přes Ethernet kabel
2. Nastavte IP adresu počítače na `192.168.1.x` (x = 2-253)
3. Otevřete webov prohlí²²eč a zadejte `http://192.168.1.1`
4. Přihlaste se (defaultně `admin`/`admin`)

### Registrace u ISP

Pro registraci GPON terminu u poskytovatele je potřeba zadat:

- **GPON Password** - Heslo od ISP
- **GPON SN** (Serial Number) - S ériové²² č slo od ISP

Tyto údaje najdete v sekci **Network Setting > PON Certification**.

## 🔧 Aktualizace Firmware

### Online aktualizace

1. Přihlaste se do webového rozhraní²²
2. Přejděte na **Advanced > System Tools > Firmware Upgrade**
3. Klikněte na **Check for Upgrades**
4. Pokud je dostupn nov verze, klikněte na **Upgrade**

### Manu ln aktualizace

1. Stá²²hněte firmware z tohoto repozitáře nebo z tp-link.com
2. Přihlaste se do webového rozhraní²²
3. Přejděte na **Advanced > System Tools > Firmware Upgrade**
4. V sekci **Local Upgrade** klikněte na **Browse** a vyberte soubor s firmware
5. Klikněte na **Upgrade** a počkejte na restart

⚠️ **Důležité upozorněn:**
- Během aktualizace nevypí²²nejte zařízení
- Před aktualizací²² zálohujte konfiguraci
- Ujistěte se, že firmware odpoví²²d hardwarové²² verzi zařízen

## 📋 Technické²² specifikace

### XM60A GPON SFP Modul

- Standard: G.984.x (1/2/3/4/5) a G.988
- Rychlost: 1,244 Gbps upstream / 2,488 Gbps downstream
- Dosah: až 20 km (9/125μm SMF)
- Konektor: SC/APC
- Vlnov d tov d lka: 1310nm-TX / 1490nm-RX

## 🔗 Odkazy

- [TP-Link Download Center](https://www.tp-link.com/cz/support/download/)
- [TP-Link GPON User Guide](https://www.tp-link.com/us/document/111835/)

## 📄 Licence

Tento repozitář je licencov n pod licenc uvedenou v souboru LICENSE.

---

*Posledn aktualizace: Srpen 2026*
