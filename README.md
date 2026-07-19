# some style please!

Minimalistyczny, szybki i responsywny motyw [Hugo](https://gohugo.io/) oparty na [nostyleplease](https://github.com/hanwenguo/hugo-theme-nostyleplease). Motyw zachowuje prosty, tekstowy charakter oryginału, dodając obsługę wielu języków, stron, taksonomii, podpisów obrazków, galerii i lekkich shortcode’ów.

### [Demo motywu](https://004822.xyz)

![Schematy kolorów](https://github.com/jkkNl/somestyleplease/raw/main/images/colors.webp)

## Funkcje

- minimalistyczny i responsywny interfejs;
- kilka schematów kolorystycznych: `auto`, `light`, `dark`, `matrix`, `bear`, `together`;
- obsługa wielu języków dla stron, wpisów, taksonomii i RSS;
- automatyczny przełącznik języków pokazujący tylko dostępne tłumaczenia;
- kategorie i tagi;
- RSS dla poszczególnych języków;
- favicon konfigurowany z poziomu parametrów motywu;
- TOC z opcjonalną ramką;
- MathJax;
- podpisy obrazków i filmów z obsługą linków Markdown;
- responsywne galerie obrazów bez JavaScriptu;
- wyróżnione fragmenty tekstu bez dodatkowego globalnego CSS;
- natywne przypisy Goldmarka w treści;
- konfiguracja przez Hugo Pipes i fingerprinting CSS;
- brak wymaganych zależności Node.js.

## Instalacja

Sklonuj repozytorium lub dodaj je jako submoduł do `themes/somestyleplease`, a następnie ustaw motyw w konfiguracji Hugo.

**TOML**

~~~toml
theme = "somestyleplease"
~~~

**YAML**

~~~yaml
theme: somestyleplease
~~~

Przykładowe treści dostarczane z motywem mają `draft = true`. Aby zobaczyć je lokalnie, uruchom:

~~~bash
hugo server --buildDrafts
~~~

W repozytorium znajduje się również demonstracyjny wpis `gallery-demo` pokazujący galerie, podpisy, linki w podpisach i wyróżnione fragmenty.

## Konfiguracja

Ustawienia motywu znajdują się w `params.theme_config`.

**TOML**

~~~toml
[params.theme_config]
appearance = "auto" # auto | light | dark | matrix | bear | together
date_format = "02.01.2006"
categories = true
tags = true
post_limit = 100
show_more_url = "posts"
favicon = "favicon.ico"
~~~

**YAML**

~~~yaml
params:
  theme_config:
    appearance: auto
    date_format: "02.01.2006"
    categories: true
    tags: true
    post_limit: 100
    show_more_url: posts
    favicon: favicon.ico
~~~

Konfiguracja projektu użytkownika ma pierwszeństwo przed domyślnymi wartościami motywu.

### Favicon

Umieść plik w katalogu `static`:

~~~text
static/favicon.ico
~~~

Następnie wskaż nazwę pliku:

~~~toml
[params.theme_config]
favicon = "favicon.ico"
~~~

## Tworzenie treści

### Front matter

Motyw korzysta ze standardowego front matter Hugo. Najważniejsze pola:

| Pole | Typ | Zastosowanie |
| --- | --- | --- |
| `title` | string | Tytuł strony lub wpisu |
| `date` | date | Data publikacji |
| `draft` | bool | Ukrycie treści w zwykłym buildzie |
| `categories` | array | Kategorie wpisu |
| `tags` | array | Tagi wpisu |
| `toc` | bool | Włączenie spisu treści |
| `tocBorder` | bool | Dodanie ramki do spisu treści |
| `mathjax` | bool | Włączenie MathJax na stronie |
| `custom_js` | array | Pliki JS z `assets/js/` |
| `weight` | int | Kolejność stron i elementów menu |

Przykład:

~~~toml
+++
title = "Mój wpis"
date = 2025-07-19T12:00:00+02:00
draft = false
categories = ["technologia"]
tags = ["hugo", "markdown"]
toc = true
tocBorder = true
mathjax = false
+++
~~~

### Przypisy

Przypisy należy dodawać w zwykłej treści Markdown, korzystając z natywnej składni Goldmarka:

~~~markdown
To jest tekst z przypisem[^1].

[^1]: Treść przypisu.
~~~

Przypisy w podpisach obrazków nie są przechwytywane przez motyw. Dzięki temu Hugo zachowuje natywne i przewidywalne przetwarzanie przypisów.

## Obrazy i wideo

### Podpisy obrazków

Opcjonalny tytuł obrazu jest wyświetlany jako wyśrodkowany podpis:

~~~markdown
![Tekst alternatywny](image.jpg "Widoczny podpis")
~~~

Podpis może zawierać podstawowy Markdown, w tym linki:

~~~markdown
![Zegarek](watch.webp "Zdjęcie z [Reddita](https://www.reddit.com/)")
~~~

Obrazy bez tytułu są renderowane bez podpisu. Tekst alternatywny pozostaje niezależny od podpisu i służy dostępności.

### Wideo przez Markdown

Wideo można osadzić tak samo jak obraz:

~~~markdown
![video](/attachment/example/video.webm)
~~~

Motyw rozpoznaje również rozszerzenia `webm`, `mp4`, `m4v`, `ogv`, `ogg` i `mov`, więc tekst alternatywny może opisywać nagranie:

~~~markdown
![Porównanie wskazówek](/attachment/example/video.webm "Podpis filmu")
~~~

Wideo otrzymuje kontrolki, `preload="metadata"` i responsywną szerokość.

## Shortcode’y

### Galerie obrazów

Shortcode `gallery` tworzy responsywną galerię CSS Grid bez JavaScriptu:

~~~markdown
{{< gallery label="Galeria zegarków" >}}

![Casio](casio.webp "Casio")
![Tissot](tissot.webp "Tissot")
![Tudor](tudor.webp "Tudor")

{{< /gallery >}}
~~~

Podpisy oraz linki w podpisach działają tak samo jak przy pojedynczym obrazie. Galeria automatycznie dopasowuje liczbę kolumn do szerokości ekranu.

### Wyróżniony fragment

Shortcode `highlight` otacza ważny fragment minimalistyczną ramką podobną do ramki TOC:

~~~markdown
{{< highlight >}}

To jest ważna informacja z **pogrubieniem** i [linkiem](https://gohugo.io/).

{{< /highlight >}}
~~~

CSS wyróżnienia znajduje się bezpośrednio w shortcode, więc nie zwiększa globalnego arkusza stylów, jeśli funkcja nie jest używana.

### Szczegóły

Shortcode `details` tworzy rozwijany element HTML:

~~~markdown
{{< details summary="Pokaż więcej" open="false" >}}

Ukryta treść z **Markdownem**.

{{< /details >}}
~~~

### Wideo przez shortcode

Dla zachowania zgodności dostępny jest również shortcode:

~~~markdown
{{< video src="/attachment/example/video.webm" >}}
~~~

Dla nowych treści zalecana jest składnia Markdown opisana wyżej, ponieważ jest krótsza i korzysta z tego samego render hooka co obrazy.

### Matematyka

Na stronie z `mathjax = true` można używać shortcode’ów `texi` i `texd`:

~~~markdown
{{< texi "x^2 + y^2 = z^2" >}}
~~~

## Taksonomie

Jeśli `categories = true` lub `tags = true`, motyw generuje strony kategorii i tagów. Nazwy terminów są wyświetlane małymi literami, a link powrotu do strony głównej otrzymuje taki sam górny odstęp jak w artykułach.

Wpis może mieć wiele kategorii i tagów:

~~~toml
categories = ["zegarki", "technologia"]
tags = ["hugo", "markdown"]
~~~

## Wielojęzyczność

Motyw obsługuje strony, wpisy, taksonomie i RSS w wielu językach.

### Konfiguracja języków

**TOML**

~~~toml
defaultContentLanguage = "en"
defaultContentLanguageInSubdir = true

[languages]
  [languages.en]
    locale = "en-US"
    label = "English"
    weight = 1

  [languages.pl]
    locale = "pl-PL"
    label = "Polski"
    weight = 2
~~~

**YAML**

~~~yaml
defaultContentLanguage: en
defaultContentLanguageInSubdir: true

languages:
  en:
    locale: en-US
    label: English
    weight: 1
  pl:
    locale: pl-PL
    label: Polski
    weight: 2
~~~

### Pliki tłumaczeń

Używaj tego samego basename’u i dodawaj kod języka:

~~~text
content/posts/my-post.en.md
content/posts/my-post.pl.md
content/pages/about.en.md
content/pages/about.pl.md
~~~

Przełącznik języków pokazuje tylko inne dostępne wersje tego samego zasobu. Jeśli dla strony nie istnieje tłumaczenie, nie pojawi się pusty lub niepotrzebny link.

### Tłumaczenia interfejsu

Dodaj pliki `i18n/<język>.yaml`, np.:

~~~text
i18n/en.yaml
i18n/pl.yaml
~~~

Motyw korzysta m.in. z następujących kluczy:

- `homepage.intro`;
- `homepage.moreintro`;
- `homepage.footer`;
- `general.back_home_text`;
- `general.categories`;
- `general.tags`;
- `categories.<category-slug>`.

Jeśli nie chcesz prefiksu `/en/` dla domyślnego języka, ustaw:

~~~toml
defaultContentLanguageInSubdir = false
~~~

## Dostosowywanie motywu

Hugo pozwala nadpisywać pliki motywu w katalogu projektu. Przykładowo własny footer można umieścić w:

~~~text
layouts/partials/footer.html
~~~

Własne pliki CSS i JavaScript można dodawać w katalogach:

~~~text
assets/css/
assets/js/
~~~

Motyw korzysta z Hugo Pipes, kompresji i fingerprintingu arkusza CSS. Nie wymaga Node.js ani npm.

## Licencja i podziękowania

Motyw jest dostępny na licencji [MIT](https://opensource.org/licenses/MIT). Zgłoszenia błędów i pull requesty są mile widziane.

Część kodu pochodzi z projektów [hanwenguo/hugo-theme-nostyleplease](https://github.com/hanwenguo/hugo-theme-nostyleplease) i [wooseopkim/hugo-theme-nostyleplease](https://github.com/wooseopkim/hugo-theme-nostyleplease). Część przykładowych treści pochodzi z [tego motywu Jekyll](https://github.com/huangyz0918/moving).
