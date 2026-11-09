# QuoteGo — wewnętrzna dokumentacja ochrony danych (beta)

**Stan: 09.11.2026 — roboczy, do potwierdzenia przez operatora.** Dokument nie jest publiczną polityką ani opinią prawną. Nie wpisuj tu haseł, kluczy API, tokenów ani danych prawdziwych klientów.

## 1. Roboczy rejestr czynności przetwarzania
| Proces | Kategorie osób i danych | Cel | Wstępna podstawa | Odbiorcy/system | Retencja / usunięcie | Stan |
|---|---|---|---|---|---|---|
| Konta i logowanie | Testerzy: e-mail, identyfikator, dane uwierzytelnienia | Dostęp do aplikacji | art. 6(1)(b) RODO — do potwierdzenia | Supabase Auth | W czasie konta; backupy/logi nieustalone | Częściowo sprawdzone |
| Profil i wyceny | Testerzy: profil firmy, fikcyjne wpisy klientów i wycen | Funkcje aplikacji | art. 6(1)(b) dla konta; role przy prawdziwych klientach nieustalone | Supabase, urządzenie | Rekordy podstawowe kaskadowo usuwane; pliki lokalne osobno | Częściowo sprawdzone |
| Wsparcie i bezpieczeństwo | E-mail, zgłoszenia, potencjalne logi | Obsługa błędów, bezpieczeństwo | art. 6(1)(f) — wymaga testu równowagi | Poczta, potencjalne usługi techniczne | Do ustalenia według rzeczywistych systemów | Niezweryfikowane |

Przed przyjęciem prawdziwych danych klientów trzeba ustalić role administrator/podmiot przetwarzający i odpowiednie warunki powierzenia (art. 28 RODO). Beta: wyłącznie fikcyjne dane klientów.

## 2. Mapa dostawców i transferów — do weryfikacji
- **Supabase**: ustalić region konkretnego projektu, podmiot umowny, DPA, podwykonawców, transfery i mechanizmy transferowe, okresy przechowywania logów i kopii. Nie zakładać automatycznie, że region UE oznacza brak transferów.
- **Wysyłka e-maili uwierzytelniających**: ustalić rzeczywistego dostawcę i sposób konfiguracji; nie zgadywać.
- **Aplikacja i APK**: przejrzeć faktycznie włączone SDK, telemetrię, crash reporting, uprawnienia Androida, lokalne pliki PDF/zdjęcia. Nie przypisywać przetwarzania niewłączonym funkcjom.
- **Hosting dokumentów GitHub Pages**: publiczne strony informacyjne; nie umieszczać na nich danych użytkowników ani sekretów.

## 3. Zasady retencji — do ustalenia
- Konto i rekordy podstawowe: w okresie istnienia konta; usunięcie w aplikacji przetestowane 09.11.2026, brak orphanów w sześciu tabelach.
- Logi uwierzytelniania, bezpieczeństwa, poczta, backupy: brak potwierdzonych okresów. Sprawdzić rzeczywisty plan i konfigurację usług, nie deklarować natychmiastowego skasowania.
- Dokumenty i szkice zapisane na telefonie: użytkownik usuwa lokalnie; sprawdzić zachowanie po usunięciu konta i odinstalowaniu aplikacji.
- Żądania realizacji praw: ustalić minimalną ewidencję i okres retencji zgłoszeń.

## 4. Procedura zgłoszeń osób
1. Odbiór: robertkpa93@gmail.com. Nie żądać hasła ani kodów OTP.
2. Ustalić rodzaj żądania (dostęp, poprawienie, usunięcie, ograniczenie, sprzeciw, przenoszenie) i niezbędnie potwierdzić tożsamość bez zbierania nadmiernych danych.
3. Sprawdzić, czy QuoteGo jest administratorem danych, czy żądanie dotyczy danych klienta fachowca; w drugim przypadku skierować do właściwego administratora lub współpracować zgodnie z umową.
4. Co do zasady odpowiedzieć bez zbędnej zwłoki, najpóźniej w ciągu miesiąca; w przypadkach przewidzianych prawem można przedłużyć termin o kolejne dwa miesiące, informując o tym w pierwszym miesiącu.
5. Odnotować datę, zakres, czynności i odpowiedź bez zbędnych danych osobowych.

## 5. Procedura naruszenia bezpieczeństwa
1. Zabezpieczyć dostęp, zebrać podstawowe fakty: czas, system, kategorie i szacunkowa liczba osób/rekordów, ryzyko, działania naprawcze.
2. Ocenić ryzyko dla praw i wolności osób. Gdy wymagane, zgłosić naruszenie organowi nadzorczemu bez zbędnej zwłoki, w miarę możliwości w ciągu 72 godzin od stwierdzenia; jeśli później — wyjaśnić opóźnienie.
3. Jeśli prawdopodobne jest wysokie ryzyko, rozważyć obowiązek zawiadomienia osób, z uwzględnieniem wyjątków ustawowych.
4. Dokumentować również incydenty, które nie wymagają zgłoszenia.
5. Nie publikować w repo szczegółów umożliwiających atak ani danych poszkodowanych.

## 6. Minimalne kontrole przed zaproszeniem 10 testerów
- [ ] Region, DPA, transfery, retencja i dostawcy potwierdzone.
- [ ] Faktyczne SDK, uprawnienia i przepływy danych w wydawanym APK sprawdzone.
- [ ] Logowanie, reset hasła i izolacja kont przetestowane na jednorazowych kontach.
- [x] Usuwanie konta i sześciu podstawowych kategorii rekordów przetestowane (nie obejmuje backupów i plików lokalnych).
- [ ] Zasady testów i polityka zatwierdzone, opublikowane i podlinkowane w APK.
- [ ] Użytkownicy otrzymują jasny zakaz prawdziwych danych klientów w becie.
- [ ] Przygotowany kanał zgłoszeń i podstawowa ewidencja incydentów.

**Granica oceny:** ten dokument porządkuje obowiązki; sam nie dowodzi pełnej zgodności z RODO.
