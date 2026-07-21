# Grupa Zaawansowana — Moduł 4: Capstone — zmiana bez generatora

> 🔒 **Wymagane wejście:** zaliczone Moduły 1–3.

## O co chodzi

To jest finał. Składasz wszystko razem: **VS Code** (M0), **git + GitHub** (M1), **czytanie kodu** (M2) i **debugowanie** (M3) — żeby zrobić rzecz, której przez cały kurs nie robiłeś: **dodać do swojego agenta nową funkcję, pisząc kod ręcznie.**

Reguła: **nie każesz AI wygenerować całości.** Autouzupełnianie wtyczki może podpowiadać Ci pojedyncze linie, ale **to Ty piszesz to narzędzie i rozumiesz każdy jego fragment.** Na koniec robisz to jak inżynier w zespole: na osobnej gałęzi (branch) i przez **Pull Request**.

## Cel

Po tym module:
- dodałeś do agenta **nowe narzędzie**, pisząc je samodzielnie,
- agent faktycznie go używa (widać to w przeglądarce),
- zrobiłeś to na **osobnej gałęzi** i przez **Pull Request** na GitHubie,
- potrafisz opisać w PR, **co** dodałeś i **jak** to działa.

## Zadanie: narzędzie „Podziel rachunek"

Dodasz agentowi narzędzie `splitBill`, które dzieli rachunek na osoby (z opcjonalnym napiwkiem). Po zmianie agent powinien poprawnie odpowiedzieć na: *„Podziel 240 zł na 4 osoby z napiwkiem 10%"*.

> 💡 Chcesz własny pomysł zamiast dzielenia rachunku (np. przelicznik walut offline, kalkulator BMI, licznik słów)? Śmiało — byle miał tę samą strukturę narzędzia i realnie coś liczył. Reszta instrukcji zostaje taka sama.

### 1. Załóż gałąź na swoją zmianę
```bash
git checkout -b feature/split-bill
```
Od teraz pracujesz „na boku", nie ruszając głównej wersji.

### 2. Znajdź, gdzie mieszkają narzędzia
Otwórz `app/api/chat/route.ts` (umiesz to z Modułu 2). Znajdź obiekt `tools: { ... }` — to tam siedzą kalkulator, data/czas itd. **Przeczytaj narzędzie `calculator`** — będzie Twoim wzorem. Zwróć uwagę na jego trzy części:
- `description` — kiedy agent ma go użyć,
- `inputSchema` — jakie dane przyjmuje (zod),
- `execute` — co robi i co zwraca.

### 3. Napisz narzędzie `splitBill` — ręcznie
Dopisz do obiektu `tools` nowe narzędzie. Szkielet poniżej — ale **`execute` piszesz sam** (to jest sedno modułu):
```js
splitBill: tool({
  description: "Dzieli kwotę rachunku na osoby, z opcjonalnym napiwkiem w procentach.",
  inputSchema: z.object({
    total: z.number().describe("Łączna kwota rachunku"),
    people: z.number().describe("Liczba osób"),
    tipPercent: z.number().optional().describe("Napiwek w procentach, np. 10"),
  }),
  execute: async ({ total, people, tipPercent = 0 }) => {
    // TODO (Twoja robota):
    // 1. Zabezpiecz się przed dzieleniem przez zero (people <= 0).
    // 2. Dolicz napiwek do kwoty.
    // 3. Policz kwotę na osobę.
    // 4. Zwróć obiekt, np. { total, people, tipPercent, perPerson }.
  },
}),
```
Nie potrzebujesz nowych importów — `tool` i `z` są już w tym pliku.

### 4. Uruchom i przetestuj w przeglądarce
```bash
npm run dev
```
Wejdź na stronę czatu i zapytaj: **„Podziel 240 zł na 4 osoby z napiwkiem 10%"**.
Oczekiwana odpowiedź: 240 + 10% = 264, na 4 osoby = **66 zł/os.** Jeśli agent liczy dobrze — działa.

> Jeśli coś nie gra — wróć do Modułu 3: przeczytaj błąd, wrzuć `console.log` do `execute`, znajdź przyczynę. **Sam.**

### 5. Zacommituj zmianę na gałęzi
```bash
git add .
git commit -m "Dodane narzedzie splitBill: dzielenie rachunku z napiwkiem"
```

### 6. Wypchnij gałąź i otwórz Pull Request
```bash
git push -u origin feature/split-bill
```
Wejdź na swoje repo na GitHubie — pojawi się żółty pasek **„Compare & pull request"**. Kliknij go i **napisz opis PR** (własnymi słowami):
- **Co** dodałeś (narzędzie splitBill),
- **Jak** działa (co przyjmuje, co zwraca, jak liczy napiwek),
- **Jak przetestowałeś** (jakie pytanie zadałeś agentowi i co odpowiedział).

Kliknij **Create pull request**, a potem **Merge pull request** → **Confirm merge**.

## ✅ Samo-weryfikacja (Twój dowód „done")

- Agent w przeglądarce poprawnie dzieli rachunek (66 zł/os. dla przykładu wyżej).
- Na GitHubie masz **zmergowany Pull Request** z sensownym opisem.
- Zmiana jest w gałęzi głównej repo.

## 🤖 Sprawdź się sam przez AI (zanim wyślesz prowadzącemu)

Wklej do wtyczki AI swój kod narzędzia + opis PR:

> *„Jestem na Module 4 (capstone). Dodałem ręcznie narzędzie do agenta. Oto kod: [wklej splitBill] i opis PR: [wklej]. Oceń wg rubryki — PASS/FAIL + jedno zdanie:*
> *1. Czy narzędzie ma poprawny `inputSchema` (zod) i sensowny `description`?*
> *2. Czy `execute` liczy poprawnie (napiwek + podział) i zabezpiecza dzielenie przez zero?*
> *3. Czy opis PR własnymi słowami wyjaśnia, co i jak działa (a nie wygląda na wygenerowany w całości)?"*

## Jak oddać

Wyślij **w DM do prowadzącego**:
1. **link do repo**,
2. **link do zmergowanego Pull Requesta**,
3. jedno zdanie: „Moduł 4 (capstone) gotowy".

## Gratulacje — skończyłeś Grupę Zaawansowaną 🎉

Przeszedłeś drogę od „wklejam prompty, AI buduje" do:
- pracy w prawdziwym IDE,
- wersjonowania i współpracy przez git + GitHub + Pull Requesty,
- czytania cudzego kodu i wskazywania palcem, gdzie co jest,
- łapania i naprawiania błędów bez podpowiadacza,
- **napisania własnej funkcji ręcznie i wdrożenia jej jak inżynier.**

To nie jest już „użytkownik AI". To ktoś, kto panuje nad swoim projektem.

## Chcesz więcej? → Bonus: trzeci agent z backendem (Python) — POZIOM WYŻEJ

Skończenie Modułów 0–4 to **pełne ukończenie Grupy Zaawansowanej**. Bonus z Pythonem to **osobny, jeszcze wyższy poziom** — już nie część tej ścieżki, tylko krok ponad nią.

Tu budujesz od zera **trzeciego agenta z prawdziwym backendem w Pythonie (FastAPI)** — inny język, inny stack, prawdziwa architektura klient–serwer. To jest w pełni opcjonalne i przeznaczone dla osób, które chcą wyjść poza to, co robiliśmy do tej pory. Plik: `W5_BONUS_PYTHON.md`.

> Nie czujesz się na siłach? **Nie musisz.** Ukończenie Modułu 4 to komplet — bonus jest dla tych, którzy chcą sięgnąć piętro wyżej.
