# QuoteGo — kontrola przed zaproszeniem 10 testerów

Stan roboczy: 9 listopada 2026 r. Dokument techniczny dla operatora, **nie zastępuje polityki prywatności ani porady prawnej**.

## Potwierdzone
- [x] Oddzielne publiczne repozytorium na dokumenty; kod aplikacji pozostaje prywatny.
- [x] Publiczne strony z **projektami** polityki i zasad testów oraz instrukcją żądania usunięcia konta.
- [x] W kodzie jest `delete_my_account`; sześć podstawowych tabel ma `ON DELETE CASCADE`.
- [x] Właściciel potwierdził, że w używanym APK widzi przycisk „Usuń konto”.
- [x] Właściciel potwierdził, że PDF działa w ostatnim APK.
- [x] W poprzednim odczycie Supabase sześć podstawowych tabel miało włączony RLS.

## Do sprawdzenia przed zaproszeniem
- [ ] Test usunięcia osobnego konta: zalogowanie, fikcyjny klient, fikcyjna wycena, usunięcie, odrzucenie ponownego logowania.
- [ ] Odczyt kontrolny w Supabase: brak rekordu Auth oraz danych konta we wszystkich sześciu tabelach. Nie wpisywać haseł ani tokenów do SQL.
- [ ] Potwierdzenie regionu projektu Supabase, kategorii logów, zasad retencji i dostępnych umów dotyczących przetwarzania danych.
- [ ] Ustalenie podstaw prawnych i ról wobec danych kont testerów oraz danych klientów fachowców; w becie używać wyłącznie fikcyjnych danych klientów.
- [ ] Zatwierdzenie finalnej polityki i zasad testów, z datą wejścia w życie. Usunięcie oznaczenia „PROJEKT” dopiero po weryfikacji.
- [ ] Potwierdzenie dostępności publicznych adresów HTTPS oraz zgodności linków użytych w APK z finalnymi dokumentami.
- [ ] Sprawdzenie uprawnień i funkcji rzeczywiście dostępnych w wersji APK, w tym zachowania lokalnych plików po usunięciu konta.
- [ ] Osobna kontrola deklaracji Google Play, jeśli beta będzie dystrybuowana przez Google Play.

## Zakres świadomie wyłączony
Nie wdrażamy obecnie tabel ani migracji LIVE, Showtime, chmurowych kopii szkiców i dokumentów. Brak tych tabel **nie jest samodzielnie blockerem ograniczonej bety**, o ile aplikacja nie próbuje korzystać z nieuruchomionych funkcji.

## Test bezpieczny
Wykorzystać **nowe, jednorazowe konto**, a nie główne konto właściciela. Dane klienta i wyceny muszą być fikcyjne. Po usunięciu konta sprawdzić też pliki lokalne na urządzeniu.

Kontakt do operatora: robertkpa93@gmail.com.
