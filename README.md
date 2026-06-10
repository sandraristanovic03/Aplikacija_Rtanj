# 🌲 Aplikacija za Monitoring Šuma Rtanja

**Detekcija promena stanja šumskih ekosistema pomoću Sentinel-2 i Dynamic World podataka**

---

## 📱 Pristupi Aplikaciji

### 🔴 **MAIN APPLICATION (Google Earth Engine)**

**👉 [Otvori GEE Aplikaciju Ovde](https://ee-sandraristanovic03.projects.earthengine.app/view/aplikacija-promena-stanja-uma-rtanj)** 👈

Ovo je glavna interaktivna aplikacija za analizu šuma Rtanja.

---

## 📖 Opis Projekta

Aplikacija za monitoring šumskih ekosistema na planini Rtanj koristi:
- **Sentinel-2** satelitske snimke (multispektralne podatke)
- **Dynamic World** algoritam (klasifikacija land cover-a)
- **Spektralne indekse** za procenu zdravstvenog stanja vegetacije

### 🎯 Glavne Mogućnosti

✅ **Analiza Vegetacije** - Praćenje zdravstvenog stanja biljnog pokrivača
✅ **Detekcija Promena** - Identifikacija šumskih gubitaka i prirana
✅ **Fenološka Klasifikacija** - Razlikovanje listopadnih i četinarskih šuma
✅ **Istorijski Trendovi** - Praćenje promena od 2016-2024
✅ **Zonalna Statistika** - Proračuni površina u hektarima (ha)

---

## 📊 Korišćeni Spektralni Indeksi

### 1. **NDVI** (Normalized Difference Vegetation Index)
- **Značaj**: Meri zdravstveno stanje vegetacije
- **Formula**: `(NIR - RED) / (NIR + RED)`
- **Raspon**: -1 do +1 (veće = zdravija vegetacija)
- **Primena**: Osnovna procena vitalnosti biljnog pokrivača

### 2. **NBR** (Normalized Burn Ratio)
- **Značaj**: Detektuje degradaciju i poremećaje šumskog tkiva
- **Formula**: `(NIR - SWIR) / (NIR + SWIR)`
- **Raspon**: -1 do +1
- **Primena**: Detekcija požara, bolesti, insektnih napadaja

### 3. **SAVI** (Soil-Adjusted Vegetation Index)
- **Značaj**: Korigovani indeks koji smanjuje uticaj tla
- **Formula**: `((NIR - RED) / (NIR + RED + L)) * (1 + L)` gde je L=0.5
- **Primena**: Areas sa malom vegetacijom gde je tlo dominantno

### 4. **LAI** (Leaf Area Index)
- **Značaj**: Meri gustinu lisne površine/krošnje
- **Formula**: `LAI = EVI * 3.618 - 0.118`
- **Raspon**: 0-7 (viši indeks = gušća krošnja)
- **Primena**: Procena biomase i produktivnosti šume

---

## 🗺️ Šumska Klasifikacija

Aplikacija automatski klasifikuje šume u dve vrste:

### 🍂 **Listopadne Šume**
- Izgube listove u zimskom periodu
- NDVI < 0.35 u zimskom periodu (decembar-februar)
- Karakteristične za oblasti sa umirenim klimama

### 🌲 **Četinarske Šume**
- Zadržavaju iglice i zelenilu tokom godine
- NDVI ≥ 0.35 u zimskom periodu
- Sposobne da fotosinteziraju tokom zime

---

## 📈 Analiza Promena (2016-2024)

Aplikacija generiše tri tipa mapa:

1. **Diferencijalna Mapa** 🔴🟢
   - Pokazuje pad ili rast indeksa
   - Crveno = Pad vrednosti (degradacija)
   - Zeleno = Rast vrednosti (oporavak/prirast)

2. **Mapa Gubitka Šume** ❌
   - Područja gde je šuma nestala
   - Ili je zadržala samo malu količinu vegetacije

3. **Mapa Prirasta Šume** ✅
   - Područja gde je nova šuma porasla
   - Uglavnom areal koji je prethodno bio bez šume

---

## 🔧 Tehnička Implementacija

### Korišćene Tehnologije
- **Google Earth Engine** - Cloud-based geospatial processing
- **Sentinel-2 Level 2A** - ESA satelitski snimci sa atmosferskom korekcijom
- **Dynamic World** - Google-in AI model za klasifikaciju land cover-a
- **JavaScript** (Google Earth Engine API)

### Oblačna Maska
- Automatski filtrirane slike sa više od 70% oblačnog pokrivača
- Dodatna filtering na 50% za kompozite
- Bitwise masking QA60 slojeva

### Vremenska Rezolucija
- Analiza po godinama
- Fleksibilna izbor sezone (mesec početka i kraja)
- Srednja vrednost (medijana) za kompozite

---

## 💡 Kako Koristiti Aplikaciju

### Korak 1: Otvaranje Aplikacije
👉 [Klikni Ovde](https://ee-sandraristanovic03.projects.earthengine.app/view/aplikacija-promena-stanja-uma-rtanj)

### Korak 2: Postavljanje Parametara
1. **Izbor vremenskog perioda**: Početna i krajnja godina (2016-2024)
2. **Izbor sezone**: Meseci analiza (npr. jun-septembar za leto)
3. **Izbor indeksa**: NDVI, NBR, SAVI ili LAI

### Korak 3: Pokretanje Analize
- Kliknite na **⚡ POKRENI PROSTORNU ANALIZU**
- Čekajte da se izračunaju rezultati (~20-60 sekundi)

### Korak 4: Analiza Rezultata
- **Mapa**: Dinamički prikaz sa legendom
- **Statistika**: Površine u hektarima
- **Grafikon**: Trend vrednosti indeksa kroz godine

---

## 📊 Primer Izveštaja

```
📊 IZVEŠTAJ O PROMENAMA ZA RTANJ
--------------------------------------------------
• Analizirani period: 2016 — 2024
• Korišćeni indikator: NDVI

• Ukupna šuma 2016: 5,234.50 ha
  └🍂 Listopadne: 3,100.25 ha
  └🌲 Četinarske: 2,134.25 ha

• Ukupna šuma 2024: 5,187.30 ha
  └🍂 Listopadne: 3,080.10 ha
  └🌲 Četinarske: 2,107.20 ha

❌ Ukupan gubitak šuma: 47.20 ha
✅ Ukupan prirast šuma: 12.50 ha
--------------------------------------------------
📈 NETO PROMENA: -34.70 ha
```

---

## 🌍 Podatkovni Sources

| Izvor | Rezolucija | Dostupnost | Opis |
|-------|-----------|-----------|-------|
| **Sentinel-2** | 10m | 2015-Sadašnjost | Multispektralni snimci (11 kanala) |
| **Dynamic World** | 10m | 2015-Sadašnjost | AI-bazirana klasifikacija (9 klasa) |
| **AOI (Granica Rtanja)** | Vektorski | Prilagođeno | GEE Asset - Administrativne granice |

---

## ⚠️ Ograničenja i Napomene

- **Oblačnost**: Analiza se može pogoršati tijekom vlažnih perioda (puno oblaka)
- **Rezolucija**: 10m piksela može propustiti male šumske promene
- **Atmosferska Korekcija**: Korišćeni su Level 2A podaci (već korigovani)
- **Dynamic World Mode**: Fiksiran na klasu "Trees" (klasa 1) - bez fleksibilnog praga
- **Fenologija**: Klasifikacija listopadne vs četinarske zavisi od zimske NDVI vrednosti

---

## 📚 Dostupna Dokumentacija

- 📖 **[UPUTSTVO.md](./UPUTSTVO.md)** - Detaljno uputstvo za korišćenje aplikacije
- 📊 **[INDEKSI.md](./INDEKSI.md)** - Objašnjenje svih spektralnih indeksa i njihove primene

---

## 📝 Autori i Licenca

**Kreatorno**: Sandra Ristanović
**Institucija**: Earth Observation (GIS & Remote Sensing)
**Datum**: 2026
**Licenca**: CC0 (Javna domena) / Open Source

---

## 🔗 Dodatni Resursi

- [Google Earth Engine Documentation](https://developers.google.com/earth-engine)
- [Sentinel-2 Documentation](https://sentinel.esa.int/web/sentinel/user-guides/sentinel-2-msi)
- [Dynamic World Dataset](https://www.dynamicworld.app/)
- [Remote Sensing Indices](https://www.indexdatabase.de/)

---

## 📧 Kontakt i Podrška

👤 **GitHub**: [@sandraristanovic03](https://github.com/sandraristanovic03)

---

**Napomena**: Ova aplikacija je rezultat istraživanja monitoring šuma Rtanja pomoću satelitskih podataka. Svi rezultati su za naučne i edukativne svrhe.
