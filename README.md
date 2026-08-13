# TP-Link GPON System Documentation

Kompletní¹¹ dokumentace k systému TP-Link GPON (Gigabit-capable Passive Optical Network).

## 📦 Obsah repozitá¹¹e

### Firmware

- **firmware/XX230v/** - Firmware pro model XX230v
  - `XX230v_v1_0.16.0_3.0.0_release-250423.zip` - Firmware verze 0.16.0 / 3.0.0 (release z 23.4.2025)

### Dokumentace

- `release notes.txt` - Pozn11mky k vyd11n11
- `LICENSE` - Licence

---

## 🌐 Co je GPON?

**GPON** (Gigabit-capable Passive Optical Network) je standard pro optické¹¹ s11t11 vyvinut11 pod ITU-T G.984.x, který umo17enuje p11enos dat vysokou rychlost11:

- **Downstream (stahov11n11):** a17 2,488 Gbps
- **Upstream (odes11l11n11):** a17 1,244 Gbps
- **Dosah:** a17 20 km na jednom vl11kn11
- **Rozd11lovac11 pom11r:** a17 1:128 (a17 2048 ONT na jedno OLT)

### Architektura GPON

1. **OLT (Optical Line Terminal)** - Za11í¹¹en11 u poskytovatele (ISP), nap11. TP-Link P1200-08, DS-P7001-16
2. **ODN (Optical Distribution Network)** - Pasivn11 optická¹¹ s11t11 s rozbo11ova11i
3. **ONT/ONU (Optical Network Terminal/Unit)** - Koncové¹¹ za11í¹¹en11 u zákazníka, nap11. TP-Link XX230v, TX-VG1530

---

## 📡 TP-Link GPON Produkty

### ONT/ONU Termin11ly

| Model | Typ | Porty | Wi-Fi | Voice | Pozn11mky |
|-------|-----|-------|-------|-------|----------|
| **XX230v** | GPON ONT | 1×¹ GE | Ne | Ne | Základní¹¹ GPON termin11l |
| **XX-530V** | XPON ONT | 1×¹ GE, 1×¹ FE | Dual-band (2.4G + 5G) | 1×¹ FXS | Podpora EPON/GPON auto-adaptive |
| **XZ000-G6v** | XPON ONT | 1×¹ GE | Ne | 1×¹ FXS | VoIP podpora, gigabitové¹¹ rychlosti |
| **TX-VG1530** | GPON Router | 4×¹ GE | Ano | Ano | Komplexní¹¹ router s Wi-Fi |
| **TL-GP112** | GPON Terminal | 4×¹ GE | Ne | Ano | Podpora POTS, USB 2.0 |

### SFP Moduly

| Model | Typ | Dosah | Vlnová¹¹ délka | Konektor |
|-------|-----|-------|----------------|----------|
| **XM60A** | GPON ONU SFP | 20 km | Tx: 1310 nm, Rx: 1490 nm | SC/APC |

**XM60A Specifikace:**
- Standard: G.984.x (1/2/3/4/5) a G.988
- Rychlost: 1,244 Gbps upstream / 2,488 Gbps downstream
- Dosah: a17 20 km (9/125 μm SMF)
- T11í¹¹d11: Class C+
- Citlivost p11í¹¹ijma11e: -28 dBm
- P11etí¹¹en11: -8 dBm
- Nap11á¹¹et11: 3.3 V (≤ ±5%)
- Hot-swap: Ano
- Diagnostika: DDM (Digital Diagnostics Monitoring) - nap11á¹¹et11, teplota, výkon
- Provozní¹¹ teplota: 0 °C a17 70 °C

### OLT Za11í¹¹en11

| Model | Porty | Podpora ONT | Uplink | Management |
|-------|-------|-------------|--------|------------|
| **P1200-08** | 8×¹ GPON | 1024 ONT | 8×¹ GE RJ45, 8×¹ GE SFP, 2×¹ 10G SFP+ | CLI, EMS (SNMP), Console |
| **DS-P7001-16** | 16×¹ GPON | 2048 ONT | 10G SFP+ | SNMP, Console |

---

## ⚙️ Konfigurace ONT/ONU

### P11í¹¹ipojen11 k za11í¹¹en11

1. P11ipojte po11í¹¹ta11 k GPON termin11lu p11es Ethernet kabel
2. Nastavte IP adresu po11í¹¹ta11e na `192.168.1.x` (x = 2-253)
3. Otev11ete webov11 prohlí¹¹í¹¹e11 a zadejte `http://192.168.1.1` (nebo `http://tplinkmodem.net`)
4. P11ihlaste se (defaultn11 `admin`/`admin` nebo heslo z manu11lu)

### Registrace u ISP (PON Certification)

Pro registraci GPON termin11lu u poskytovatele internetu je t11eba zad11t:

- **GPON Password** - Autentifika11n11 heslo od ISP (obvykle 10-20 znaků, hex nebo ASCII)
- **GPON SN (Serial Number)** - S11riové¹¹ 11s11lo za11í¹¹en11 od ISP (obvykle 12-24 znaků)

**Postup:**
1. P11ihlaste se do webového rozhran11
2. P11ejd11te na **Network Setting > PON Certification**
3. Zadejte **GPON Password** a/nebo **GPON SN** poskytnuté¹¹ ISP
4. Ulo17ete a po11kejte na registraci (LED PON by m11la sví¹¹tit zelen11)

### Podporované¹¹ standardy

- **ITU-T G.984.1/2/3/4** - GPON standardy
- **G.987.3** - 10G-PON protokol
- **G.988** - OMCI (ONT Management Control Interface)
- **AES-128** - Šifrov11n11 dat
- **FEC (Forward Error Correction)** - RS(255,239), bidirekcion11ln11
- **DBA (Dynamic Bandwidth Allocation)** - 5 typů, SBA + DBA
- **PLOAM** - Physical Layer OAM funkce
- **T-CONT/GEMPORT** - 32 T-CONT, 256 GEMPORT

---

## 🔧 Aktualizace Firmware

### Online aktualizace

1. P11ihlaste se do webového rozhran11
2. P11ejd11te na **Advanced > System Tools > Firmware Upgrade**
3. Klikn11te na **Check for Upgrades**
4. Pokud je dostupn11 nov11 verze, klikn11te na **Upgrade**

### Manu11ln11 aktualizace

1. St11hn11te firmware z tohoto repozit1111e nebo z [tp-link.com](https://www.tp-link.com/cz/support/download/)
2. P11ihlaste se do webového rozhran11
3. P11ejd11te na **Advanced > System Tools > Firmware Upgrade**
4. V sekci **Local Upgrade** klikn11te na **Browse** a vyberte soubor s firmware
5. Klikn11te na **Upgrade** a po11kejte na restart (3-5 minut)

⚠️ **Důle17it11 upozorn11n11:**
- B11hem aktualizace nevypí¹¹í¹¹nejte za11í¹¹en11
- P11ed aktualizac11 z11lohujte konfiguraci
- Ujist11te se, 17e firmware odpoví¹¹d11 hardwarové¹¹ verzi za11í¹¹en11
- Pou17í¹¹vejte pouze ofici11ln11 firmware od TP-Link

---

## 📊 Technické¹¹ specifikace GPON

### Fyzická¹¹ vrstva

| Parametr | Hodnota |
|----------|---------|
| Downlink rychlost | 2,488 Gbps |
| Uplink rychlost | 1,244 Gbps |
| Vlnová¹¹ délka (Tx) | 1310 nm |
| Vlnová¹¹ délka (Rx) | 1490 nm |
| Typ vl11kna | 9/125 μm SMF (Single-Mode Fiber) |
| Konektor | SC/APC |
| Maxim11ln11 dosah | 20 km |
| Rozd11lovac11 pom11r | 1:128 (a17 1:2048 u OLT) |

### Bezpe11nost

- **AES-128** - Šifrov11n11 upstream i downstream dat
- **Serial Number Authentication** - Autentifikace podle SN
- **Password Authentication** - Autentifikace heslem
- **OMCI Management** - Bezpe11n11 spr11va ONT

### QoS (Quality of Service)

- **802.1p** - 4 prioritn11 fronty
- **SP/WRR scheduling** - Strict Priority / Weighted Round Robin
- **Traffic shaping** - Podpora pro voice, video, data

### VLAN

- **4K VLAN entries**
- **Port-based VLAN**
- **802.1Q VLAN**
- **QinQ VLAN**
- **Port VLAN translation**

---

## 🔍 Diagnostika a monitoring

### LED indik11tory

| LED | Stav | Význam |
|-----|------|--------|
| **Power** | Zelen11 | Za11í¹¹en11 je zapnuté¹¹ |
| **PON** | Zelen11 | Úsp11šná¹¹ registrace k OLT |
| **PON** | 10erven11/blikaj11c11 | Chyba p11ipojen11 / registrace |
| **LOS** | Zelen11/10erven11 | Loss of Signal - 1711dn11 optická¹¹ s11gn11l |
| **LAN** | Zelen11/blikaj11c11 | Aktivn11 p11ipojen11, p11enos dat |
| **WLAN** | Zelen11 | Wi-Fi je aktivn11 |

### DDM (Digital Diagnostics Monitoring)

SFP moduly XM60A podporují¹¹ monitoring:
- Nap11á¹¹ec11 nap11á¹¹en11
- Teplota
- Vysí¹¹lac11 výkon (Tx power)
- P11í¹¹í¹¹í¹¹mac11 výkon (Rx power)
- Bias current

---

## 🔗 Odkazy

- [TP-Link Download Center](https://www.tp-link.com/cz/support/download/)
- [TP-Link GPON User Guide](https://www.tp-link.com/us/document/111835/)
- [TP-Link Service Provider - GPON](https://service-provider.tp-link.com/gpon/)
- [XM60A Datasheet](https://static.tp-link.com/upload/product-overview/2024/202403/20240314/XM60A%20Datasheet.pdf)

---

## 📄 Licence

Tento repozit1111 je licencov11n pod licencí¹¹ uvedenou v souboru LICENSE.

---

*Posledn11 aktualizace: Srpen 2026*
