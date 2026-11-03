# NDC & Distribution Channels Analytics Dashboard

Kompleksowy model analityczny w programie Excel zaprojektowany pod kątem monitorowania, optymalizacji i wsparcia sprzedaży w kanałach dystrybucji (ze szczególnym uwzględnieniem technologii NDC oraz tradycyjnych GDS).

---

## Architektura Projektu

1. **Surowe Dane Źródłowe (`synthetic_flight_passenger_data`)**
2. **Warstwa Konfiguracyjna (arkusz `custom`)**:
   * **Parametryzacja biznesowa:** Dedykowana, odizolowana komórka konfiguracyjna przechowująca ruchomy próg operacyjny (limit błędów API, np. `110`).
   * **Tabely pomocnicze pod wizualizacje:** Stworzenie dedykowanych, odseparowanych tabel agregujących dane w tle wyłącznie pod kątem wykresów na głównym dashboardzie. Dzięki temu główna tabela analityczna pozostaje czysta i wolna od sztywnych zależności graficznych.
3. **Główny Dashboard Menedżerski (arkusz `Analiza_Dystrybucji`)**:
   * **Karty KPI (Wskaźniki Kluczowe):** Dynamiczne, autorskie karty sumujące na dole arkusza:
     * Całkowita Liczba Zapytań
     * Całkowita Liczba Rezerwacji
     * Globalny Wskaźnik Konwersji (L2B)
   * **Wizualizacje Analityczne:**
     * **Wykres 1 (Biznesowy):** Kolumnowy wykres porównujący wolumen zapytań i rezerwacji dla głównych kanałów dystrybucji (`Direct`, `GDS`, `NDC`).
     * **Wykres 2 (Techniczny / Operacyjny):** Horyzontalny wykres wydajnościowy monitorujący błędy API oraz średni czas odpowiedzi (`ms`).
   * **Interaktywność (Slicers):** Globalny fragmentator *Linia Lotnicza* (*Airline Slicer*) połączony relacyjnie z wieloma tabelami i wykresami naraz, umożliwiający błyskawiczne filtrowanie danych w czasie rzeczywistym.
4. **Podgląd Dashbordu**:
<img width="1483" height="714" alt="Zrzut ekranu 2026-11-03 130145" src="https://github.com/user-attachments/assets/fe79a37d-270f-4f00-8f1c-60d32051dd5a" />
