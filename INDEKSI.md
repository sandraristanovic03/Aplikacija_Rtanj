# 📊 Spektralni Indeksi - Detaljno Objašnjenje

## Uvod

Spektralni indeksi su matematičke kombinacije vrednosti iz različitih kanala (talasnih dužina) satelitskog snimanja. Oni se koriste za ekstrakciju biofizičkih informacija.

---

## 1. NDVI (Normalized Difference Vegetation Index)

### Formula
```
NDVI = (NIR - RED) / (NIR + RED)
```

### Kanali
- **NIR** (Blizu-infracrvenо): Sentinel-2 Band 8 (842 nm)
- **RED** (Crveno): Sentinel-2 Band 4 (665 nm)

### Vrednost i Interpretacija

| NDVI Vrednost | Interpretacija | Pokrivač |
|---|---|---|
| < 0.2 | Gola tla, voda | Bez vegetacije |
| 0.2 - 0.4 | Retka vegetacija | Mahovine, trave |
| 0.4 - 0.6 | Umirena vegetacija | Voće stabla, šiblje |
| 0.6 - 0.8 | Gusta vegetacija | Šume, žitarica |
| > 0.8 | Veoma gusta vegetacija | Idealne šume |

### Prednosti
✅ Jednostavna formula
✅ Mala osetljivost na atmosferu
✅ Standardni indeks u remote sensingу

### Limitacije
❌ Zasicen u gustim šumama
❌ Osetljiv na atmosferske uslove
❌ Ne razlikuje vrste vegetacije

---

## 2. NBR (Normalized Burn Ratio)

### Formula
```
NBR = (NIR - SWIR) / (NIR + SWIR)
```

### Kanali
- **NIR** (Blizu-infracrvenо): Sentinel-2 Band 8 (842 nm)
- **SWIR** (Kratko talasno infracrveno): Sentinel-2 Band 12 (2202 nm)

### Vrednost i Interpretacija

| NBR Vrednost | Interpretacija |
|---|---|
| > 0.5 | Zdravo, nevođeno drveće |
| 0.2 - 0.5 | Umireno oštećenje |
| 0 - 0.2 | Značajno oštećenje |
| < 0 | Golo tlo ili voda |

### Primena
🔥 **Detekcija požara**
🦗 **Detektovanje insektnih napadaja**
🌳 **Detektovanje bolesti drveća**
💧 **Stres od suše**

---

## 3. SAVI (Soil-Adjusted Vegetation Index)

### Formula
```
SAVI = ((NIR - RED) / (NIR + RED + L)) * (1 + L)
gde je L = 0.5
```

### Kanali
- **NIR** (Blizu-infracrvenо): Sentinel-2 Band 8 (842 nm)
- **RED** (Crveno): Sentinel-2 Band 4 (665 nm)

### Vrednost i Interpretacija

| SAVI Vrednost | Interpretacija |
|---|---|
| < 0.1 | Retka ili nema vegetacije |
| 0.1 - 0.2 | Mala pokrivnost |
| 0.2 - 0.4 | Umirena pokrivnost |
| > 0.4 | Gusta vegetacija |

### Primena
🏜️ **Suva i semi-aridna područja**
🌾 **Kulturenosničke poljoprivrede**
🌲 **Mlade šume sa vidljivim tlom**

---

## 4. LAI (Leaf Area Index)

### Formula
```
LAI = EVI * 3.618 - 0.118
```

### Vrednost i Interpretacija

| LAI Vrednost | Krošnjenje |
|---|---|
| 0 - 1 | Vrlo retka krošnja |
| 1 - 2 | Retka krošnja |
| 2 - 3 | Umirena krošnja |
| 3 - 5 | Gusta krošnja |
| > 5 | Maksimalno gusta krošnja |

### Primena
🍃 **Merenje biomase**
💧 **Evapotranspiracija**
🌳 **Produktivnost šume**
🔍 **Detaljna analiza gustine krošnje**

---

## Poređenje Indeksa

| Aspekt | NDVI | NBR | SAVI | LAI |
|---|---|---|---|---|
| **Primena** | Opšta vegetacija | Požari/Bolest | Suva tla | Biomasa |
| **Kompleksnost** | Jednostavna | Jednostavna | Srednja | Kompleksna |
| **Atmosfera** | Osetljivo | Veoma osetljivo | Osetljivo | Veoma osetljivo |

---

## Zaključak

Spektralni indeksi su moćan alat za remote sensing i monitoring prirode. Njihovo razumevanje je ključno za interpretaciju satelitskih snimanja.
