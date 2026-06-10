# 📖 Uputstvo za Korišćenje Aplikacije

## 🚀 Početak

### Korak 1: Otvaranje Aplikacije

👉 **[KLIKNI OVDE DA OTVORIŠ APLIKACIJU](https://ee-sandraristanovic03.projects.earthengine.app/view/aplikacija-promena-stanja-uma-rtanj)**

Aplikacija će se otvoriti u novoj kartici preglednika. Čeka se učitavanje (1-3 sekunde).

---

## 🎮 Pregled Interfejsa

```
┌─────────────────────────────────────────────────────────┐
│                  APLIKACIJA RTANJ                       │
│          Monitoring šumskih ekosistema                  │
├─────────────────────────────────────────────────────────┤
│                                                         │
│  LEVA STRANA:              DESNA STRANA:               │
│  ┌─────────────────┐       ┌─────────────────┐        │
│  │  CONTROL PANEL  │       │   MAPA          │        │
│  │  - Godine       │       │   - Slojevi     │        │
│  │  - Meseci       │       │   - Legenda     │        │
│  │  - Indeksi      │       │   - Zoom/Pan    │        │
│  │  - [POKRENI]    │       │                 │        │
│  │  - Statistika   │       │                 │        │
│  │  - Grafikon     │       │                 │        │
│  └─────────────────┘       └─────────────────┘        │
│                                                         │
└─────────────────────────────────────────────────────────┘
```

---

## ⚙️ Korak-po-Korak Analiza

### Faza 1: Postavljanje Vremenskog Perioda

**📅 Početni vremenski presek** (gornji selektor)
- Kliknite na padajući meni
- Izaberite početnu godinu (2016-2024)
- Primer: "Godina 2016"

**📅 Krajnji vremenski presek** (donji selektor)
- Kliknite na padajući meni
- Izaberite krajnju godinu (mora biti veća od početne)
- Primer: "Godina 2024"

**⚠️ Validacija**: Krajnja godina MORA biti veća od početne!

---

### Faza 2: Izbor Fenološke Sezone

**🌱 Početak fenološke sezone**
- Kliknite na padajući meni
- Izaberite mesec početka (obično jun - 6)
- Ovo je mesec kada počinje vegetacijska sezona

**🌱 Kraj fenološke sezone**
- Kliknite na padajući meni
- Izaberite mesec kraja (obično septembar - 9)
- Ovo je mesec kada se sezona završava

**Primedbe**:
- Početak fenološke sezone mora biti pre kraja!
- Za leto: jun (6) → septembar (9)
- Za celogodišnu analizu: januar (1) → decembar (12)

---

### Faza 3: Izbor Spektralnog Indikatora

**📊 Izbor spektralnog indikatora** - Kliknite na meni

Dostupni indeksi:

1. **NDVI** (Normalized Difference Vegetation Index)
   - Najbolji za: Opštu procenu zdravlja vegetacije
   - Raspon: -1 do +1 (viši = zdravija)
   - Preporuka: Početna analiza

2. **NBR** (Normalized Burn Ratio)
   - Najbolji za: Detekciju požara, bolesti, insektnih napadaja
   - Raspon: -1 do +1
   - Preporuka: Kada vidite anomalije u NDVI-ju

3. **SAVI** (Soil-Adjusted Vegetation Index)
   - Najbolji za: Suva područja, retka vegetacija
   - Raspon: 0 do +1
   - Preporuka: Detaljnija analiza sa manje šuma

4. **LAI** (Leaf Area Index)
   - Najbolji za: Procena gustine krošnje
   - Raspon: 0 do +7 (m²/m²)
   - Preporuka: Detaljne analize biomase

---

### Faza 4: Pokretanje Analize

**⚡ Dugme POKRENI PROSTORNU ANALIZU**

1. Kliknite na zeleno dugme: **⚡ POKRENI PROSTORNU ANALIZU**
2. Čekajte poruku: **"⏳ Pokrenuta prostorna analiza..."**
3. Analiza traje: **20-60 sekundi** (zavisi od veličine AOI-a)
4. Kada je gotova: **"✅ Analiza uspešno izvršena!"**

---

## 📊 Čitanje Rezultata

### Mapa (Desna Strana)

Na mapi se prikazuju različiti slojevi:

#### 🟩 Diferencijalna Mapa (Uvek Vidljiva)
- **Zeleno**: Indeks se povećao (bolje zdravlje biljaka)
- **Crveno**: Indeks se smanjio (degradacija)
- **Belo/Sivo**: Bez značajne promene

#### 🟥 Gubitak Šume (Za Aktiviranje)
Kliknite na opis sloja da aktivirate:
- **Crvena boja**: Detektovane oblasti gde je šuma bila ali je sada nestala
- Područja sa padom indeksa

#### 🟣 Prirast Šume
- **Ljubičasta boja**: Nova šuma koja je porasla
- Areas gdje je šume nije bilo, ali je sada vidljiva

#### 🌳 Šumske Maske
- **Tamno zelena (četinari)**: Šume koje zadržavaju iglice
- **Svetlo zelena (listopadne)**: Šume koje gube listove zimi

---

### 📊 Statistički Panel

Nakon analize, prikazuje se detaljni izveštaj:

```
📊 IZVEŠTAJ O PROMENAMA ZA RTANJ
--------------------------------------------------
• Analizirani period: 2016 — 2024
• Korišćeni indikator: NDVI

• Ukupna šuma 2016: 5,234.50 ha          ← Početna površina
  └🍂 Listopadne: 3,100.25 ha
  └🌲 Četinarske: 2,134.25 ha

• Ukupna šuma 2024: 5,187.30 ha          ← Krajnja površina
  └🍂 Listopadne: 3,080.10 ha
  └🌲 Četinarske: 2,107.20 ha

❌ Ukupan gubitak šuma: 47.20 ha        ← Areas gde je šuma nestala
✅ Ukupan prirast šuma: 12.50 ha         ← Areas gde je nova šuma porasla
--------------------------------------------------
📈 NETO PROMENA: -34.70 ha               ← Finalna razlika
```

### 📈 Grafikon

Grafikon prikazuje **trend vrednosti indeksa kroz godine**:

```
  Srednja vrednost NDVI
  ↑
  0.7 │     ╱╲
      │    ╱  ╲
  0.6 │───╱────╲────────
      │  ╱      ╲
  0.5 │─╱────────╲──
      │╱          ╲
  0.4 └───────────────→ Godina
      2016  2018  2020  2022  2024
```

- **Nagore**: Indeks se poboljšava (zdraija vegetacija)
- **Nadole**: Indeks se pogoršava (degradacija)
- **Ravno**: Stabilna situacija

---

## 🗺️ Navigacija na Mapi

### Zoom
- **Približavanje**: Scroll miša gore
- **Udaljavanjе**: Scroll miša dole
- Ili: Dugmići **+/-** u gornjem levom uglu mape

### Pomeranje
- **Drag mišu** po mapi da se pomeriš
- Ili: Koristi strelice na tastaturi

### Aktiviranje/Deaktiviranje Slojeva
1. Pogledaj **"Slojevi"** dugme (gornji desni ugao)
2. Kliknite na checkboxes pored slojeva da ih uključiš/isključiš
3. Primena: Želiš li da vidiš samo gubitak? Uključi samo taj sloj.

---

## 💡 Praktični Primeri

### Primer 1: Monitorovanje Opšte Vegetacije

1. **Početna godina**: 2016
2. **Krajnja godina**: 2024
3. **Sezona**: Jun (6) → Septembar (9)
4. **Indeks**: NDVI
5. **Klikni**: ⚡ POKRENI

**Šta gledam**: Zelena područja = poboljšanje; crvena = degradacija

---

### Primer 2: Detekcija Požara i Bolesti

1. **Početna godina**: 2023
2. **Krajnja godina**: 2024
3. **Sezona**: Maj (5) → Oktobar (10)
4. **Indeks**: NBR (Normalized Burn Ratio)
5. **Klikni**: ⚡ POKRENI

**Šta gledam**: 
- Crvene oblasti pokazuju požare ili bolesti
- NBR je bolji od NDVI-ja za ove probleme

---

### Primer 3: Analiza Biomase

1. **Početna godina**: 2020
2. **Krajnja godina**: 2024
3. **Sezona**: Maj (5) → Septembar (9)
4. **Indeks**: LAI (Leaf Area Index)
5. **Klikni**: ⚡ POKRENI

**Šta gledam**:
- Tamne oblasti = gusta krošnja (> 5 LAI)
- Svetle oblasti = retka krošnja (< 2 LAI)
- Trend na grafikonu pokazuje promenu gustine

---

## ⚠️ Česta Pitanja

### P: Šta ako se analiza dugo čeka?
**O**: To je normalno - analiza obrađuje terabajtе podataka. Čekaj 1-2 minuta.

### P: Šta znači crvena boja na mapi?
**O**: Pad vrednosti indeksa - degradacija šume, bolest, ili požar.

### P: Šta znači zelena boja na mapi?
**O**: Rast vrednosti indeksa - zdravija vegetacija ili oporavak.

### P: Mogu li analizirati samo deo Rtanja?
**O**: Trenutno je analiza ograničena na celu AOI (granicu Rtanja).

### P: Koliko stara je mapa?
**O**: Najnoviji dostupni Sentinel-2 podaci (Latencija: ~2-3 dana)

### P: Zašto neka mesta nemaju boju?
**O**: Mogu biti:
- Direktno pod oblacima (filtrirani)
- Van šumskog pokrivača
- Bez dovoljno podataka

---

## 🔧 Tehničke Napomene

### Sistem Zahtevi
- **Preglednik**: Chrome, Firefox, Safari, Edge (novije verzije)
- **Internet**: Brza konekcija (3+ Mbps preporučeno)
- **Rezolucija**: 1024x768 ili viša
- **RAM**: 2GB+

### Kompatibilnost
- ✅ Desktop/Laptop
- ✅ Tablet (iPad, Android)
- ⚠️ Mobilni telefon (mogućno, ali ne preporučeno)

### Performanse
- Analiza: 20-60 sekundi
- Učitavanje: 1-3 sekunde
- Zoom/Pan: Instant

---

## 🆘 Rešavanje Problema

### Problem: Analiza se ne pokreće
**Rešenje**: 
1. Osvežite stranicu (F5 ili Ctrl+R)
2. Očistite "cache" (Ctrl+Shift+Del)
3. Pokušajte sa drugim preglednikom

### Problem: Mapa ne učitava se
**Rešenje**:
1. Čekaj 10 sekundi
2. Proveri internet konekciju
3. Otvori drugačiji preglednik

### Problem: Greške pri analizi
**Rešenje**:
1. Proveri da li je krajnja godina > početne godine
2. Proveri da li je krajnji mesec > početnog meseca
3. Pokušaj sa drugom kombinacijom parametara

---

## 📚 Dodatni Resursi

- 📖 [README - Detaljno Objašnjenje Aplikacije](./README.md)
- 📊 [INDEKSI - Sve O Spektralnim Indeksima](./INDEKSI.md)
- 🌐 [Google Earth Engine Docs](https://developers.google.com/earth-engine)
- 📡 [Sentinel-2 Dokumentacija](https://sentinel.esa.int/)

---

## 📞 Kontakt

Za pitanja ili probleme:
👤 **GitHub**: [@sandraristanovic03](https://github.com/sandraristanovic03)

---

**Sretno sa analizom! 🌲🗺️**
