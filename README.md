# Podstawowe polecenia stosowane w systemie GNU/Linux

To repozytorium zawiera informację o podstawowych komendach używanych w systemie GNU/Linux wraz z krótkimi przykładami.

## Spis treści
1. [Czym jest GNU/Linux, terminal i po co go używać](#czym-jest-gnulinux-terminal-i-po-co-go-używać)
2. [Podstawowe polecenia](#podstawowe-polecenia)  
2.1 [Katalogi i Pliki](#katalogi-i-pliki)  
2.2 [Tekst](#tekst)  
2.3 [Użytkownicy](#użytkownicy)  
2.4 [Uprawnienia](#uprawnienia)  
2.5 [Procesy](#procesy)  
2.6 [Programy i pakiety](#programy-i-pakiety)  
2.7 [Symbole](#symbole)  
2.8 [Archiwa](#archiwa)  
2.9 [Informacje o systemie](#informacje-o-systemie)  
2.10 [Inne](#inne)  
3. [Słowniczek](#słowniczek)

## Czym jest GNU/Linux, terminal i po co go używać
GNU/Linux jest to system operacyjny, posiadający kernel Linux stworzony przez Linusa Torvaldsa i używający wolnego oprogramowania GNU.

Podstawowym programem używanym w tym systemie jest terminal(w zasadzie emulator terminala) znany również pod swoją angielską nazwą 'shell'.
Umożliwia wpisywanie poleceń w formie tekstowej dlatego zaliczany jest do programów CLI(Command Line Interface), co jest przeciwieństwem dla graficznego interfejsu użytkownika GUI(Graphical User Interface).

Często jest on używany przez nieco bardziej zaawansowanych użytkowników, którzy w ten sposób automatyzują masę rzeczy i oszczędzają czas.

W codziennym użytku może pomóc rozwiązać większość problemów, które można napotkać, gdy coś się zepsuje w systemie oraz wykonać niektóre operacje dużo szybciej niż poprzez graficzny interfejs.

Trzeba przed rozpoczęciem nauki zapamiętać, że Linux, w przeciwieństwie do Windowsa, rozróżnia wielkość liter w nazwach plików oraz poleceń.

Dodatkowo trzeba pamiętać, że nie ma w Linuxie liter dysków, a wszystkie foldery są podfolderem głównego katalogu '/'.
Istnieje kilka ważniejszych katalogów, które czasami mogą być używane np.:
* /home - Zawiera foldery domowe użytkowników
* /media - Montowane są tutaj dyski przenośne, pendrive itp.
* /mnt - Montowane są tutaj partycje dysków HDD oraz SSD
Reszta folderów nie powinna być używana przez początkujących użytkowników

Część podstawowych pojęć oraz proces instalacji GNU/Linuxa jest wyjaśniony w repozytorium - https://github.com/qarmin/GNU-Linux-Podstawy/blob/master/README.md#informacje-o-repozytorium.

W przypadku błędów o braku dostępu, instrukcję należy poprzedzić poleceniem `sudo` nadającym najwyższe prawa administratora, jednak należy używać tego z rozwagą.

Nazwy oznaczone w opisie pojedynczym cudzysłowem(np. 'plik.txt') można dowolnie modyfikować w poleceniu w zależności od oczekiwanego rezultatu.

## Podstawowe polecenia
### Katalogi i pliki

`pwd` - Wyświetla ścieżkę w której aktualnie się znajdujemy

![SCR](https://user-images.githubusercontent.com/41945903/65830756-c180a380-e2b2-11e9-9f87-dfd43d16ba8e.png)

`cd` - Polecenie do zmiany aktualnego katalogu
* `cd ..` - Przechodzi jeden katalog do góry
* `cd roman/zawory` - Przechodzi do katalogu 'zawory' znajdującego się wewnątrz innego folderu 'roman'

`ls` - Polecenie służące do wyświetlenia listy plików i folderów w danym katalogu
* `ls -A` - Wyświetla wszystkie(również ukryte) pliki i foldery

![SCR](https://user-images.githubusercontent.com/41945903/65830767-d3624680-e2b2-11e9-8737-507cdf35f1aa.png)

* `ls -l` - Wyświetla informacje o właścicielach plików/folderów, uprawnienia do nich, rozmiar i czas utworzenia

![SCR](https://user-images.githubusercontent.com/41945903/65830763-ccd3cf00-e2b2-11e9-8db0-6a6680a1de2c.png)

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


![SCR](https://user-images.githubusercontent.com/41945903/65830774-de1cdb80-e2b2-11e9-83fa-6b4553665f79.png)

`cat` - Polecenie do wypisywania zawartości pliku na ekran oraz łączenia kilku plików w jeden
* `cat plik.txt` - Wyświetla zawartość pliku 'plik.txt' w konsoli

![SCR](https://user-images.githubusercontent.com/41945903/65830709-41f2d480-e2b2-11e9-91e5-7f4bcf120397.png)

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

![SCR](https://user-images.githubusercontent.com/41945903/65830701-1bcd3480-e2b2-11e9-94ec-f1419952d506.png)

* `locate -c "*.jpg"` - Wyświetla ilość plików z rozszerzeniem 'jpg' w systemie

![SCR](https://user-images.githubusercontent.com/41945903/65830693-0e17af00-e2b2-11e9-966a-a259706a3a4c.png)

`find` - Polecenie służące do wyszukiwania plików w podanej lokalizacji
* `find hasla.kbdx` - Szuka w aktualnej lokalizacji pliku 'hasla.kbdx'
* `find /home/rafal -name DCIM.jpg` - Szuka w lokalizacji '/home/rafal' oraz wszystkich znajdujących się tam folderach pliku o nazwie 'DCIM.jpg'(parametr -name)
* `find /home/rafal -iname dCiM` - Szuka w lokalizacji '/home/rafal' oraz wszystkich znajdujących się tam folderach pliku lub folderu o nazwie 'dCiM' bez względu na wielkość liter(parametr -iname)
* `find /mnt/ -name *.mp3` - Wyświetla wszystkie pliki o rozszerzeniu 'mp3' w folderze '/mnt'

![SCR](https://user-images.githubusercontent.com/41945903/65830677-e4f71e80-e2b1-11e9-8fa4-4fa81141e1b4.png)

### Tekst

`tail` - Polecenie do wyświetlania ostatnich linijek pliku
* `tail ffmpeg.sh -n 3` - Wyświetla 3 ostatnie linijki z pliku 'ffmpeg.sh'

![SCR](https://user-images.githubusercontent.com/41945903/65830675-e3c5f180-e2b1-11e9-8182-63298ff68f19.png)

`head` - Polecenie do wyświetlania początkowych linijek pliku
* `head haldric.txt -n 15` - Wyświetla 15 początkowych linijek z pliki 'haldric.txt'

`grep` - Polecenie wyświetlające linie zawierające określone frazy/wyrażenia regularne
* `ls | grep arch` - Wyświetla tylko te linijki z polecenia 'ls', które zawierają słowo 'arch'

![SCR](https://user-images.githubusercontent.com/41945903/65830577-fa1f7d80-e2b0-11e9-90ab-eada5d92048d.png)

`sort` - Polecenie sortujące dane w pliku
* `sort plik.txt` - Sortuje plik 'plik.txt' rosnąco(domyślnie) i jego zawartość wypisuje na ekran terminala

![SCR](https://user-images.githubusercontent.com/41945903/65830557-dbb98200-e2b0-11e9-8bbd-791331952aca.png)

* `sort plik.txt > posortowany.txt` - Sortuje plik 'plik.txt' malejąco(parametr -r) i rezultat zapisuje do pliku 'posortowany.txt'
* `sort -c plik.txt` - Sprawdza czy plik 'plik.txt' jest posortowany

![SCR](https://user-images.githubusercontent.com/41945903/65830546-ca707580-e2b0-11e9-835a-c6e9290ef3bc.png)

`rg` - Polecenie wyświetlające tekst pasujący do danego wyrażenia regularnego
* `rg "ERR[_V]{0,2}\("` - Wyświetla i podkreśla tekst który pasuje do wyrażenia 'ERR[_V]{0,2}\(' czyli np. 'ERR_V' lub 'ERR'

![SCR](https://user-images.githubusercontent.com/41945903/65830543-c9d7df00-e2b0-11e9-9d86-7d046a013a03.png)

`wc` - Polecenie służące do zliczania słów oraz wystąpień danych fraz
* `wc plik.txt` - Wyświetla kolejno liczbę linii, ilość słów oraz liczbę znaków w pliku plik.txt

![SCR](https://user-images.githubusercontent.com/41945903/65830528-a90f8980-e2b0-11e9-8f36-0d220e7c9551.png)

* `ls | wc -l` - Wyświetla ilość wyników zwróconych przez polecenie 'ls'(w tym przypadku ilość plików i katalogów)

![SCR](https://user-images.githubusercontent.com/41945903/65830527-a876f300-e2b0-11e9-9529-d8881fcd399d.png)

### Użytkownicy

`su` - Polecenie do zmiany aktualnego użytkownika(tylko w terminalu)
* `su rafal` - Zmienia aktualnego użytkownika na 'rafal'
* `su` - Zmienia aktualnego użytkownika na root. Jest to skrót polecenia 'su root'. Aby móc go używać należy nadać hasło dla tego użytkownika poleceniem 'passwd'

![SCR](https://user-images.githubusercontent.com/41945903/65830522-985f1380-e2b0-11e9-8176-cc497d4e9c1b.png)

`sudo` - Polecenie wymuszające wykonanie podanego po nim polecenia z uprawnieniami administratora
* `sudo touch wada.txt` - Tworzy z uprawnieniami administratora plik 'wada.txt', którego inni użytkownicy nie mogą usunąć ani zmodyfikować

![SCR](https://user-images.githubusercontent.com/41945903/65830674-e32d5b00-e2b1-11e9-9733-eb56da608142.png)

`useradd` - Polecenie do dodawania użytkownika. Aby móc się na dane konto zalogować, należy nadać mu hasło poleceniem `passwd`
* `useradd stefan` - Dodanie użytkownika 'stefan'

`passwd` - Polecenie umożliwiające zmianę hasła danego użytkownika
* `passwd rafal` - Zmienia/Nadaje hasło dla użytkownika 'rafal'

`who` - Polecenie wyświetlające listę zalogowanych użytkowników

![SCR](https://user-images.githubusercontent.com/41945903/65830513-7796be00-e2b0-11e9-8ba6-e9c67bb27f63.png)

`whoami` - Polecenie wyświetla nazwę aktualnie zalogowanego użytkownika

![SCR](https://user-images.githubusercontent.com/41945903/65830512-76fe2780-e2b0-11e9-9423-9e861ff33333.png)

### Uprawnienia
`chmod` - Polecenie do zmiany uprawnień plików i folderów. Liczba je określająca jest trzycyfrowa oznaczająca kolejno uprawnienia dla właściciela, grupy i innych użytkowników i każda z nich składa się z trzech uprawnień do r(4) - odczytu, w(2) - modyfikacji i x(1) - wykonywania danego pliku. Każda z liczb określającej uprawnienia może przyjmować maksymalną wartość 7 a minimalną 0, która to jest sumą poszczególnych uprawnień.
* `chmod 750 gitRepo -R` - Zmienia uprawnienia folderu 'gitRepo' i wszystkich plików w nim(opcja -R) dla właściciela do odczytu, modyfikacji i wykonywania pliku(7=4+2+1), dla grupy tylko do odczytu i wykownywania(5=4+1) a wszyscy inni nie mogą z niego korzystać

`chown` - Polecenie do zmiany właściciela pliku lub folderu
* `chown rafal zdjecia -R` - Zmienia właściciela folderu 'zdjęcia' i wszystkich plików oraz katalogów w nim zawartych(parametr -R) na 'rafal'

`chgrp` - Polecenie do zmiany grupy pliku i folderu
* `chgrp root plik.txt` - Zmienia grupę pliku 'plik.txt' na 'root'

### Procesy
`top` - Polecenie wyświetla aktualne zużycie procesora CPU, RAM oraz inne informacje o aktualnie uruchomionych procesach
* `top -d 1` - Zmniejsza czas aktualizacji wykresów do 1 sekundy(parametr -d)

![SCR](https://user-images.githubusercontent.com/41945903/65832164-b3d21a80-e2c0-11e9-8014-433575414905.png)

`kill` - Polecenie umożliwiające wysłanie sygnału do procesu o danym id, które można sprawdzić poleceniem 'top'
* `kill -9 2424` - Powoduje zakończenie pracy(parametr -9) procesu o PID '2424'

`killall` - Polecenie umożliwiające wysłanie sygnału do procesu o podanej nazwie
* `killall godot` - Powoduje zakończenie pracy(domyślny tryb) wszystkich procesów o nazwie 'godot'

### Programy i pakiety
`apt` - Polecenie do zarządzania pakietami w systemach pochodzących od Debiana takich jak Ubuntu, Linux Mint czy Zorin OS
* `apt update` - Aktualizuje listę wersji pakietów i ich zależności oraz podaje ilość pakietów możliwych do aktualizacji

![SCR](https://user-images.githubusercontent.com/41945903/65830430-9ea0c000-e2af-11e9-92e5-5727bc15dc34.png)

* `apt upgrade -y` - Aktualizuje wszystkie pakiety. Parametr -y skutkuje automatycznym rozpoczęciem pobrania i instalacji aktualizacji po wyświetleniu listy programów posiadających nowsze wersje

![SCR](https://user-images.githubusercontent.com/41945903/65830436-ac564580-e2af-11e9-9d3a-c6497f5281bc.png)

* `apt list` - Wyświetla listę wszystkich dostępnych pakietów
  * `apt list --installed` - Wyświetla tylko zainstalowane pakiety

![SCR](https://user-images.githubusercontent.com/41945903/65830300-81b7bd00-e2ae-11e9-83ab-d79260f152cb.png)

  * `apt list | grep blender` - Wyświetla wszystkie dostępne pakiety mające w nazwie 'blender'

  ![SCR](https://user-images.githubusercontent.com/41945903/65830298-80869000-e2ae-11e9-9f79-f68c4e9c56b6.png)

  * `apt list --upgradable` - Pokazuje listę wszystkich pakietów, których nowsza wersja jest dostępna w repozytorium

![SCR](https://user-images.githubusercontent.com/41945903/65830231-dc044e00-e2ad-11e9-8413-cdc0c2bce298.png)

* `apt install` - Służy do instalacji oprogramowania
  * `apt install blender` - Instaluje pakiet 'blender' wraz z zależnościami z repozytorium
  
![SCR](https://user-images.githubusercontent.com/41945903/65830228-da3a8a80-e2ad-11e9-9633-199bda65b6be.png)

* `apt purge blender` - Usuwa pakiet 'blender' wraz z zależnościami, jeśli nie są używane przez inne programy

![SCR](https://user-images.githubusercontent.com/41945903/65830229-dad32100-e2ad-11e9-9600-b53df1c49ede.png)

* `apt show` - Wyświetla informacje o podanym pakiecie
  * `apt show krita` - Pokazuje informacje o pakiecie 'krita'

![SCR](https://user-images.githubusercontent.com/41945903/65830227-d9095d80-e2ad-11e9-91a0-58849ac0f035.png)
  
`add-apt-repository` - Polecenie służące do dodania PPA, umożliwiającego pobranie z niego konkretnych programów. Ich listę można znaleźć na stronie https://launchpad.net/. Należy po tym poleceniu wykonać `apt update` aby zaktualizować listę dostępnego oprogramowania
* `add-apt-repository ppa:christian-boxdoerfer/fsearch-daily` - Dodaje informacje do systemu o PPA zawierającym program 'fsearch', który można później zainstalować poleceniem `apt install fsearch-trunk`

![SCR](https://user-images.githubusercontent.com/41945903/65830224-d870c700-e2ad-11e9-9c76-6e3935f3dbd0.png)

`dpkg` - Polecenie służące do zarządzania plikami .deb
* `dpkg -i plik.deb` - Instaluje w systemie paczkę 'plik.deb'

![SCR](https://user-images.githubusercontent.com/41945903/65830222-d444a980-e2ad-11e9-8a33-a804d9c23588.png)

### Symbole
`&` - Odpina program od okna konsoli, dzięki czemu można ją wyłączyć bez konieczności wyłączenia również programu
* `firefox &` - Otwiera program 'firefox' i odpina go od konsoli, którą można w każdym momencie wyłączyć

`>>` - Przekierowuje i dopisuje zawartość standardowego strumienia do podanego pliku
* `ls >> /home/rafal/listaPlikow.txt` - Dopisuje do pliku '/home/rafal/listaPlikow.txt' wynik polecenia 'ls'

`>` - Przekierowuje zawartość standardowego strumienia do podanego pliku, którego zawartość najpierw kasuje
* `ls > /home/ubu/plik.txt` - Usuwa zawartość pliku '/home/ubu/plik.txt' i wpisuje do niego wynik polecenia 'ls'

![SCR](https://user-images.githubusercontent.com/41945903/65829115-0ea84980-e2a2-11e9-8607-0d886a182567.png)

`|` - Służy do przekazania danych do podprogramu, który będzie na nich operował
* `ls | grep i` - Lista programów zebrana poprzez polecenie 'ls', jest filtrowana przez 'grep' i pokazywane są jedynie
foldery zawierające w nazwie 'i'

![SCR](https://user-images.githubusercontent.com/41945903/65829114-0d771c80-e2a2-11e9-9233-f3d4ff5f1150.png)

`;` - Średnik oddziela niezależne od siebie zadania, dzięki czemu można zapisać ich kilka w linii
* `cd ..;ls` - Przechodzi katalog wyżej, bez względu czy udało się czy nie, wypisuje listę plików i folderów

![SCR](https://user-images.githubusercontent.com/41945903/65829113-0c45ef80-e2a2-11e9-8f03-b1366c25fedf.png)

`&&` - Służy do łączenia komend. Jeśli znajdująca się po lewej stronie znaku `&&` instrukcja nie zostanie poprawnie wykonana, to ta po prawej stronie znaku nie wywoła się
* `sudo apt update && sudo apt upgrade -y` - Aktualizujemy listy pakietów a jeśli się to uda to aktualizujemy system

`~` - Tylda oznacza folder domowy użytkownika
* `cd ~/Pulpit` - Przechodzi do Pulpitu domyślnego użytkownika, `~` jest skrótem lokalizacji '/home/nazwaUzytkownika' zatem aktualnym folderem będzie np. '/home/alfred/Pulpit'

![SCR](https://user-images.githubusercontent.com/41945903/65829112-0a7c2c00-e2a2-11e9-88ed-48400e9a3fcf.png)

* `""` - W cudzysłowach można zawrzeć nazwę, która np. zawiera spację i jej użycie zostałoby błędnie odczytane jako 2 lub więcej argumentów
  * `cd "zdjecia 2018"` - Przechodzi do folderu 'zdjecia 2018', użycie polecenia `cd zdjecia 2018` wypisałoby błąd o zbyt dużej ilości argumentów

![SCR](https://user-images.githubusercontent.com/41945903/65831125-605acf00-e2b6-11e9-9d98-de22168c2dd6.png)

### Archiwa
`tar` - Polecenie służące do archiwizacji plików i folderów
* `tar -czvf archiwum.tar.gz /home/lilia/zdjecia.jpg /mnt/pliki` - Pakuje plik '/home/lilia/zdjecia.jpg' oraz katalog '/mnt/pliki' wraz z zawartością do pliku 'archiwum.tar.gz'
* `tar -czvf szczoteczka.tar.gz /home/ubuntu --exclude=/home/ubuntu/Pobrane` - Pakuje katalog '/home/ubuntu' wraz z zawartością do pliku 'szczoteczka.tar.gz', lecz pomija katalog '/home/ubuntu/Pobrane'(parametr --exclude)

![SCR](https://user-images.githubusercontent.com/41945903/65829072-ba04ce80-e2a1-11e9-912a-93ff19e41d4b.png)
* `tar -xzvf zdjecia.tar.gz -C /home/roman/arch` - Wypakowuje zawartość pliku 'zdjecia.tar.gz' do katalogu '/home/roman/arch'(folder musi istnieć)

![SCR](https://user-images.githubusercontent.com/41945903/65829073-bb35fb80-e2a1-11e9-905c-8f8d0fa7f099.png)

`zip` - Polecenie do archiwizacji plików w formacie ZIP
* `zip -r archiwum.zip folder hasla.txt` - Tworzy 'archiwum.zip' w formacie ZIP i wrzuca do środka katalog 'folder' oraz plik 'hasla.txt'

`unzip` - Polecenie do wypakowania spakowanego pliku ZIP
* `unzip archiwum.zip -d /home/rafal/Pulpit` - Wypakowuje plik 'archiwum.zip' do folderu '/home/rafal/Pulpit'

### Informacje o systemie
`lsblk` - Polecenie do wyświetlenia listę dysków, partycji oraz zamontowanych woluminów
* `lsblk -e7` - Wyświetla tylko listę dysków i partycji bez paczek SNAP

![SCR](https://user-images.githubusercontent.com/41945903/65829071-b96c3800-e2a1-11e9-8bd0-de27a32ce56d.png)

`uname` - Polecenie które wyświetla podstawowe informacje o systemie
* `uname -a` - Wypisuje kernel, jego wersję, system, czas instalacji oraz zestaw instrukcji procesora

![SCR](https://user-images.githubusercontent.com/41945903/65829070-b8d3a180-e2a1-11e9-8d54-54c99066ff0f.png)

`ifconfig` - Polecenie używane do wypisywania informacji o sieci tj. adres IP, maska sieciowa czy adres MAC

![SCR](https://user-images.githubusercontent.com/41945903/65829063-a8bbc200-e2a1-11e9-9397-590468216307.png)

`glxinfo` - Polecenie do wyświetlenia szeregu informacji o karcie graficznej i jej sterownikach
* `glxinfo | grep OpenGL` - Wyświetla podstawowe informacje o karcie graficznej

![SCR](https://user-images.githubusercontent.com/41945903/65829062-a8232b80-e2a1-11e9-93c2-a2ac0949c4b6.png)

`lspci` - Polecenie do wyświetlania podstawowych informacji o komponentach komputera

![SCR](https://user-images.githubusercontent.com/41945903/65831527-df520680-e2ba-11e9-8977-15a9a60acbe8.png)

### Inne
`history` - Polecenie wyświetlające listę ostatnich komend wpisanych do konsoli. W prosty sposób można wyszukiwać ostatnie polecenia za pomocą skrótu klawiszowego CTRL + R

![SCR](https://user-images.githubusercontent.com/41945903/65829061-a6f1fe80-e2a1-11e9-8f75-bd031ccebe3f.png)

`shutdown` - Polecenie używane do wyłączenia systemu
* `shutdown now` - Natychmiastowo wyłącza system
* `shutdown 8:00` - Wyłącza system o godzinie 8:00
* `shutdown +15 "Wyłączanie komputera"` - System wyłączy się za '15' minut i wyświetli wiadomość 'Wyłączania komputera'

`reboot` - Polecenie do restartowania systemu

`uptime` - Polecenie do wyświetlania czasu od ostatniego włączenia systemu oraz liczbę zalogowanych użytkowników do systemu

![SCR](https://user-images.githubusercontent.com/41945903/65829057-a0638700-e2a1-11e9-875d-2714cd7db6b6.png)

`alias` - Polecenia do tworzenia aliasów(przezwisk) dla danego polecenia/zbioru poleceń
* `alias infoGPU='glxinfo | grep OpenGL'` - Tworzy alias o nazwie 'infoGPU' mający za zadanie wypisać podstawowe informacje o GPU, który można odtąd używać zamiast polecenia 'glxinfo | grep OpenGL'

![SCR](https://user-images.githubusercontent.com/41945903/65829051-92ae0180-e2a1-11e9-9eae-b5ab7f599c26.png)

`unalias` - Polecenie do usuwania stworzonego wcześniej aliasu
* `unalias infoGPU` - Usuwa alias o nazwie 'infoGPU'

`clear` - Polecenie do czyszczenia konsoli

`man` - Polecenie pokazujące instrukcję dla danego polecenia
* `man apt` - Wyświetla instrukcję polecenia 'apt'

![SCR](https://user-images.githubusercontent.com/41945903/65829045-83c74f00-e2a1-11e9-8ed0-98b608860952.png)

`exit` - Polecenie które zamyka kartę lub terminal

![SCR](https://user-images.githubusercontent.com/41945903/65829016-5084c000-e2a1-11e9-9222-2b9f967bc59b.png)

## Słowniczek
* **Kompilacja** - Proces zamiany kodu źródłowego stworzonego w dowolnym języku programowania na język maszynowy.
* **Pakiet** - To skompilowany i skompresowany kod źródłowy(najczęściej programów lub bibliotek), używany przez różne dystrybucje w formie plików DEB, RPM.
* **Repozytorium** - Miejsce, gdzie znajdują się różne programy.
* **Wyrażenie regularne** - Wzorzec, dla którego program dopasowuje tekst, np. dla wyrażenia 'człowiek[i]{0,1}' można przyporządkować teksty takie jak 'człowiek' czy 'człowieki'.
