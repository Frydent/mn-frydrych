# mn-frydrych.de

Strona Maksymiliana i Nikoliny. Leży na GitHub Pages — to znaczy, że
GitHub sam ją publikuje. Zapisujesz zmianę w plikach, mija minuta lub dwie
i zmiana jest widoczna w internecie. Nie ma żadnego „wysyłania na serwer".

---

## Co gdzie leży

```
index.html          strona główna — TU jest treść: teksty, zdjęcia, układ
style.css           wygląd: kolory, wielkości liter, odstępy
assets/img/         zdjęcia
assets/fonts/       czcionki
assets/fonts.css    definicje czcionek — tego pliku nie trzeba nigdy otwierać

nikolina/index.html wizytówka Nikoliny  (osobna, gotowa strona)
max/index.html      wizytówka Maxa      (osobna, gotowa strona)

CNAME               adres domeny — NIE RUSZAĆ
og.jpg              obrazek, który pokazuje się przy linku w WhatsAppie
favicon.ico         ikonka w karcie przeglądarki
icon.png
apple-touch-icon.png
```

---

## Dwie rzeczy, których nie wolno zmieniać

**Adresy `/nikolina` i `/max`.** Prowadzą do nich kody QR wydrukowane na
wizytówkach. Kod QR nie da się już zmienić, więc te dwa foldery muszą
zostać dokładnie tak nazwane. Wszystko *wewnątrz* tych stron można
zmieniać dowolnie — wygląd, kolory, teksty, zdjęcia. Tylko nazwy folderów
zostają.

**Plik `CNAME`.** Zawiera jedną linijkę: `mn-frydrych.de`. To on mówi
GitHubowi, pod jakim adresem ma stać strona. Skasowanie go zdejmuje stronę
z domeny.

---

## Jak coś zmienić

Najprościej wprost na GitHubie, bez instalowania czegokolwiek:

1. Kliknij plik, np. `index.html`
2. Ikonka ołówka po prawej stronie
3. Popraw, co trzeba
4. Na dole **Commit changes** — w okienku wpisz krótko, co zmieniłaś
5. Po minucie odśwież `mn-frydrych.de`

Każdy zapis to osobny punkt w historii. Jeśli coś pójdzie nie tak, w
zakładce **Commits** klikasz wcześniejszą wersję i wracasz do niej. Nic
nie ginie bezpowrotnie — dlatego można próbować śmiało.

### Zmienić tekst

Otwórz `index.html`. Teksty stoją między znacznikami, np.:

```html
<div class="data">10 • 09 • 2026</div>
<div class="imiona">MAKSYMILIAN &amp; NIKOLINA</div>
```

Zmieniasz to, co jest w środku. Reszty nie ruszasz.

### Zmienić zdjęcie

Wgraj nowy plik do `assets/img/` (przycisk **Add file → Upload files**),
a potem w `index.html` wskaż jego nazwę:

```html
<img class="zdjecie" src="assets/img/zamek.webp" alt="Zamek Chałupki">
```

`alt` to opis dla kogoś, kto zdjęcia nie zobaczy — warto go dopisać.

### Zmienić kolory

Wszystkie siedzą na górze `style.css`, w jednym miejscu:

```css
--tlo:    #eceae7;   /* tło dookoła */
--karta:  #e6e0d9;   /* tło strony */
--zloto:  #8a6c31;   /* data */
--tekst:  #524430;   /* imiona */
```

Zmiana jednej wartości przemalowuje wszystko, co jej używa.

### Dopisać nową sekcję

W `index.html`, między istniejącymi blokami:

```html
<section class="sekcja">
  <h2>Plan dnia</h2>
  <p>15:00 — ceremonia</p>
  <p>17:00 — przyjęcie</p>
</section>
```

Potem w `style.css` dopisujesz, jak ma wyglądać:

```css
.sekcja {
  background: var(--pasek);
  padding: 40px 24px;
  text-align: center;
  color: var(--tekst);
}
```

---

## Nowa podstrona

Załóż folder, a w nim `index.html` — na przykład `plan/index.html`.
Strona będzie pod adresem `mn-frydrych.de/plan`. Najprościej skopiować
`index.html` ze strony głównej i przerobić. Pamiętaj, żeby ścieżki do
zdjęć zaczynały się od ukośnika: `/assets/img/…`, bo jesteś piętro niżej.

---

## Nie musisz pisać kodu sama

Ta strona jest tak zbudowana, żeby dało się o niej **rozmawiać**. Możesz
otworzyć Claude'a, dać mu dostęp do tego repozytorium i powiedzieć zwykłym
zdaniem, czego chcesz — „dodaj sekcję z planem dnia", „zrób tło
ciemniejsze", „wstaw galerię ze zdjęciami z wesela". On zna te pliki
i wprowadzi zmiany.

Dlatego właśnie strona wygląda tak, jak wygląda: krótki `index.html`,
osobne `style.css`, zdjęcia jako pliki. Wcześniej wszystko siedziało
w jednym pliku na pół megabajta i nie dało się tego ani czytać, ani
sensownie zmieniać.
