# CMDB Column Rearrange – Automatyzacja przetwarzania danych

Skrypt Python automatyzujący przekształcanie pliku Excel eksportowanego z systemu CMDB (np. ServiceNow) do formatu wymaganego przez szablon raportowy.

## Problem

Miesięczny eksport danych z systemu CMDB dostarczał plik Excel z kolumnami w niestandardowej kolejności — niezgodnej z wymaganym formatem szablonu raportowego. Ręczne przestawianie kolumn zajmowało czas i było podatne na błędy.

## Rozwiązanie

Skrypt Jupyter Notebook który:
- wczytuje plik Excel z systemu CMDB
- przestawia kolumny w kolejności wymaganej przez szablon
- kopiuje kolumnę `Name` i automatycznie przycina wartości FQDN do hostnameu (segment przed pierwszą kropką)
- zapisuje gotowy plik przez przyjazne okno dialogowe GUI — dostępne dla użytkowników bez wiedzy programistycznej

## Demo

```
Wejście:  server01.domain.corp  →  Wyjście: server01
Wejście:  db-prod.internal.corp →  Wyjście: db-prod
```

## Wymagania

- Python 3.8+
- pandas
- openpyxl
- tkinter (wbudowany w standardową bibliotekę Python)

```bash
pip install pandas openpyxl
```

## Uruchomienie

1. Otwórz `cmdb_column_rearrange.ipynb` w Jupyter Notebook lub JupyterLab
2. Uruchom wszystkie komórki (`Run All`)
3. W oknie dialogowym wybierz plik źródłowy Excel (eksport CMDB)
4. Wskaż lokalizację zapisu pliku wynikowego
5. Gotowe — plik jest przekształcony i zapisany

## Struktura kolumn wyjściowych

| Pozycja | Kolumna |
|---------|---------|
| 1 | Resource Unit |
| 2 | Name |
| 3 | Company |
| 4 | Contract |
| 5 | Profitcenter |
| 6 | RU Variant |
| 7 | Name (hostname – przycięty) |
| 8–14 | Kolumny pomocnicze |
| 15 | Description |
| 16 | Status |
| 17 | Class |
| 18 | Assignment group |
| 19 | Created |
| 20 | Installed |
| 21 | CI Managed By |

## Tech Stack

`Python 3.10` · `pandas` · `openpyxl` · `tkinter` · `Jupyter Notebook`

## Autor

**Bartosz Wadowski** – Data Analyst  
[LinkedIn](https://www.linkedin.com/in/bartosz-wadowski/)
