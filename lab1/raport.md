# Raport z zadania 1
## Cel ćwiczenia
Celem ćwiczenia było pobranie odpowiednich map satelitarnych z platformy [Copernicus Browser](https://browser.dataspace.copernicus.eu/), a następnie przygotowanie mapy z wizualizacją wskaźnika NDVI.

## Przebieg ćwiczenia
W serwisie  [Copernicus Browser](https://browser.dataspace.copernicus.eu/) zaznaczono wybrany fragment mapy satelitarnej (Rys. 1). Następnie w zakładce **Analytical** pobrano dane rastrowe odpowiadające dwóm pasmom spektralnym: **B04 (RED)** — pasmo czerwone, oraz **B08 (NIR)** — bliską podczerwień (Rys. 2).

![Wybór obszaru na mapie w serwisie Copernicus](images/01_copernicus_browser.png)
*Rys. 1. Zaznaczenie obszaru w serwisie Copernicus*

![Pobranie map B04 i B08](images/02_copernicus_download.png)
*Rys. 2. Pobieranie pasm spektralnych w Copernicus Browser.*

Pobrane rastry zaimportowano do nowego projektu QGIS i nazwano `b04` (Rys. 3) oraz `b08` (Rys. 4). W narzędziu **Raster → Raster Calculator** obliczono wskaźnik NDVI (Rys. 5) zgodnie ze wzorem:

$$
NDVI = \frac{NIR - RED}{NIR + RED}
$$

![Warstwa `b04` w programie QGIS](images/03_b04.png)
*Rys. 3. Warstwa `b04` w programie QGIS.*

![Warstwa `b08` w programie QGIS](images/04_b08.png)
*Rys. 4. Warstwa `b04` w programie QGIS.*

![Raster Calculator](images/05_ndvi_calculator.png)
*Rys. 5. Narzędzie **Raster Calculator***

Wynik oobliczeń zapisano w nowej warstwie nazwanej `ndvi` (Rys. 6).

![Warstwa `ndvi` w kolorach szarości](images/06_ndvi_bw.png)
*Rys. 6. Warstwa NDVI.*

Dla otrzymanej warstwy zmieniono sposób wyświetlania na **Singleband pseudocolor**, aby uwidocznić zróżnicowanie wartości NDVI (Rys. 7). Przyjęto zakres wizualizacji od −0,1 do 0,92 (Rys. 8).

![Końcowa mapa NDVI](images/09_ndvi_layer.png)
*Rys. 7. Wizualizacja otrzymanego wskaźnika NDVI.*

![Konfiguracja **Symbology**](images/08_ndvi_properties_2.png)
*Rys. 8. Konfiguracja właściwości **Symbology** warstwy NDVI.*

## Wyniki i wnioski

Uzyskano mapę przedstawiającą przestrzenne zróżnicowanie wskaźnika NDVI na wybranym obszarze. Wartości wyższe są zazwyczaj związane z obecnością aktywnej roślinności, natomiast niskie lub ujemne mogą odpowiadać m.in. zabudowie, odkrytej glebie i wodzie. Przyjęta paleta barw pozwala łatwiej odróżnić poszczególne obszary, jednak kolory należy interpretować zgodnie z przyjętą skalą. Dla porównania mapa w kolorach naturalnych. Uzysiane wyniki są zgodne z obserwacjami wynikającymi z porównania mapy satelitarną w kolorach widzialnych przez ludzkie oko (Rys. 9).

![Obraz obszaru w barwach naturalnych](images/09b_true_color.png)

*Rys. 9. Obraz w barwach naturalnych do porównania z mapą NDVI.*
