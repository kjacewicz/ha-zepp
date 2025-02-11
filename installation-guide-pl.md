# Jak zainstalować HA na zegarku Zepp, aby kontrolować swoje urządzenia?

### Spis treści
- Kompatybilne modele
- Funkcje aplikacji
- Instalacja aplikacji
- Przygotowanie
- Instalacja za pomocą instalatora
- Instalacja przez terminal
- Konfiguracja aplikacji
- Podziękowania i kredyty

# Kompatybilne modele
Dzięki członkom naszej społeczności mogliśmy przetestować i dostosować aplikację do następujących modeli:
- Amazfit GTS 3
- Amazfit GTR 3
- Amazfit GTR 3 Pro
- Amazfit GTS 4 Mini
- Amazfit GTS 4
- Amazfit GTR 4
- Amazfit Cheetah Pro
- Amazfit Active
- Amazfit Active Edge
- Amazfit Balance
- Amazfit T-REX 2
- Amazfit Bip 5 Unity
- Amazfit Band 7
- Xiaomi Band 7 (w tym przypadku konieczny jest dodatkowy krok – sprawdź ten wpis).

Pracujemy nad aktualizacją aplikacji, aby była kompatybilna z większą liczbą 
urządzeń Zepp. Jeśli masz model, który nie znajduje się na liście, 
dołącz do naszej społeczności na Telegramie, aby go przetestować! Jeśli 
planujesz zakup zegarka, polecamy sprawdzić ceny w oficjalnym sklepie 
Amazfit Global Retail Store na AliExpress.

# Funkcje aplikacji
Po zainstalowaniu HA na swoim zegarku Zepp będziesz mógł:
- Wyświetlać swoje encje w trzech kategoriach: urządzenia, skrypty i sensory.
- Kontrolować swoje urządzenia: włączać i wyłączać gniazdka oraz światła, zmieniać jasność i efekty (jeśli są obsługiwane) oraz zarządzać multimediami.
- Uruchamiać swoje skrypty i automatyzacje.
- Wyświetlać informacje z czujników

Po zainstalowaniu HA na swoim zegarku Zepp będziesz mógł również przeglądać informacje z podłączonych czujników.

# Przygotowanie

1. Jeśli jeszcze tego nie zrobiłeś, pobierz i zainstaluj aplikację Zepp (dawniej Amazfit) na swoim urządzeniu mobilnym. Następnie utwórz konto i zaloguj się.
- Zepp (dawniej Amazfit)
📌 Cena: Darmowa
2. Teraz wykonaj następujące kroki:
Przejdź do Profil > Ustawienia > Informacje i kilkukrotnie naciśnij logo Zepp, aż pojawi się komunikat: „Tryb dewelopera został aktywowany”.
3. Kolejnym krokiem będzie zbudowanie i instalacja aplikacji Home Assistant (brzmi skomplikowanie, ale przeprowadzę Cię przez wszystkie etapy).
Przygotowanie środowiska deweloperskiego:
* Zainstaluj Node.js: Pobierz wersję oznaczoną jako „Recommended For Most Users” i zainstaluj.
* Zainstaluj Git: Pobierz najnowszą wersję, uruchom instalator i zakończ instalację.
* Zarejestruj się w konsoli deweloperskiej Zepp (nie używaj konta Google). To konieczne do instalacji HA na zegarku.

Jesteś już prawie gotowy! Teraz możemy przejść do właściwej instalacji aplikacji.

Instalacja aplikacji
Masz dwie opcje:
- Instalacja za pomocą instalatora (najprostsza metoda).
- Instalacja ręczna przez terminal (dla bardziej zaawansowanych użytkowników).

# Instalacja za pomocą instalatora
1. Pobierz plik instalacyjny, rozpakuj go i uruchom.
2. Wybierz język (1 dla hiszpańskiego, 2 dla angielskiego) i naciśnij Enter.
3. Naciśnij 4 i Enter, aby zainstalować Zeus CLI (oprogramowanie do tworzenia aplikacji Zepp). Zamknij okno po zakończeniu instalacji.
4. Naciśnij 5 i Enter, aby sprawdzić wersję Zeus CLI. Jeśli zobaczysz numer wersji, wszystko poszło zgodnie z planem.
5. Naciśnij 6 i Enter, aby zainstalować aplikację Home Assistant (lub ją zaktualizować). Po zakończeniu instalacji naciśnij dowolny klawisz.
6. Naciśnij 7 i Enter, wybierz swój zegarek z listy (użyj strzałek, jeśli potrzebujesz przewinąć). Na ekranie pojawi się kod QR.
7. Otwórz aplikację Zepp na telefonie i przejdź do Profil > Twój zegarek > Tryb dewelopera.
Stuknij ikonę „+” w prawym górnym rogu, wybierz Skanuj i zeskanuj kod QR. Poczekaj na zakończenie instalacji.
Na zegarku w menu powinna pojawić się opcja Home Assistant!

# Instalacja ręczna przez terminal
Jeśli preferujesz ręczną instalację lub napotkałeś błąd, wykonaj następujące kroki:
1. Otwórz terminal systemowy (cmd) i wpisz:
npm i @zeppos/zeus-cli -g
To zainstaluje Zeus CLI.
2. Po zakończeniu instalacji sprawdź, czy działa poprawnie:
zeus -v
Jeśli zobaczysz numer wersji, wszystko poszło zgodnie z planem.
💡 Jeśli otrzymasz błąd „npm ERR! code EBUSY”, wpisz:
npm install -g npm@latest
a następnie powtórz instalację.
5. Pobierz aplikację Home Assistant:
git clone https://github.com/TitoTB/ha-zepp
cd ha-zepp
zeus preview

6. Po uruchomieniu ostatniego polecenia otworzy się konsola deweloperska Zepp w Twojej przeglądarce. Zaloguj się na wcześniej utworzone konto.
7. Wróć do terminala i wybierz swój zegarek z listy (użyj strzałek, jeśli trzeba przewinąć). Na ekranie pojawi się kod QR.
8. Otwórz aplikację Zepp na telefonie i przejdź do Profil > Twój zegarek > Tryb dewelopera.
Stuknij ikonę „+” w prawym górnym rogu, wybierz Skanuj i zeskanuj kod QR. Poczekaj na zakończenie instalacji.
Sprawdź w menu zegarka, czy pojawiła się opcja Home Assistant.

# Konfiguracja aplikacji
Teraz musimy połączyć aplikację z instancją Home Assistant. W aplikacji Zepp przejdź do:
Profil > Twój zegarek > Tryb dewelopera > Mini Program > Home Assistant (Settings).
Wprowadź następujące dane:
* Local HA instance address – np. http://homeassistant.local:8123/
* External HA instance address – np. https://twojadomena.com/
* Long access token – wygeneruj go w Home Assistant:
Otwórz aplikację HA na telefonie, przejdź do menu bocznego i kliknij swoją nazwę użytkownika.
Przewiń na dół, wybierz „Utwórz token”, nazwij go (np. „XiaomiBand7”) i skopiuj kod.
Wklej kod w aplikacji Zepp.

Wybór encji:
Możesz wyszukiwać encje według nazwy, domeny lub wyświetlić pełną listę.
Naciśnij „Search”, aktywuj wybrane encje i użyj przycisku „Top”, aby je uporządkować.

# Podziękowania i kredyty
Aplikacja została stworzona na bazie projektu ga2mer oraz koncepcji kategoryzacji encji od shorty88.
Społeczność aguacatec (Barny i Tito) opracowała nową wersję, poprawiając interfejs i dodając wsparcie dla większej liczby zegarków Zepp OS.
🔹 Teraz możesz sterować swoim domem bezpośrednio z zegarka Zepp! 🎉

Przetłumaczone na podstawie http://web.archive.org/web/20241103093642/https://aguacatec.es/instalar-ha-en-tu-reloj-zepp/
