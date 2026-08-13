# GPON technologie a TP‑Link GPON

Tento dokument shrnuje kompletní¹¹ informace o technologii GPON (Gigabit-capable Passive Optical Network) podle řady standardů ITU‑T G.984 a na závěr uv11d11 konkré¹¹tn11 parametry vybran11ch TP‑Link GPON zařízen11.

## Základní¹¹ charakteristika GPON

GPON je optická¹¹ přístupová¹¹ technologie typu PON (Passive Optical Network), při které jeden optick11 vl11knov11 kmen z centr11ln11 lokality (OLT) obsluhuje mnoho koncov11ch jednotek (ONT/ONU) přes pasivn11 optick11 splittery.
Standardy ITU‑T G.984 definují¹¹ architekturu, fyzickou vrstvu, přenosovou vrstvu i management (OMCI) pro gigabitové¹¹ pasivn11 optick11 s11tě.

Typické¹¹ parametry GPON dle G.984/G.984.2/G.984.3:

- Downstream: až 2.488 Gbit/s (často uv11děno jako 2.5 Gbit/s), sd11lené¹¹ mezi ONT.
- Upstream: až 1.244 Gbit/s (1.25 Gbit/s).
- Vlnové¹¹ délky: 1490 nm downstream, 1310 nm upstream (případně 1550 nm pro RF video).
- Sd11lec11 poměr (split ratio): typicky 1:64, volitelně až 1:128.
- Dosah: logicky cca 20 km, s vhodnou optikou až 28 dB optick11ho budgetu (Class B+).

## Architektura GPON

GPON s11ť se skl11d11 ze tří hlavn11ch prvků: OLT, ODN a ONT/ONU.

- **OLT (Optical Line Terminal)** – zařízen11 v centr11ln11 stanici/CO, které ukončuje kořenov11 konec ODN, implementuje GPON protokol, ř11d11 přenos downstream i upstream a spravuje ONT přes OMCI.
- **ODN (Optical Distribution Network)** – pasivn11 optická¹¹ distribuční¹¹ s11ť tvořená¹¹ vl11kny a optick11mi splittery; neobsahuje aktivn11 elektroniku.
- **ONT/ONU (Optical Network Terminal/Unit)** – koncová¹¹ jednotka u z11kazn11ka, která přev11d11 optick11 sign11l na ethernet, hlas (FXS), Wi‑Fi apod.; ONT je speci11ln11 případ ONU určen11 pro jednoho účastn11ka.

Downstream přenos (OLT → ONT) je broadcast – OLT vys11l11 r11mce všem ONT a každ11 ONT si vybere pouze r11mce určené¹¹ pro sebe.
Upstream přenos (ONT → OLT) je koordinov11n pomocí TDMA, kde OLT přiděluje časové¹¹ sloty jednotliv11m ONT tak, aby nedoch11zelo ke koliz11m.

## Standardy ITU‑T G.984

Řada G.984 je rozdělena do několika doporučení¹¹, která pokr11vaj11 jednotlivé¹¹ vrstvy systému GPON.

- **G.984.1** – Obecná¹¹ charakteristika GPON, topologie, definice OLT, ONT, ODN.
- **G.984.2** – Specifikace fyzické¹¹ vrstvy (Physical Media Dependent, optika, vlnové¹¹ délky, optick11 budget).
- **G.984.3** – Přenosov11 konvergenční¹¹ vrstva (Transmission Convergence), enkapsulace GEM r11mců, TDM/TDMA logika.
- **G.984.4** – OMCI (ONT Management and Control Interface), protokol pro řízen11 ONT z OLT (konfigurace UNI, spojen11, management).

GPON použív11 vlastní enkapsulaci GEM (GPON Encapsulation Method), která umo17ňuje přen11šet různé typy služeb včetně Ethernetu a TDM přes jednotn11 r11mcov11 form11t.
Standardy poč11taj11 s možností¹¹ dalš11 evoluce (XG‑PON, XGS‑PON, NG‑PON2), které mohou koexistovat na stejn11m vl11kně díky oddělen11m vlnov11m délk11m.

## Přenosové¹¹ parametry a QoS

Na fyzické¹¹ úrovni GPON využív11 NRZ modulaci s FEC (Forward Error Correction) typicky RS(255,239), což zvyšuje odolnost přenosu vůči chyb11m.
Pro řízen11 přenosu GPON zav11d11 koncept T‑CONT (Transmission Container) a GEM portů, které umo17ňují¹¹ pru17né¹¹ přidělov11ní¹¹ šířky p11sma a QoS pro jednotlivé¹¹ služby.

Typické¹¹ vlastnosti QoS a traffic managementu:

- Podpora priorit (např. 802.1p) a více front na port.
- Dynamické¹¹ přidělov11ní¹¹ p11sma (DBA – Dynamic Bandwidth Allocation).
- Oddělení¹¹ služeb (internet, IPTV, VoIP) na úrovni VLAN a GEM portů.

## GPON vs EPON (stručné¹¹ srovn11n11)

EPON (IEEE 802.3ah) je konkurenční¹¹ PON standard založen11 na nativn11m Ethernetu, zatímco GPON je definov11n ITU‑T s GEM enkapsulac11.
Ve FTTH nasazen11ch m11 GPON obvykle vyšš11 downstream kapacitu (2.488 Gbit/s sd11leně) a silnější QoS/OAM, zatímco EPON boduje v jednoduchosti a ceně někter11ch komponent.

| Parametr          | GPON (ITU‑T G.984)            | EPON (IEEE 802.3ah)          |
|-------------------|-------------------------------|------------------------------|
| Downstream        | 2.488 Gbit/s                  | 1.25 Gbit/s (1G EPON)        |
| Upstream          | 1.244 Gbit/s                  | 1.25 Gbit/s                  |
| Split ratio       | 1:64 typ., až 1:128           | 1:32 typ., až 1:64           |
| Encapsulace       | GEM, T‑CONT/GEM ports         | Nativn11 Ethernet, 8b/10b     |
| Organizace        | ITU‑T                         | IEEE                         |
| Evoluce           | XG‑PON, XGS‑PON, NG‑PON2      | 10G‑EPON, 25G‑EPON           |

## TP‑Link GPON zařízen11 – přehled

Na trhu GPON zařízen11 TP‑Link nab11z11 řadu koncov11ch jednotek (ONT/ONU), routerů a SFP modulů, které jsou kompatibilní¹¹ se standardy ITU‑T G.984 a typicky pracují¹¹ s tř11dou optiky B+.

### TX‑VG1530 – VoIP GPON router

TX‑VG1530 je N300 VoIP GPON router určen11 pro FTTH nasazen11, který splňuje standardy ITU‑T G.984.1/2/3/4 a použív11 optick11 modul Class B+.
Poskytuje downstream až 2.488 Gbit/s a upstream až 1.244 Gbit/s, rozhran11 zahrnují¹¹ 1 SC/APC GPON port, 4×¹ 10/100/1000 Mbps RJ45 LAN porty, 2×¹ RJ11 FXS porty pro hlas a 1×¹ USB 2.0 port.

### XX230v – GPON ONU/ONT

Model XX230v je GPON ONU/ONT, který je rovněž kompatibilní¹¹ s ITU‑T G.984 a podporuje maxim11ln11 rychlosti 2.488 Gbit/s downstream a 1.244 Gbit/s upstream.
Podle datasheetu m11 3×¹ 10/100/1000 Mbps LAN porty, 1×¹ USB 2.0 port, 1×¹ FXS port a 1×¹ SC/APC GPON port, pracuje na vlnov11ch délk11ch 1490 nm (downstream) a 1310 nm (upstream) a použív11 optickou třídu B+ s citlivostí¹¹ GPON přij11mače okolo −27 dBm.

### XM60A – GPON ONU SFP modul

XM60A je GPON ONU SFP modul navržen11 podle G.984 a kompatibilní¹¹ s SC/APC konektorem, určen11 pro integraci GPON ONT funkc11 přímo do zařízen11 se SFP slotem.
Poskytuje 1.244 Gbit/s upstream a 2.488 Gbit/s downstream, podporuje dosah až 20 km na 9/125 μm SMF, typicky pracuje v tř11dě B+ nebo C+ a využív11 vlnové¹¹ délky 1310 nm pro vys11l11n11 a 1490 nm pro příjem.
