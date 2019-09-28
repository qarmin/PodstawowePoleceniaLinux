# Podstawowe polecenia konsolowe używane w systemie GNU/Linux

To repozytorium zawiera informację o podstawowych komendach używanych w systemie GNU/Linux wraz z krótkimi przykładami.

## Spis treści
1. [Czym jest GNU/Linux, terminal i po co go używać]
2. [Podstawowe polecenia]
2.1 [Katalogi i Pliki]
2.2 [Tekst]
2.3 [Użytkownicy]
2.4 [Uprawnienia]
2.5 [Procesy]
2.6 [Programy i pakiety]
2.7 [Symbole]
2.8 [Archiwa]
2.9 [Inne]
3. [Słowniczek](#Slowniczek)

## Czym jest GNU/Linux, terminal i po co go używać
GNU/Linux jest to system operacyjny, posiadający kernel Linux stworzony przez Linusa Torvaldsa i używający wolnego oprogramowania GNU.

Podstawowym programem używanym w tym systemie jest terminal(w zasadzie emulator terminala) znany również pod swoją angielską nazwą 'shell'.
Umożliwia wpisywanie poleceń w formie tekstowej dlatego zaliczany jest do programów CLI(Command Line Interface), co jest przeciwieństwem dla graficznego interfejsu użytkownika GUI(Graphical User Interface).

Często jest on używany przez nieco bardziej zaawansowanych użytkowników, którzy w ten sposób automatyzują masę rzeczy i oszczędzają czas.

W codziennym użytku może pomóc rozwiązać większość problemów, które można napotkać, gdy coś się zepsuje w systemie oraz wykonać niektóre operacje dużo szybciej niż poprzez graficzny interfejs.

Trzeba przed rozpoczęciem nauki zapamiętać, że Linux, w przeciwieństwie do Windowsa, rozróżnia wielkość liter w nazwach plików oraz poleceń.

Część podstawowych pojęć oraz proces instalacji GNU/Linuxa jest wyjaśniony w repozytorium - https://github.com/qarmin/GNU-Linux-Podstawy/blob/master/README.md#informacje-o-repozytorium

W przypadku błędów o braku dostępu, instrukcję należy poprzedzić poleceniem `sudo` nadającym najwyższe prawa administratora.

Nazwy oznaczone w opisie pojedynczym cudzysłowem(np. 'plik.txt') można dowolnie modyfikować w poleceniu w zależności od oczekiwanego rezultatu

## Podstawowe polecenia
### Katalogi i pliki

`pwd` - Wyświetla ścieżkę w której aktualnie się znajdujemy

`cd` - Polecenie do zmiany aktualnego katalogu
* `cd ..` - Przechodzi jeden katalog do góry
* `cd roman/zawory` - Przechodzi do katalogu 'zawory' znajdującego się wewnątrz innego folderu 'roman'.

`ls` - Polecenie służące do wyświetlenia listy plików i folderów w danym katalogu
* `ls -A` - Wyświetla wszystkie(również ukryte) pliki i foldery
* `ls -l` - Wyświetla informacje o właścicielach plików/folderów, uprawnienia do nich, rozmiar i czas utworzenia.

`mv` - Polecenie do przenoszenia plików oraz katalogów pomiędzy folderami używane również jako narzędzie do zmiany nazwy
* `mv plik.txt mapa` - Przenosi plik 'plik.txt' do folderu mapa
* `mv projekt.rar gniazdo/projekt2.zip` - Przenosi plik 'projekt.rar' do folderu gniazdo i jednocześnie zmienia jego nazwę na 'projekt2.zip'

`cp` - Polecenie używane do tworzenia kopii plików lub folderów w danej lokalizacji
* `cp plik.txt plik2.txt` - Tworzy kopię pliku 'plik.txt' i zapisuje go pod nazwą 'plik2.txt'
* `cp Tapety Tapety2 -R` - Kopiuje folder 'Tapety' do folderu 'Tapety2', dzięki opcji -R kopiuje również wszystkie elementy zawierające się w nim

`mkdir` - Polecenie do tworzenie nowego folderu
* `mkdir polowy` - Tworzy nowy folder 'polowy'

`rmdir` - Polecenie do usuwania podanego katalogu
* `rmdir wideo` - Usuwa katalog o nazwie 'wideo'
* `rmdir --ignore-fail-on-non-empty dokumenty` - Usuwa katalog 'dokumenty' wraz z zawartością

`touch` - Polecenie do tworzenia plików
* `touch plik.txt` - Tworzy pusty plik o nazwie 'plik.txt'

`file` - Polecenie do sprawdzania zawartości pliku
* `file plik.txt` - Wyświetla rodzaj pliku 'plik.txt' bazując na zawartości, nie rozszerzeniu(plik z rozszerzeniem .txt nie musi być plikiem tekstowym)

`cat` - Polecenie do wypisywania zawartości pliku na ekran oraz łączenia kilku plików w jeden.
* `cat plik.txt` - Wyświetla zawartość pliku 'plik.txt' w konsoli
* `cat plik.txt plik2.txt plik.txt` - Łączy zawartość plików 'plik2.txt' oraz 'plik.txt' i wypisuje je na ekran

`rm` - Polecenie służące do usunięcia folderu/pliku
* `rm -r wideo` - Usuwa katalog 'wideo' wraz z zawartością(parametr -r)
* `rm -rf zdjecia` - Usuwa folder 'zdjecia' wraz z zawartością, bez żadnych pytań i ostrzeżeń(opcja -f)
* `rm plik.txt` - Usuwa plik 'plik.txt'

`ln` - Polecenie tworzące dowiązanie(skrót) do plików lub folderów
* `ln -s /home/rafal/aplikacja /usr/bin/aplikacja` - Tworzy skrót(dowiązanie symboliczne) do pliku '/home/rafal/aplikacja' w podanej lokalizacji '/usr/bin/aplikacja'

`locate` - Polecenie do szybkiego wyszukiwania plików, korzystając z bazy danych, określając ich położenie bezwzględne. Bazę można zaktualizować poleceniem `sudo updatedb`
* `locate wszystko.txt` - Wyszukuje w systemie plik 'wszystko.txt'
* `locate -i WiLk` - Szuka w systemie plik lub folder 'WiLk' nie uwzględniając wielkości liter(parametr -i) - pasuje również 'WILK', 'wilk' czy 'WILk'
* `locate "*.png" -n 20` - Wyświetla maksymalnie 20 plików o dowolnej nazwie(* oznacza dowolny ciąg znaków) z rozszerzeniem 'png'
* `locate -c "*.jpg"` - Wyświetla ilość plików z rozszerzeniem 'jpg' w systemie

`find` - Polecenie służące do wyszukiwania plików w podanej lokalizacji
* `find hasla.kbdx` - Szuka w aktualnej lokalizacji pliku 'hasla.kbdx'
* `find /home/rafal -name DCIM.jpg` - Szuka w lokalizacji '/home/rafal' oraz wszystkich znajdujących się tam folderach pliku o nazwie 'DCIM.jpg'(parametr -name)
* `find /home/rafal -iname dCiM` - Szuka w lokalizacji '/home/rafal' oraz wszystkich znajdujących się tam folderach pliku lub folderu o nazwie 'dCiM' bez względu na wielkość liter(parametr -iname)
* `find /mnt/ -name *.mp3` - Wyświetla wszystkie pliki o rozszerzeniu 'mp3' w folderze '/mnt'

### Tekst

`tail` - Polecenie do wyświetlania ostatnich linijek pliku
* `tail ffmpeg.sh -n 3` - Wyświetla 3 ostatnie linijki z pliku 'ffmpeg.sh'

`head` - Polecenie do wyświetlania początkowych linijek pliku
* `head haldric.txt -n 15` - Wyświetla 15 początkowych linijek z pliki 'haldric.txt'

`grep` - Polecenie wyświetlające linie zawierające określone frazy/wyrażenia regularne
* `glxinfo | grep OpenGL` - Wyświetla tylko te linijki z polecenia 'glxinfo', które zawierają słowo 'OpenGL'

`sort` - Polecenie sortujące dane w pliku
* `sort plik.txt` - Sortuje plik 'plik.txt' rosnąco(domyślnie) i jego zawartość wypisuje na ekran terminala
* `sort plik.txt > posortowany.txt` - Sortuje plik 'plik.txt' malejąco(parametr -r) i rezultat zapisuje do pliku 'posortowany.txt'
* `sort -c plik.txt` - Sprawdza czy plik 'plik.txt' jest posortowany

`rg` - Wyświetla tekst pasujący do danego wyrażenia regularnego
* `rg "ERR[_V]{0,2}\("` - Wyświetla i podkreśla tekst który pasuje do wyrażenia 'ERR[_V]{0,2}\('  czyli np. 'ERR_V' lub 'ERR'

`wc` - Służy do zliczania słów oraz wystąpień danych fraz
* `wc plik.txt` - Wyświetla kolejno liczbę linii, ilość słów oraz liczbę znaków w pliku plik.txt
* `ls | wc -l` - Wyświetla ilość wyników zwróconych przez polecenie 'ls'(w tym przypadku ilość plików i katalogów)

### Użytkownicy

`su` - Polecenie do zmiany aktualnego użytkownika(w terminalu)
* `su rafal` - Zmienia aktualnego użytkownika na 'rafal'
* `su` - Zmienia aktualnego użytkownika na root. Jest to skrót polecenia 'su root'. Aby móc go używać należy nadać hasło dla użytkownika root poleceniem 'passwd'

`sudo` - Wymusza wykonanie polecenia z uprawnieniami administratora
* `sudo touch wada.txt` - Tworzy z uprawnieniami administratora plik 'wada.txt', którego inni użytkownicy nie mogą usunąć ani zmodyfikować

`useradd` - Dodawanie użytkownika. Aby móc się na niego zalogować należy nadać 
* `useradd stefan` - Dodanie użytkownika 'stefan'

`passwd` - Ma za zadanie zmienić hasło podanego użytkownika. Należy go używać z uprawnieniami administratora
* `passwd rafal` - Zmienia hasło dla użytkownika 'rafal'

`who` - Wyświetla listę zalogowanych użytkowników

`whoami` - Wyświetla aktualnie zalogowanego użytkownika

### Uprawnienia
`chmod` - Polecenie do zmiany uprawnień plików i folderów. Liczba jest trzycyfrowa oznaczająca uprawnienia dla właściela, grupy i innych użytkowników i każda z nich składa się z trzech uprawnień do r(4) - odczytu, w(2) - modyfikacji i x(1) - wykonywania danego pliku.
* `chmod 750 gitRepo -R` - Zmienia uprawnienia folderu 'gitRepo' i wszystkich plików w nim(opcja -R) dla właściciela do odczytu, modyfikacji i wykonywania pliku(7=4+2+1), dla grupy tylko do odczytu i wykownywania(5=4+1) a wszyscy inni nie mogą z niego korzystać.

`chown` - Polecenie do zmiany właściciela pliku lub folderu
* `chown rafal zdjecia -R` - Zmienia właściciela folderu 'zdjęcia' i plików w nim zawartych(parametr -R) na 'rafal'

`chgrp` - Polecenie do zmiany grupy pliku i folderu
* `chgrp root plik.txt` - Zmienia grupę pliku 'plik.txt' na 'root'

### Procesy
`top` - Wyświetla aktualne zużycie procesora CPU, RAM oraz inne informacje o działających procesach
* `top -d 1` - Zmniejsza czas aktualizacji do 1 sekundy

`kill` - "Zabija"(wyłącza) proces o określonym numerze identyfikacyjnym(PID), najprościej go sprawdzić poleceniem `top`
* `kill -9 2424` - Zabija proces o ID 2424

`killall` - "Zabija"(wyłącza) wszystkie procesy o danej nazwie
* `killall godot` - Zabija wszystkie procesy o nazwie 'godot'

### Programy i pakiety
`apt` - narzędzie do zarządzania pakietami(aplikacjami) w systemach pochodzących od Debiana takich jak Ubuntu, Linux Mint czy Zorin OS.
* `apt update` - Aktualizuje listę wersji pakietów i ich zależności, aby móc sprawdzić możliwość aktualizacji systemu.
* `apt upgrade -y` - Aktualizuje wszystkie aplikacje. Parametr -y skutkuje automatycznym rozpoczęciem pobrania aktualizacji i jej instalacji po wyświetleniu listy
* `apt list` - Wyświetla listę wszystkich dostępnych pakietów
  * `apt list | grep blender` - Wyświetla wszystkie dostępne pakiety mające w nazwie 'blender'
* `apt list --upgradable` - Wyświetla listę wszystkich pakietów, których nowsza wersja jest dostępna w repozytorium
* `apt install` - Służy do instalacji oprogramowania
  * `apt install -y blender` - Instaluje program 'blender' z repozytorium
* `apt show` - Wyświetla informacje o podanym pakiecie

`add-apt-repository` - Polecenie służące do dodania PPA, umożliwiającego pobranie z niego konkretnych programów. Ich listę można znaleźć na stronie https://launchpad.net/. Należy po tym poleceniu wykonać `apt update` aby zaktualizować listę dostępnego oprogramowania.
* `add-apt-repository ppa:christian-boxdoerfer/fsearch-daily` - Dodaje informacje do systemu o PPA zawierającym program 'fsearch', który można później zainstalować

`dpkg` - Polecenie służące do zarządzania plikami .deb
* `dpkg -i plik.deb` - Instaluje w systemie paczkę 'plik.deb'

### Symbole
`&` - Odpina program od okna konsoli, dzięki czemu można wyłączyć konsolę bez konieczności wyłączenia programu
* `firefox &` - Otwiera program 'firefox' i odpina go od konsoli, którą w każdym momencie można wyłączyć

`>>` - Przekierowuje i dopisuje zawartość standardowego strumienia do podanego pliku
* `ls >> /home/rafal/listaPlikow.txt` - Dopisuje do pliku '/home/rafal/listaPlikow.txt' wynik polecenia 'ls'

`>` - Przekierowuje zawartość standardowego strumienia do podanego pliku, którego zawartość najpierw kasuje
* `ls > /home/ubu/plik.txt` - Usuwa zawartość pliku '/home/ubu/plik.txt' i wpisuje do niego wynik polecenia 'ls'

`|` - Służy do przekazania danych do podprogramu, który będzie na nich operował
* `ls | grep P` - Lista programów zebrana poprzez polecenie 'ls', jest filtrowana przez 'grep' i pokazywane są jedynie
foldery zawierające w nazwie 'P'

`;` - Średnik oddziela niezależne od siebie zadania, dzięki czemu nie trzeba wpisywać poleceń w kilku liniach
* `cd ..;ls` - Przechodzi katalog wyżej, bez względu czy udało się czy nie, wypisuje listę plików i folderów

`&&` - Służy do łączenia komend. Jeśli znajdująca się po lewej stronie znaku `&&` instrukcja nie zostanie poprawnie wykonana, to ta po prawej stronie znaku nie wywoła się.
* `apt update && apt upgrade -y` - Aktualizujemy listy pakietów a jeśli się to uda to aktualizujemy system

`~` - Tylda oznacza folder domowy użytkownika
* `cd ~/` - Przechodzi do folderu domowego użytkownika, `~` jest skrótem lokalizacji '/home/nazwaUzytkownika'

### Archiwa
`tar` - Polecenie służące do archiwizacji plików i folderów
* `tar -czvf archiwum.tar.gz /home/lilia/zdjecia.jpg /mnt/pliki` - Pakuje plik '/home/lilia/zdjecia.jpg' oraz katalog '/mnt/pliki' wraz z zawartością do pliku 'archiwum.tar.gz'
* `tar -czvf szczoteczka.tar.gz /home/ubuntu --exclude=/home/ubuntu/Pobrane` - Pakuje katalog '/home/ubuntu' wraz z zawartością do pliku 'szczoteczka.tar.gz', lecz pomija katalog '/home/ubuntu/Pobrane'
* `tar -xzvf zdjecia.tar.gz -C /home/roman/arch` - Wypakowuje zawartość pliku 'zdjecia.tar.gz' do katalogu '/home/roman/arch'

`zip` - Polecenie do archiwizacji plików w formacie ZIP
* `zip -r archiwum.zip folder hasla.txt` - Tworzy 'archiwum.zip' w formacie ZIP i wrzuca do środka katalog 'folder' oraz plik 'hasla.txt'

`unzip` - Polecenie do wypakowania spakowanego pliku ZIP
* `unzip archiwum.zip -d /home/rafal/Pulpit` - Wypakowuje plik 'archiwum.zip' do folderu '/home/rafal/Pulpit'

### Informacje o systemie
`lsblk` - Wyświetla listę dysków, partycji oraz zamontowanych woluminów
* `lsblk -e7` - Wyświetla tylko listę fizycznych dysków i partycji bez paczek SNAP

`uname` - Wyświetla podstawowe informacje o systemie
* `uname -a` - Wypisuje kernel, jego wersję, system, czas instalacji oraz zestaw instrukcji procesora

`ifconfig` - Wyświetla informacje o sieci tj. adres IP, maska sieciowa czy adres MAC 

`glxinfo` - Wyświetla szereg informacji o karcie graficznej i jej sterownikach
* `glxinfo | grep OpenGL` - Wyświetla podstawowe informacje o karcie graficznej

### Inne
`history` - Polecenie wyświetlające listę ostatnich komend wpisanych w konsolę. W prosty sposób można wyszukiwać ostatnie polecenia za pomocą skrótu klawiszowego CTRL + R.

`shutdown` - Polecenie używane do wyłączenia systemu
* `shutdown now` - Natychmiastowo wyłącza system.
* `shutdown 8:00` - Wyłącza system o godzinie 8:00.
* `shutdown +15 "Wyłączanie komputera"` - System wyłączy się za '15' minut i wyświetli wiadomość 'Wyłączania komputera'

`reboot` - Wykonuje restart systemu.

`uptime` - Wyświetla czas od ostatniego włączenia systemu i oraz liczbę zalogowanych użytkowników do systemu.

`alias` - Tworzy alias(przezwisko) dla danego polecenia/zbioru poleceń
* `alias infoGPU='glxinfo | grep OpenGL'` - Tworzymy alias o nazwie 'infoGPU' mający za zadanie wypisać podstawowe informacje o GPU, który możemy odtąd używać zamiast polecenia 'glxinfo | grep OpenGL'

`unalias` - Usuwa wcześniej stworzony alias
* `unalias infoGPU` - Usuwa alias o nazwie 'infoGPU'

`man` - pokazuje instrukcję dla danego polecenia
* `man apt` - Wyświetla instrukcję polecenia 'apt' 

`exit` - Zamyka kartę lub terminal.

## Słowniczek
* **Kompilacja** - proces zamiany kodu źródłowego stworzonego w dowolnym języku programowania na język maszynowy.
* **Pakiet** - to skompilowany i skompresowany kod źródłowy(najczęściej programów lub bibliotek), używany przez różne dystrybucje w formie plików DEB, RPM.
* **Repozytorium** - Miejsce, gdzie znajdują się różne programy.
* **Wyrażenie regularne** - Wzorzec, dla którego program dopasowuje tekst, np. dla wyrażenia 'człowiek[i]{0,1}' oznacza, że można do niego przyporządkować tekst 'człowiek jak i `człowieki`
