# projekt_zmwd

Projekt analizy danych geograficznych porównujący ceny Big Maca i ataki rekinów na mapie świata. Projekt łączy dane ekonomiczne, bezpieczeństwa i informacje geograficzne, aby odkryć ciekawe korelacje i wzorce na poziomie kraju.

## Struktura projektu

```
projekt_zmwd/
├── README.md                           # Dokumentacja projektu
├── data/                              # Dane źródłowe
│   ├── big-mac-full-index.csv         # Indeks cen Big Maca na świecie
│   ├── Shark attacks and fatalities - Global Shark Attack File (GSAF) (2018).csv
│   │                                   # Dane o atakach rekinów
│   └── world_countries/               # Dane geograficzne (Shapefiles)
│       ├── World_Countries__Generalized_.shp
│       ├── World_Countries__Generalized_.dbf
│       ├── World_Countries__Generalized_.shx
│       └── World_Countries__Generalized_.prj
├── notebooks/                          # Analiza Jupyter Notebook
│   ├── big_macs.ipynb                 # Analiza cen Big Maca
│   └── shark_attacks.ipynb            # Analiza ataków rekinów
└── maps/                              # Mapy wygenerowane z analiz
    ├── big_mac_dollar_price_per_100k_km2.png
    ├── big_mac_dollar_price_per_border_1000_km.png
    ├── big_mac_dollar_price_per_name_len.png
    ├── shark_attacks_per_100k_km2.png
    ├── shark_attacks_per_border_1000_km.png
    └── shark_attacks_per_name_len.png
```

## Opis notatników

### big_macs.ipynb
Analiza cen Big Maca na całym świecie z wizualizacją geograficzną. Notebook:
- Wczytuje dane Big Maca z roku 2025
- Dopasowuje nazwy krajów z różnych źródeł danych
- Łączy dane ekonomiczne z warstwą geograficzną (Shapefile)
- Tworzy mapy choropleth pokazujące:
  - Ceny Big Maca względem powierzchni kraju (na 100k km²)
  - Ceny Big Maca względem długości granic (na 1000 km granic)
  - Korelację cen Big Maca z długością nazwy kraju

**Zależności:** pandas, geopandas, numpy, matplotlib

### shark_attacks.ipynb
Analiza globalnych ataków rekinów z wizualizacją geograficzną. Notebook:
- Wczytuje dane z Global Shark Attack File (GSAF) z 2018 roku
- Grupuje ataki rekinów według krajów
- Mapuje nazwy krajów do standardowych nazw geograficznych
- Integruje dane z warstwą geograficzną
- Tworzy mapy choropleth pokazujące:
  - Liczbę ataków rekinów na 100k km² powierzchni
  - Ataki rekinów względem długości linii brzegowej (na 1000 km granic)
  - Potencjalną korelację z długością nazwy kraju

**Zależności:** pandas, geopandas, numpy, matplotlib, requests

## Dane źródłowe

### big-mac-full-index.csv
Indeks cen Big Maca na całym świecie - dane ekonomiczne porównujące ceny hamburgerów w McDonaldzie w różnych krajach. Zawiera:
- Nazwy krajów
- Daty pomiaru
- Ceny w dolarach

### Shark attacks and fatalities - Global Shark Attack File (GSAF) (2018).csv
Zbiór danych o atakach rekinów z bazy Global Shark Attack File. Zawiera:
- Liczba ataków rekinów po krajach
- Inne informacje związane z bezpieczeństwem morskim

### capital-city-population.csv
Dane dotyczące populacji stolic krajów na świecie

### world_countries/ (Shapefile)
Dane geograficzne w formacie Shapefile zawierające:
- Granice krajów
- Nazwy krajów w standardowej formie
- Geometrię poligonów dla celów wizualizacji kartograficznej

## Wymagania

Do uruchomienia notatników niezbędne jest zainstalowanie potrzebnych pakietów - plik `requirements.txt`

## Użycie

1. Zainstaluj zależności: `pip install -r requirements.txt`
2. Otwórz Jupyter Notebook: `jupyter notebook`
3. Otwórz i uruchom notatniki w `notebooks/`:
   - `big_macs.ipynb` - dla analizy cen Big Maca
   - `shark_attacks.ipynb` - dla analizy ataków rekinów

## Wygenerowane mapy

Projekt generuje 6 map w formacie PNG w katalogu `maps/`:

| Plik | Opis |
|------|------|
| `big_mac_dollar_price_per_100k_km2.png` | Cena Big Maca znormalizowana do powierzchni kraju |
| `big_mac_dollar_price_per_border_1000_km.png` | Cena Big Maca względem długości granic |
| `big_mac_dollar_price_per_name_len.png` | Korelacja ceny Big Maca z długością nazwy kraju |
| `shark_attacks_per_100k_km2.png` | Liczba ataków rekinów na 100k km² |
| `shark_attacks_per_border_1000_km.png` | Ataki rekinów względem długości brzegu |
| `shark_attacks_per_name_len.png` | Potencjalna korelacja ataków rekinów z długością nazwy kraju |

## Główne funkcjonalności

- ✅ Wczytywanie i czyszczenie danych z wielu źródeł
- ✅ Mapowanie nazw krajów między różnymi bazami danych
- ✅ Integracja danych tabelarycznych z danymi geograficznymi
- ✅ Tworzenie map choropleth w Pythonie
- ✅ Normalizacja danych do cech geograficznych (powierzchnia, długość granic)
- ✅ Wizualizacja korelacji między danymi ekonomiczno-bezpieczeństwa a cechami geograficznymi

## Autor

Projekt zmwd - Analiza danych geograficznych

## Data ostatniej aktualizacji

14 stycznia 2026