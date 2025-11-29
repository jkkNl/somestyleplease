+++
title = 'Spis treści, tag details, schematy kolorów kategorie i tagi (ten wpis ma naprawdę długi tytuł!)'
date = 2025-11-20T13:34:54+02:00
draft = true
toc = true
tocBorder = true
categories = ["przykładowe posty", "druga kategoria"]
tags = ["mogą być", "też różne tagi"]
+++

## Spis treści
### Co to jest?
Spis treści (Table of content - TOC) to to co widzisz na samej górze tego wpisu. Spis treści może być obramowany lub nie. Klikając na pozycję w spisie treści użytkownik jest przenoszony do odpowiedniego fragmentu strony, nagłówek zaś jest podświetlany.

### Jak włączyć TOC?
Tworząc nowego posta na samej górze, w miejscu gdzie jest tytuł posta i jego data musisz umieścić:
```toml
toc = true
tocBorder = true
```
Możesz oczywiście otworzyć tego posta `../themes/somestyleplease/content/posts/test-toc-and-details.pl.md` i otworzyć go w edytorze tekstu, wtedy zobaczysz jak to działa.

## Details
### Co to jest ?
HTMLowy standard niestety nie wspierany przez markdown. Ale ten szablon i tak go wspiera, więc gdy czasami chcesz coś ukryć skorzystaj z niego.
{{< details summary="Kliknij mnie" >}}
Tu może być dużo tekstu.
{{< /details >}}
### Jak użyć "Details"?
Cóż, musisz sprawdzić samodzielnie. Otwórz w edytorze tekstu `../themes/somestyleplease/content/posts/test-toc-and-details.pl.md` i wszystko stanie się jasne.

## Schematy kolorów
Jeśli chcesz zmienić kolorystykę szablonu edytuj plik config.toml i znajdź linijkę:
 ```toml
 appearance = "auto"
 ```
 Możesz ją zmienić na kilka predefiniowanych styli (`light`, `dark`, `matrix`, `bear`, `together`). Jeśli zostawisz `auto` schemat kolorów będzie się dopasowywać do kolorów w Twoim systemie operacyjnym (między `light` i `dark`). Możesz z łatwością dodawać swoje schematy kolorystyczne, po prostu edytuj CSS. Jest to proste i jeśli dajesz radę sobie z Hugo to edycja CSS nie powinna być też bardzo trudna. ;-)