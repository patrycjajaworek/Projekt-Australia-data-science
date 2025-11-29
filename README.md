# Road Crash Analysis – Data Science Project (Erasmus+, Politecnico di Milano)

Projekt został zrealizowany podczas wymiany Erasmus+ na Politecnico di Milano, w ramach kursu poświęconego praktycznym zastosowaniom analizy danych oraz metod uczenia maszynowego.  
Celem pracy była szczegółowa analiza danych dotyczących wypadków drogowych w stanie Victoria (Australia) oraz identyfikacja różnych czynników środowiskowych, infrastrukturalnych i behawioralnych wpływających na ciężkość obrażeń uczestników zdarzeń.

Projekt obejmował pełny proces data-science: od integracji danych pochodzących z wielu źródeł, poprzez czyszczenie, preprocessing i eksploracyjną analizę danych, aż po inżynierię cech oraz budowę modeli predykcyjnych.  
Dane wymagały połączenia informacji o warunkach atmosferycznych, stanie nawierzchni oraz cechach uczestników ze szczegółowymi danymi o samych wypadkach co wiązało się z koniecznością starannego obchodzenia się z danymi niejednorodnymi i częściowo niekompletnymi.

W ramach EDA przeanalizowano zależności pomiędzy warunkami pogodowymi, oświetleniem, typem drogi, ograniczeniami prędkości oraz rolami kierowców a ciężkością obrażeń. Wykorzystano liczne metody wizualizacji i analizy statystycznej, aby ujawnić wzorce i zależności mające znaczenie dla bezpieczeństwa drogowego.  
Następnie zbudowano model klasyfikacyjny Random Forest służący do przewidywania stopnia obrażeń, a jego jakość oceniono m.in. za pomocą accuracy, precision, recall, balanced accuracy oraz analizy istotności cech.

Projekt dostarczył praktycznego doświadczenia w pracy z rzeczywistymi danymi, współpracy w zespole projektowym oraz zastosowaniu metod uczenia maszynowego w kontekście problemu o dużym znaczeniu społecznym i infrastrukturalnym.

## Cele projektu

- połączenie i ujednolicenie danych pochodzących z różnych źródeł (warunki atmosferyczne, stan nawierzchni, informacje o uczestnikach, szczegóły zdarzenia), tak aby stworzyć kompletny i spójny zbiór do analizy,
- przeprowadzenie eksploracyjnej analizy danych (EDA) w celu identyfikacji kluczowych wzorców, anomalii oraz zależności między czynnikami środowiskowymi, infrastrukturalnymi i behawioralnymi,
- opracowanie i przetestowanie modelu predykcyjnego oceniającego prawdopodobieństwo wystąpienia poważnych obrażeń w wypadkach drogowych, z wykorzystaniem technik uczenia maszynowego,
- interpretacja wyników oraz prezentacja najważniejszych wniosków dotyczących czynników wpływających na bezpieczeństwo drogowe.


## Dane

Wykorzystane zbiory:

- `victorian_road_crash_data.csv`  
- `atmospheric_cond.csv`  
- `person.csv`  
- `road_surface_cond.csv`  

Zbiory połączono kluczem `ACCIDENT_NO`.

---

# Wizualizacje i analiza eksploracyjna (EDA)

W ramach eksploracyjnej analizy danych przygotowano zestaw wizualizacji pokazujących kluczowe zależności w danych dotyczących wypadków drogowych.  
Wykresy przedstawiają wpływ warunków środowiskowych, infrastruktury oraz czynników behawioralnych na liczbę zdarzeń oraz poziom obrażeń uczestników.  

### Wpływ warunków oświetleniowych na liczbę i ciężkość wypadków  
![Light Conditions](light_condition.jpg)

Powyższa wizualizacja przedstawia zestawienie liczby wypadków drogowych w różnych warunkach oświetleniowych oraz udział wypadków poważnych i śmiertelnych (Serious & Fatal). Wykres podzielony jest na trzy części:

#### **1. All Accidents – ogólna liczba wypadków**
Najwięcej zdarzeń drogowych ma miejsce w świetle dziennym. Wynika to z faktu, że ruch drogowy jest wtedy zdecydowanie największy.  
W warunkach nocnych — zarówno na drogach oświetlonych, jak i nieoświetlonych — wypadków jest znacznie mniej, co odzwierciedla niższe natężenie ruchu.

#### **2. Serious & Fatal – liczba wypadków poważnych i śmiertelnych**
Podobnie jak w poprzednim przypadku, najwięcej poważnych zdarzeń występuje za dnia ale wynika to z ogólnej dominacji liczbowej.  
Ciekawa różnica pojawia się przy zdarzeniach nocnych: mimo mniejszej liczby wypadków, udział poważnych i śmiertelnych przypadków rośnie.

#### **3. Serious/Fatal Share (%) – udział procentowy najcięższych wypadków**
W tej części widać najważniejszy wniosek z całego wykresu.  
Procentowy udział poważnych obrażeń jest najwyższy w warunkach:

- **Dark (Unlit) – 52.2%**  
- **Dark (Lit) – 40.8%**  
- **Daylight – 36.7%**  
- **Low Light – 34.9%**  
- **Dark (Unknown) – 27%**  
- **Unknown – 14.4%**

Warunki „Dark (Unlit)” oraz „Dark (Lit)” mają wyraźnie większy udział zdarzeń poważnych, mimo że całkowita liczba wypadków jest tam niższa.

---

### **Wnioski**
- Warunki oświetleniowe są jednym z kluczowych czynników związanych z ciężkością wypadków drogowych.  
- Choć w dzień wypadków jest najwięcej, to noc — szczególnie na drogach **nieoświetlonych** — znacząco zwiększa prawdopodobieństwo poważnych lub śmiertelnych obrażeń.  






# Analiza i modelowanie

## Feature Importance (Random Forest)
*(tutaj screen wykresu ważności cech)*  
`![Feature Importance](#)`

---

## Wyniki modeli

Możesz wkleić tabelę albo screen:

### Tabela (jeśli wolisz tekst)

| Model            | Accuracy | Precision | Recall | Balanced Accuracy |
|------------------|----------|-----------|--------|-------------------|
| Random Forest    | 0.87     | 0.81      | 0.79   | 0.85              |
| Logistic Reg.    | 0.74     | 0.69      | 0.66   | 0.72              |
| Decision Tree    | 0.79     | 0.75      | 0.70   | 0.76              |

### Albo screen tabeli / macierzy pomyłek  
`![Model Results](#)`

---

## Przebieg analizy

- czyszczenie danych i łączenie plików CSV,  
- eksploracja danych, statystyki opisowe,  
- wizualizacje kluczowych zmiennych,  
- budowa modelu predykcyjnego (Random Forest),  
- ocena jakości modelu,  
- identyfikacja najważniejszych czynników wpływających na skutki wypadków.

---

## Rola w zespole

Projekt zrealizowany był w 4-osobowym zespole.

**Mój wkład:**

- przygotowanie i łączenie danych,  
- część EDA i wizualizacji,  
- udział w budowie i ocenie modelu,  
- współtworzenie wniosków i podsumowania.

---

## Podsumowanie

Projekt obejmuje pełny proces data-science: od surowych danych, przez wizualizacje i analizę, aż po model predykcyjny.  
Wyniki wskazują m.in. istotny wpływ prędkości, liczby uczestników i warunków oświetleniowych na powagę obrażeń.
