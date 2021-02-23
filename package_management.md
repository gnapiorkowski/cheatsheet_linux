# Debian Based (Ubuntu/Xubuntu/Lubuntu/Debian/...) (Laptop Dell latitude e6330)

## Aktualizacja systemu (raz na tydzień dwa wypadałoby robić)

```bash
sudo apt update && sudo apt upgrade
```
update aktualizuje bazę danych z aplikacjami

upgrade aktualizuje aplikacje zainstalowanie w systemie

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
apt remove <nazwa_aplikacji>
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
Jednak mamy jeszcze AUR (Arch User Repo.)
- Repozytoria Użytkowników Arch,
w których są aplikacje wrzucane przez użytkowników.
Dostajemy się tam używając *yay* jak poniżej.
***Bardzo przydatne, ponieważ znacznie ułatwia instalowanie
mniej popularnych aplikacji***

```bash
yay <nazwa_aplilacji>
```

Wyświetli nam ponumerowaną listę aplikacji i ich opisów, w których nazwach znaleziono <nazwa_aplikacji>. Należy wybrać jedną (wpisać numer z klawiatury) i zatwierdzić Enterem. Można wybrać kilka np 1 2 3, albo tak samo kilka 1-3. Przy wyborze kilku zostaną po prostu zainstalowane wszystkie.
