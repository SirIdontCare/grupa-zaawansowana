# Advanced Track — Moduł 0: Kokpit (VS Code, koniec z autopilotem)

> 🎯 **To jest bilet wstępu do Advanced Track.** Przejdź Moduł 0, wyślij dowód prowadzącemu — i ruszasz z Modułem 1. Kto nie przejdzie, nic nie traci — wraca do kursu głównego.

## O co chodzi w tej ścieżce

W kursie głównym **zlecałeś** AI: wklejałeś prompt, asystent budował, Ty testowałeś. To była magia — ale magii się nie rozumie, magii się używa.

Advanced Track odwraca to o 180°. Tu **schodzisz pod maskę własnego agenta**: uruchamiasz go ręcznie, czytasz jego kod, wersjonujesz przez git, debugujesz sam. AI zostaje — ale teraz siedzi **w Twoim IDE jako drugi pilot**, a nie jako osobna apka, która robi wszystko za Ciebie.

Pierwszy krok: przesiadka do prawdziwego kokpitu inżyniera — **VS Code**.

> ⚠️ **Wymóg całej ścieżki:** pracujesz w **VS Code + wtyczce z asystentem AI** (GitHub Copilot / Claude Code / Codex). Jeśli kurs główny robiłeś w Codex Desktop czy Antigravity — tutaj przesiadasz się na IDE. **Praca w VS Code to właśnie ta część „zaawansowana".**

## Cel Modułu 0

Po tym module:
- masz zainstalowany VS Code + wtyczkę AI,
- otwierasz w nim swój projekt agenta z kursu głównego,
- uruchamiasz agenta **ręcznie z wbudowanego terminala** (bez proszenia AI o start),
- potrafisz sam znaleźć plik `route.ts` w drzewie projektu.

Zero nowego kodu. Chodzi o to, żebyś **umiał się poruszać** tam, gdzie do tej pory poruszał się za Ciebie asystent.

## Kroki

### 1. Zainstaluj VS Code
Pobierz i zainstaluj z [code.visualstudio.com](https://code.visualstudio.com/). Uruchom.

### 2. Zainstaluj wtyczkę z asystentem AI
W VS Code otwórz panel **Extensions** (ikona klocków po lewej albo `Ctrl+Shift+X`) i zainstaluj JEDNĄ z:
- **GitHub Copilot** (szukaj „GitHub Copilot")
- **Claude Code** (szukaj „Claude Code")
- **Codex / OpenAI** (szukaj „Codex")

Zaloguj się w niej swoim kontem. To Twój drugi pilot — zostaje z Tobą do końca ścieżki.

### 3. Otwórz swój projekt agenta
`File → Open Folder…` → wskaż folder swojego agenta z kursu głównego (ten, w którym jest `package.json`).
Po lewej, w **Explorerze**, zobaczysz drzewo plików całego projektu. To jest mapa Twojego agenta.

### 4. Otwórz wbudowany terminal
Menu: `Terminal → New Terminal` (albo `` Ctrl+` ``). Na dole pojawi się terminal — i **już jesteś w folderze projektu** (nie musisz robić `cd`).

### 5. Uruchom agenta RĘCZNIE
Wpisz kolejno (zatwierdzając Enterem):
```bash
npm install
npm run dev
```
Poczekaj na adres (np. `http://localhost:3000`). Otwórz go w przeglądarce. **Twój agent działa — uruchomiony Twoją ręką, nie promptem.**

### 6. Znajdź `route.ts` — sam
W Explorerze rozwiń: `app` → `api` → `chat` → i otwórz **`route.ts`**.
To jest „mózg" Twojego agenta — plik, do którego w kolejnych modułach będziesz wracał. Na razie tylko go znajdź i otwórz.

> 💡 Nie pytaj AI „gdzie jest route.ts". O to właśnie chodzi w Module 0 — masz to znaleźć sam. Wtyczkę odpalisz przy trudniejszych modułach.

## ✅ Samo-weryfikacja (Twój dowód „done")

Zrób **jeden screenshot**, na którym widać naraz:
1. **drzewo projektu** w Explorerze VS Code (po lewej),
2. otwarty plik **`route.ts`**,
3. **wbudowany terminal** z działającym `npm run dev` (widoczny adres `localhost`).

Dla pewności, że jesteś we właściwym miejscu, wpisz w terminalu VS Code:
```bash
node -v && npm run dev
```
**Oczekiwany wynik:** wersja Node (v18+) i serwer startujący z adresem `localhost`. Jeśli to widzisz — zaliczone.

## 🤖 Sprawdź się sam przez AI (zanim wyślesz prowadzącemu)

Wklej do swojej wtyczki AI ten prompt razem z opisem tego, co zrobiłeś:

> *„Jestem na Module 0 kursu zaawansowanego. Oceń, czy zaliczyłem, wg tej rubryki — odpowiedz PASS albo FAIL + jedno zdanie co poprawić:*
> *1. Czy uruchomiłem projekt z wbudowanego terminala VS Code (nie z osobnej apki AI)?*
> *2. Czy serwer wystartował na localhost?*
> *3. Czy potrafię wskazać, gdzie w drzewie leży app/api/chat/route.ts?*
> *Oto co zrobiłem: [opisz w 3 zdaniach]"*

Jeśli AI zwróci **PASS** — jesteś w domu.

## Jak oddać

Wyślij screenshot **w prywatnej wiadomości (DM) do prowadzącego na Discordzie** — nie na publiczny kanał. To **jedyny moduł oddawany screenshotem**: od Modułu 1 zakładasz własne repozytorium na GitHubie i **od tej pory wysyłasz prowadzącemu na priv link do repo**. Cały Twój dalszy postęp widać w historii commitów, więc wystarczy jeden link.

## Gdzie tkliknąłeś próg zaawansowania

Do tej pory ktoś (AI) uruchamiał Twój projekt za Ciebie. Od teraz **robisz to sam, w narzędziu, w którym pracują prawdziwi inżynierowie.** To nie jest drobiazg — to różnica między „umiem kazać AI zbudować apkę" a „umiem tę apkę prowadzić". Reszta ścieżki stoi na tym fundamencie.
