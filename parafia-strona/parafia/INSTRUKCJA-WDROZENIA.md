# Instrukcja wdrożenia strony parafii

Ta strona jest gotowa do wdrożenia na **Netlify** — darmowym, bezpiecznym hostingu
bez bazy danych i bez panelu typu WordPress. Dzięki temu nie ma się co włamać.

## Krok 1 — Załóż konto GitHub (jeśli nie masz)

1. Wejdź na github.com i załóż darmowe konto.
2. Stwórz nowe repozytorium (np. `parafia-swkrzysztofa`) i wgraj do niego
   wszystkie pliki z tego folderu.

## Krok 2 — Załóż konto Netlify i połącz z repozytorium

1. Wejdź na netlify.com, załóż darmowe konto (może być przez GitHub).
2. Kliknij "Add new site" → "Import an existing project" → wskaż repozytorium
   z Kroku 1.
3. Netlify wdroży stronę automatycznie i nada jej adres typu
   `nazwa-losowa.netlify.app`. Można potem podpiąć własną domenę
   (np. parafiaswkrzysztofa.pl) w Site settings → Domain management.

## Krok 3 — Włącz logowanie (Netlify Identity)

1. W panelu Netlify: Site settings → Identity → **Enable Identity**.
2. W sekcji "Registration" ustaw **Invite only** (WAŻNE — to blokuje
   zakładanie kont przez obcych).
3. W sekcji "Services" → Git Gateway → **Enable Git Gateway**.

## Krok 4 — Zaproś operatora ogłoszeń

1. Nadal w sekcji Identity: kliknij **Invite users**, podaj e-mail osoby,
   która ma dodawać ogłoszenia.
2. Osoba dostanie e-mail z linkiem, ustawi sobie hasło — i to wszystko.

## Jak operator dodaje ogłoszenia (do przekazania osobie odpowiedzialnej)

1. Wejdź na **twojastrona.netlify.app/admin**
2. Zaloguj się e-mailem i hasłem.
3. Kliknij "Ogłoszenia duszpasterskie" → "+ Nowe ogłoszenie".
4. Wypełnij: tytuł, treść, data.
   - Zaznacz fragment tekstu i kliknij **B**, żeby go pogrubić.
   - Zaznacz "Oznacz jako ważne", żeby wyróżnić ogłoszenie na liście.
   - Zaznacz "Przypnij na górze strony", żeby ogłoszenie było na samej górze
     (np. odwołana Msza, pilny komunikat). Odznacz, gdy przestanie być aktualne.
5. Kliknij "Publish" (Opublikuj). Zmiana pojawi się na stronie po 30–60 sekundach.

## O bezpieczeństwie

- Strona nie ma bazy danych ani serwera PHP — nie da się jej zhackować
  typowymi atakami na WordPressa czy podobne systemy.
- Logowanie działa tylko dla zaproszonych e-maili (Invite only) —
  nikt obcy nie założy sobie konta.
- Cała historia zmian ogłoszeń jest zapisywana automatycznie (przez Git),
  więc nawet przypadkowe skasowanie da się cofnąć.
- Strona ma włączone nagłówki bezpieczeństwa (plik `_headers`) chroniące
  przed najczęstszymi atakami w przeglądarce.

## Kontakt w razie problemów

Jeśli coś nie działa lub trzeba dodać osobę do panelu, potrzebny jest dostęp
do konta Netlify (najlepiej niech ma go administrator strony, np. ktoś
zaufany z parafii lub informatyk).
