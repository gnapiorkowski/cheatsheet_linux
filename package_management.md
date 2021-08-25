# Debian Based (Ubuntu/Xubuntu/Lubuntu/Debian/...) (Laptop Dell latitude e6330)

## Aktualizacja systemu (raz na tydzień dwa wypadałoby robić)

```bash
sudo apt update && sudo apt upgrade
```
update aktualizuje bazę danych z aplikacjami

upgrade aktualizuje aplikacje na podstawie w.w. bazy danych.

## Szukanie aplikacji

```bash
apt search <nazwa_aplikacji>
```

## Instalowanie aplikacji

```bash
sudo apt install <nazwa_aplilacji>
```

## Odinsyalowanie aplikacji

```bash
sudo apt remove <nazwa_aplikacji>
```
pozostawia pliki konfiguracyjne - przydatne, jak chcesz kiedyś ponownie zainstalować tą aplikację

```bash
apt purge <nazwa_aplikacji>
```

usuwa razem z plikami konfiguracyjnymi - używać zawsze, jak nie masz w planach ponownie instalować tej aplikacji (oszczędza zaśmiecania systemu)

# Arch Based (Arch/Arco Linux/ Manjaro/...) (Laptop lenovo ThinkPad)

## Aktualizacja systemu (raz na tydzień dwa wypadałoby robić)

```bash
sudo pacman -Syu
```

S oznacza operację instalacji
y oznacza updare
u oznacza upgrade
nigdy NIE używać osobno np ``` sudo pacman -Sy ``` na systemach typu Arch

## Szukanie aplikacji

```bash
pacman -Ss <nazwa_aplikacji>
```


## Instalowanie aplikacji

```bash
sudo pacman -S <nazwa_aplikacji>
```

## Odinsyalowanie aplikacji

```bash
sudo pacman -Rns <nazwa_aplikacji>
```

usuwa razem z plikami konfiguracyjnymi - używać zawsze, pozostawianie och rzadko kiedy miałoby sens, a przy ponownej instalacji one i tak się tworzą automatycznie.


## Szukanie w liście zainstalowanych aplikacji

```bash
pacman -Qs <nazwa_aplikacji>
```

## Pacman nazwa_aplikacji

Pacman przy nazwach aplikacji dodaje opisy. Dzięki temu możemy wyszukiwać także po nich.

Np.

```bash
pacman -Ss firefox
```

znajdzie nam wszystkie aplikacje możliwe do zainstalowania, które są firefoxem, dodatkiem do firefoxa, mają w opisie cos o firefoxie itp

```bash
pacman -Ss web browser
```

wyszuka wszystkie aplikacje, które mają w opisie słowa "internet" i "browser". Między innymi na liście wyników powinien być Firefox.

Można tego używać także do przeglądania aplikacji już zainstalowanych:

```bash
pacman -Qs web browser
```

W teorii powinno znaleźć Firefox, Chromium, Chrome, Brave o ile mamy je zainstalowane.

## AUR

pacman, to narzędzie analogiczne do apptitude.
Jest podstawowym package managerem w systemach Arch based.
Jednak mamy jeszcze AUR (Arch User Repo.) - Repozytoria Użytkowników Arch,
w których są aplikacje wrzucane przez użytkowników.
Dostajemy się tam używając *yay* jak poniżej.
***Bardzo przydatne, ponieważ znacznie ułatwia instalowanie
mniej popularnych aplikacji.*** Aczkolwien należy zachować szczególną
ostrożnasc ponieważ te paczki nie przechodzą prkawie żadnej
weryfikacji. ***Nigdy nie instalować paczek oznaczonych
OUT OF DATE*** Jeżeli są tak zonaczone, to prawie zawsze
dlatego, że są zepsute i nie zostały zaaktualowane
przez autora w celu naprawienie ich.

```bash
yay <nazwa_aplilacji>
```

Wyświetli nam ponumerowaną listę aplikacji i ich opisów,
w których nazwach znaleziono <nazwa_aplikacji>.
Należy wybrać jedną (wpisać numer z klawiatury)
i zatwierdzić Enterem. Można wybrać kilka np 1 2 3,
albo tak samo kilka 1-3. Przy wyborze kilku zostaną po prostu zainstalowane wszystkie.

# Wskazówki

Jezeli chcemy zainstalować jakąś konkretna aplikację,
której nazwę z znamy, to nalepiej zaczac od wyszukania jej
używając package managera.

Na przykładzie Firefox:

* Debian based
```bash
apt search firefox
```

lub

* Arch based

```bash
pacman -Ss firefox
```

Jeżeli znaleźliśmy na liście wyników interesującą nas aplikację,
to możemy śmiało zainstalować zgodnie z instrukcjami wyżej, czyli:

* Debian based
```bash
apt install firefox
```

lub

* Arch based

```bash
pacman -S firefox
```

Jeżeli nie znaleźliśmy danej aplikacji, to zachęcam do
skorzystania z [duckduckgo.com](https://www.duckduckgo.com/)
i wyszukania "Ubuntu install firefox" albo "arch linix install forefox"

* [Arch - pierwszy wynik to ArchWiki](https://wiki.archlinux.org/index.php/Firefox)
    Mamy tam ślicznie wszystko opisane w sekcji "Installing",
    a w szczególności podaną nazwę paczki, czyli "firefox".

    [ArchWiki](https://wiki.archlinux.org/) to wspaniałe kompedium wiedzy.
    Większość problemów jest tam opisana, także zachęcam do korzystania.

* [Ubuntu - pierwszy wynik](https://vitux.com/4-ways-to-install-mozilla-firefox-in-ubuntu/)
   Autor sugeruje użycie Snap, jednak nie polecam tego rozwiązania.
   Więcej na temat Snap w sekcji Flatpak/Snap. Jednak niżej widzimy
   opis instalacji z oficjalnych repozytoriów ubuntu, a w szczególności
   <nazwa_aplikacji>, czyli "firefox" zapamiętujemy ją i podążamy dalej
   zgodnie z instrukcjami instalacji opisanymi tu wcześniej. 

Dostaniemy dotrzemy na jakąś stronę, gdzie ktoś opisał
proces instalacji tej apkikacji. Interesuje nas raczej tylko
<nazwa_aplickaji> dla naszego systemu np "firefox".

Nazwy aplikacji (paczek) różnią się czasami pomiędzy systemami,
dlatego wyszukując zalecane jest dodanie nazwy systemu bazowego
tj. Arch, lub "Ubuntu" - nie Debian, ponieważ Ubuntu bazuje na Debianie,
ale Debian jest dużo mniej popularny i szanse na znalezienie czegoś
są mniejsze.



Mając ta nazwę instalujemy zgodnie z instrukcjami wyżej.

# Flatpak/Snap

Flatpak i Snap to alternatywne managery paczek w systemie (aplikacji).
Różnica jest taka, że Snap jest zamknięty i Canonical (firma od Ubuntu)
ma nad nim pełną kontrolę - nie jest to zdrowe, dlatego preferujemy Flatpak.

Flatpak i Snap różnią się głównie tym od domyślnych systemowych managerów paczek,
że zamiast korzystać z zależności (dependencies) zaimstalowanych na systemie,
instalują je osobno dla każdej aplikacji.
Jest to łatwiejsze dla developerów,
ponieważ czasami aktualizacja jakieś biblioteki (zestaw narzędzi dla programisty)
powoduje, że aplikacja nie działa poprawnie.

Jednak ma to bardzo negatywną konotację - powoduje, że developerzy
nie aktualizują swoich aplikacji tak często, jak jest to wymagane korzystając z najnowszych
wersji bibliotek.

Jeżeli na przykład jakaś biblioteka, albo inna zależność (np. inna aplikacja)
miała dziury pozwalające na wuykorzystanie ją do penetracji
zabazpieczeń systemu, to przy aktualizacji normalniej (np. pacman -Syu)
ta dziura zostaje załatana.
Jednak w przypadku flatpak/snap nie mamy takiej gwarancji,
aktualizaja zależności leży w gestii jej developera...

***Dlatego jeżeli tylko jest to możliwe, to preferowane jest instalowanie
aplikacji z odicjalnych repozytorów, przy użyciu package managerów,
takich ja Pacman, albo Apptitude***

Czasami jednak nie ma innych sensownych rozwiązań,
jak w przypadk Spotify na Ubuntu.

```bash
flapak search spotify
```

```bash
flatpak install com.spotify.Client
```

I włączenie aplikacji:

```bash
flatpak run com.spotify.Client
```

Czasami po takiej operacji nie będziemy mieli skrótu do tej aplikacji,
a używanie flatpak run ... jest meczące.
Dlatego warto dodać sobie plik uruchamialny do
*.local/bin*, żeby móc używać go z np. DMenu (w mojej konfiguracji
Alt+Spacja odpala DMenu)

1. upewniamy się, że *.local/bin* jest w naszym PATH
```bash
echo $PATH
```

jeżeli nie ma tam *...:$USER/.local/bin/:...*, to dodajemy
to w ten sposób

```bash
echo "export PATH=/home/\$USER/.local/bin/:\$PATH" >> ~/.profile; export PATH=/home/$USER/.local.bin/:$PATH
```

2. Tworzymy plik *~/.local/bin/<nazwa_aplikacji>* wybramym edytorem tekstowym,
o treści:

```bash
#!/bin/sh

flatpak run com.spotify.Client
```

I sprawiamy, żeby był możliwy do uruchomienia:

```bash
chmod +x ~/.local/bin/<nazwa_pliku>
```

lub robimy to jednym poleceniem, używająch echo (zastępujemy pierwsze "spotify" nazwą aplikacji - na początku w FILE=... i później w flatpak run *com.spotify.Client*):

```bash
FILE=spotify; [ -f ~/.local/bin/$FILE ] && echo "Plik $FILE już istnieje. Nie udało się stworzyc pliku $FILE..."; [ -f ~/.local/bin/$FILE ] || { echo -e '#!/bin/sh\nflatpak run com.spotify.Client' > ~/.local/bin/$FILE; chmod +x ~/.local/bin/$FILE; echo "Udało się stworzyć $FILE" }
```

3. [(opcjonalnie) Dodajemy plik .desktop, żeby mieć skrót z "Menu Start"](https://wiki.archlinux.org/index.php/Desktop_entries#Application_entry)

## Aktualizacja aplikacji flatpak


```bash
flatpak update
```

