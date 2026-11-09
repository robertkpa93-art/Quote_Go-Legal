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
- [x] Test usunięcia osobnego konta z aplikacji: komunikat sukcesu i powrót do trybu demonstracyjnego (potwierdzone zdjęciem 09.11.2026). Ponowne logowanie usuniętym kontem nie było odrębnie testowane.
- [x] Kontrola Supabase 09.11.2026: operator potwierdził brak konta w Authentication → Users; zapytanie LEFT JOIN do auth.users wykazało **0 osieroconych rekordów** we wszystkich sześciu tabelach podstawowych. To nie jest pełny audyt logów, backupów ani wszystkich danych przypisanych konkretnemu UUID.
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
