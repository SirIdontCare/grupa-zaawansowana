# Grupa Zaawansowana — od użytkownika AI do inżyniera

Autorska ścieżka dla osób, które chcą przestać *zlecać* AI budowanie aplikacji, a zacząć **rozumieć i kontrolować** własny kod. Zamiast wklejać prompty do gotowej apki — schodzisz pod maskę: VS Code, git, czytanie kodu, debugowanie, pisanie funkcji ręcznie.

> Autor: **Paweł Paruzel**

## Dla kogo

Dla każdego, kto zbudował już aplikację z pomocą asystenta AI i czuje, że chce **naprawdę** zapanować nad tym, co powstaje pod spodem.

## Wymagania

- **VS Code + wtyczka z asystentem AI** (GitHub Copilot / Claude Code / Codex) — wymóg.
- **Node.js 18+**, **Git**, konto **GitHub**.
- (Bonus) **Python 3.11+** — do modułu z backendem.

## Jak to działa

> 🛑 **Pełna izolacja od kursu — to warunek wejścia.** Całą ścieżkę robisz na **kopii swojego agenta po Lekcji 7**, która ma:
> - **osobny folder** (z usuniętym `.git`, żeby nie ciągnąć powiązania z repo kursowym),
> - **osobną bazę danych** (nowy projekt Supabase / Neon),
> - **osobne repo na GitHubie** i **żadnego deployu** — pracujesz lokalnie (`npm run dev`).
>
> Twój projekt kursowy, jego baza i jego wersja na Vercelu zostają **nietknięte** — na nich idziesz dalej na zwykłych zajęciach. Bez tej izolacji eksperymenty z tej ścieżki potrafią rozwalić kurs. Wszystko ustawiasz w [Module 0](W0_KOKPIT.md) i [Module 1](W1_GIT_GITHUB.md).

Ścieżka jest **samoobsługowa** i idziesz nią własnym tempem:

1. Robisz zadanie z modułu na swoim projekcie.
2. Sprawdzasz się sam — wklejasz swój kod + dołączoną rubrykę do swojej wtyczki AI (PASS/FAIL).
3. Oddajesz dowód: **Moduł 0** — screenshot, **od Modułu 1** — link do repo na GitHubie.
4. **Moduł 0 to bilet wstępu** — kto go przejdzie, idzie dalej.

## Mapa ścieżki

### Ścieżka główna — te moduły trzeba przejść

| # | Moduł | Czego się nauczysz |
|---|---|---|
| **0** | [Kokpit: VS Code, koniec z autopilotem](W0_KOKPIT.md) | VS Code, terminal, uruchomienie projektu ręcznie |
| **1** | [Wersjonowanie jak inżynier](W1_GIT_GITHUB.md) | git + GitHub, commity, cofanie zmian |
| **2** | [Czytaj kod, który AI napisało](W2_CZYTANIE_KODU.md) | czytanie kodu, śledzenie przepływu danych |
| **2.5** | [Elementarz kodu](W2.5_ELEMENTARZ_KODU.md) | zmienne, funkcje, `if`, `return` — rozgrzewka, ~30 min |
| **3** | [Debugowanie bez AI](W3_DEBUG.md) | stack trace, `console.log`, debugger — na projekcie [`debug_agent/`](debug_agent) |
| **4** | [Capstone: zmiana bez generatora](W4_CAPSTONE.md) | własna funkcja pisana ręcznie + Pull Request |

**Ukończenie Modułów 0–4 = pełne zaliczenie Grupy Zaawansowanej.** Każdy moduł ma na końcu sekcję **„Idź dalej"** z dodatkowymi ćwiczeniami dla chętnych.

### Moduły ponadprogramowe — dla chętnych

| Moduł | Czego się nauczysz |
|---|---|
| ⭐ [Extra 1: Twoja baza od środka](E1_BAZA_OD_SRODKA.md) | SQL, tabele, własne zapytania do bazy agenta |
| ⭐ [Extra 2: Panuj nad kosztami agenta](E2_KOSZTY_AGENTA.md) | audyt kosztów, płatne przełączniki, limity, tokeny |

### Poziom wyżej

| Moduł | Czego się nauczysz |
|---|---|
| 🐍 [Bonus: Twój agent na backendzie w Pythonie](W5_BONUS_PYTHON.md) | FastAPI, architektura klient–serwer, drugi język |

> 🐍 **Bonus (Python) to osobny, wyższy poziom** — nie część głównej ścieżki, tylko krok ponad nią. Dla tych, którzy chcą sięgnąć jeszcze wyżej.

## Efekt

Po tej ścieżce przestajesz być „użytkownikiem AI" — zostajesz osobą, która **panuje nad swoim projektem**: pracuje w prawdziwym IDE, wersjonuje przez git, czyta cudzy kod, łapie błędy sama i wdraża zmiany jak inżynier.

---

© Paweł Paruzel. Materiały autorskie.
