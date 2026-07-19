+++
title = 'Galeria zdjęć i podpisy'
date = 2025-07-19T12:00:00+02:00
draft = true
tags = ['demo', 'obrazy']
+++

Ten wpis pokazuje responsywną galerię zdjęć oraz podpisy zawierające linki Markdown.

## Galeria

{{< gallery label="Galeria zegarków" >}}

![Zdjęcie zegarka 1](https://yavuzceliker.github.io/sample-images/image-1021.jpg "Zdjęcie z [przykładowej kolekcji](https://github.com/yavuzceliker/sample-images)")
![Zdjęcie zegarka 2](https://yavuzceliker.github.io/sample-images/image-1022.jpg "Drugie zdjęcie z [linkiem do źródła](https://github.com/yavuzceliker/sample-images)")
![Zdjęcie zegarka 3](https://yavuzceliker.github.io/sample-images/image-1023.jpg "Trzeci podpis zdjęcia")

{{< /gallery >}}

Ta sama składnia podpisu działa również przy pojedynczym zdjęciu:

![Pojedyncze zdjęcie zegarka](https://yavuzceliker.github.io/sample-images/image-1021.jpg "Pojedyncze zdjęcie z [linkiem do źródła](https://github.com/yavuzceliker/sample-images)")

## Wyróżniony fragment

{{< highlight >}}

To jest ważna informacja wyróżniona taką samą minimalistyczną ramką jak spis treści. Może zawierać **Markdown** i [linki](https://gohugo.io/).

{{< /highlight >}}
