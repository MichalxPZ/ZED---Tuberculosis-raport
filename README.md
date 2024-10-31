## Ustawienia

Wykorzystane biblioteki:

-   knitr,
-   dplyr,
-   EDAWR,
-   ggplot2

## Wczytanie danych z cache’owaniem

Wyświetlenie typów danych, podsumowania tabeli oraz kilku pierwszych
wierszy zbioru.

    ## tibble [3,800 × 6] (S3: tbl_df/tbl/data.frame)
    ##  $ country: chr [1:3800] "Afghanistan" "Afghanistan" "Afghanistan" "Afghanistan" ...
    ##  $ year   : int [1:3800] 1995 1995 1996 1996 1997 1997 1998 1998 1999 1999 ...
    ##  $ sex    : chr [1:3800] "female" "male" "female" "male" ...
    ##  $ child  : int [1:3800] NA NA NA NA 5 0 45 30 25 8 ...
    ##  $ adult  : int [1:3800] NA NA NA NA 96 26 1142 500 484 212 ...
    ##  $ elderly: int [1:3800] NA NA NA NA 1 0 20 41 8 8 ...

    ##    country               year          sex                child        
    ##  Length:3800        Min.   :1995   Length:3800        Min.   :    0.0  
    ##  Class :character   1st Qu.:1999   Class :character   1st Qu.:   25.0  
    ##  Mode  :character   Median :2004   Mode  :character   Median :   76.0  
    ##                     Mean   :2004                      Mean   :  493.2  
    ##                     3rd Qu.:2009                      3rd Qu.:  264.5  
    ##                     Max.   :2013                      Max.   :25661.0  
    ##                                                       NA's   :396      
    ##      adult           elderly        
    ##  Min.   :     0   Min.   :     0.0  
    ##  1st Qu.:  1128   1st Qu.:    84.5  
    ##  Median :  2589   Median :   230.0  
    ##  Mean   : 10864   Mean   :  1253.0  
    ##  3rd Qu.:  6706   3rd Qu.:   640.0  
    ##  Max.   :731540   Max.   :125991.0  
    ##  NA's   :413      NA's   :413

    ## # A tibble: 6 × 6
    ##   country      year sex    child adult elderly
    ##   <chr>       <int> <chr>  <int> <int>   <int>
    ## 1 Afghanistan  1995 female    NA    NA      NA
    ## 2 Afghanistan  1995 male      NA    NA      NA
    ## 3 Afghanistan  1996 female    NA    NA      NA
    ## 4 Afghanistan  1996 male      NA    NA      NA
    ## 5 Afghanistan  1997 female     5    96       1
    ## 6 Afghanistan  1997 male       0    26       0

Zbiór danych zawiera 3800 rekordów, które przedstawiają informacje o
liczbie zachorowań na gruźlicę w różnych krajach w latach 1995-2013.
Atrybuty zbioru danych to: kraj(‘country’), rok(‘year’), płeć(‘sex’)
oraz 3 atrybuty z przydziałem do grupy wiekowej: dzieci, dorośli i osoby
starsze(‘child’, ‘adult’, ‘elderly’).

## Podsumowanie liczby zachorowań z podziałem na płeć

Dokonujemy podsumowania ze względu na liczbę wystąpień choroby u każdej
z płci. Sumujemy dzieci, dorosłych i osoby starsze w każdej grupie.
Generujemy wykres kolumnowy dla każdej z płci.

    ## # A tibble: 2 × 2
    ##   sex       total
    ##   <chr>     <int>
    ## 1 female 15656162
    ## 2 male   27062807

![](/Users/michal/StudioProjects/INF-2ST-2sem-tpd/ZED/EDAWR/edawr_files/figure-markdown_strict/gender-summary-1.png)

## Podsumowanie sumarycznej liczby zachorowań wśród dzieci, dorosłych i osób starszych w kolejnych latach

Grupujemy dane po latach i tworzymy podsumowania osobno dla dzieci,
dorosłych oraz osób starszych. Generujemy wykres liniowy zachorowań dla
każdej grupy wiekowej w kolejnych latach.
![](/Users/michal/StudioProjects/INF-2ST-2sem-tpd/ZED/EDAWR/edawr_files/figure-markdown_strict/age-group-summary-1.png)

## Podsumowanie sumarycznej liczby zachorowań wśród dzieci, dorosłych i osób starszych w kolejnych latach z podziałem na kraje

Grupujemy dane po krajach oraz latach i tworzymy podsumowania osobno dla
dzieci, dorosłych oraz osób starszych.

Generujemy wykresy liniowe zachorowań dla każdej grupy wiekowej w
kolejnych latach z podziałem na kraje.
![](/Users/michal/StudioProjects/INF-2ST-2sem-tpd/ZED/EDAWR/edawr_files/figure-markdown_strict/country-plots-1.png)![](/Users/michal/StudioProjects/INF-2ST-2sem-tpd/ZED/EDAWR/edawr_files/figure-markdown_strict/country-plots-2.png)![](/Users/michal/StudioProjects/INF-2ST-2sem-tpd/ZED/EDAWR/edawr_files/figure-markdown_strict/country-plots-3.png)![](/Users/michal/StudioProjects/INF-2ST-2sem-tpd/ZED/EDAWR/edawr_files/figure-markdown_strict/country-plots-4.png)![](/Users/michal/StudioProjects/INF-2ST-2sem-tpd/ZED/EDAWR/edawr_files/figure-markdown_strict/country-plots-5.png)![](/Users/michal/StudioProjects/INF-2ST-2sem-tpd/ZED/EDAWR/edawr_files/figure-markdown_strict/country-plots-6.png)![](/Users/michal/StudioProjects/INF-2ST-2sem-tpd/ZED/EDAWR/edawr_files/figure-markdown_strict/country-plots-7.png)![](/Users/michal/StudioProjects/INF-2ST-2sem-tpd/ZED/EDAWR/edawr_files/figure-markdown_strict/country-plots-8.png)![](/Users/michal/StudioProjects/INF-2ST-2sem-tpd/ZED/EDAWR/edawr_files/figure-markdown_strict/country-plots-9.png)![](/Users/michal/StudioProjects/INF-2ST-2sem-tpd/ZED/EDAWR/edawr_files/figure-markdown_strict/country-plots-10.png)![](/Users/michal/StudioProjects/INF-2ST-2sem-tpd/ZED/EDAWR/edawr_files/figure-markdown_strict/country-plots-11.png)![](/Users/michal/StudioProjects/INF-2ST-2sem-tpd/ZED/EDAWR/edawr_files/figure-markdown_strict/country-plots-12.png)![](/Users/michal/StudioProjects/INF-2ST-2sem-tpd/ZED/EDAWR/edawr_files/figure-markdown_strict/country-plots-13.png)![](/Users/michal/StudioProjects/INF-2ST-2sem-tpd/ZED/EDAWR/edawr_files/figure-markdown_strict/country-plots-14.png)![](/Users/michal/StudioProjects/INF-2ST-2sem-tpd/ZED/EDAWR/edawr_files/figure-markdown_strict/country-plots-15.png)![](/Users/michal/StudioProjects/INF-2ST-2sem-tpd/ZED/EDAWR/edawr_files/figure-markdown_strict/country-plots-16.png)![](/Users/michal/StudioProjects/INF-2ST-2sem-tpd/ZED/EDAWR/edawr_files/figure-markdown_strict/country-plots-17.png)![](/Users/michal/StudioProjects/INF-2ST-2sem-tpd/ZED/EDAWR/edawr_files/figure-markdown_strict/country-plots-18.png)![](/Users/michal/StudioProjects/INF-2ST-2sem-tpd/ZED/EDAWR/edawr_files/figure-markdown_strict/country-plots-19.png)![](/Users/michal/StudioProjects/INF-2ST-2sem-tpd/ZED/EDAWR/edawr_files/figure-markdown_strict/country-plots-20.png)![](/Users/michal/StudioProjects/INF-2ST-2sem-tpd/ZED/EDAWR/edawr_files/figure-markdown_strict/country-plots-21.png)![](/Users/michal/StudioProjects/INF-2ST-2sem-tpd/ZED/EDAWR/edawr_files/figure-markdown_strict/country-plots-22.png)![](/Users/michal/StudioProjects/INF-2ST-2sem-tpd/ZED/EDAWR/edawr_files/figure-markdown_strict/country-plots-23.png)![](/Users/michal/StudioProjects/INF-2ST-2sem-tpd/ZED/EDAWR/edawr_files/figure-markdown_strict/country-plots-24.png)![](/Users/michal/StudioProjects/INF-2ST-2sem-tpd/ZED/EDAWR/edawr_files/figure-markdown_strict/country-plots-25.png)![](/Users/michal/StudioProjects/INF-2ST-2sem-tpd/ZED/EDAWR/edawr_files/figure-markdown_strict/country-plots-26.png)![](/Users/michal/StudioProjects/INF-2ST-2sem-tpd/ZED/EDAWR/edawr_files/figure-markdown_strict/country-plots-27.png)![](/Users/michal/StudioProjects/INF-2ST-2sem-tpd/ZED/EDAWR/edawr_files/figure-markdown_strict/country-plots-28.png)![](/Users/michal/StudioProjects/INF-2ST-2sem-tpd/ZED/EDAWR/edawr_files/figure-markdown_strict/country-plots-29.png)![](/Users/michal/StudioProjects/INF-2ST-2sem-tpd/ZED/EDAWR/edawr_files/figure-markdown_strict/country-plots-30.png)![](/Users/michal/StudioProjects/INF-2ST-2sem-tpd/ZED/EDAWR/edawr_files/figure-markdown_strict/country-plots-31.png)![](/Users/michal/StudioProjects/INF-2ST-2sem-tpd/ZED/EDAWR/edawr_files/figure-markdown_strict/country-plots-32.png)![](/Users/michal/StudioProjects/INF-2ST-2sem-tpd/ZED/EDAWR/edawr_files/figure-markdown_strict/country-plots-33.png)![](/Users/michal/StudioProjects/INF-2ST-2sem-tpd/ZED/EDAWR/edawr_files/figure-markdown_strict/country-plots-34.png)![](/Users/michal/StudioProjects/INF-2ST-2sem-tpd/ZED/EDAWR/edawr_files/figure-markdown_strict/country-plots-35.png)![](/Users/michal/StudioProjects/INF-2ST-2sem-tpd/ZED/EDAWR/edawr_files/figure-markdown_strict/country-plots-36.png)![](/Users/michal/StudioProjects/INF-2ST-2sem-tpd/ZED/EDAWR/edawr_files/figure-markdown_strict/country-plots-37.png)![](/Users/michal/StudioProjects/INF-2ST-2sem-tpd/ZED/EDAWR/edawr_files/figure-markdown_strict/country-plots-38.png)![](/Users/michal/StudioProjects/INF-2ST-2sem-tpd/ZED/EDAWR/edawr_files/figure-markdown_strict/country-plots-39.png)![](/Users/michal/StudioProjects/INF-2ST-2sem-tpd/ZED/EDAWR/edawr_files/figure-markdown_strict/country-plots-40.png)![](/Users/michal/StudioProjects/INF-2ST-2sem-tpd/ZED/EDAWR/edawr_files/figure-markdown_strict/country-plots-41.png)![](/Users/michal/StudioProjects/INF-2ST-2sem-tpd/ZED/EDAWR/edawr_files/figure-markdown_strict/country-plots-42.png)![](/Users/michal/StudioProjects/INF-2ST-2sem-tpd/ZED/EDAWR/edawr_files/figure-markdown_strict/country-plots-43.png)![](/Users/michal/StudioProjects/INF-2ST-2sem-tpd/ZED/EDAWR/edawr_files/figure-markdown_strict/country-plots-44.png)![](/Users/michal/StudioProjects/INF-2ST-2sem-tpd/ZED/EDAWR/edawr_files/figure-markdown_strict/country-plots-45.png)![](/Users/michal/StudioProjects/INF-2ST-2sem-tpd/ZED/EDAWR/edawr_files/figure-markdown_strict/country-plots-46.png)![](/Users/michal/StudioProjects/INF-2ST-2sem-tpd/ZED/EDAWR/edawr_files/figure-markdown_strict/country-plots-47.png)![](/Users/michal/StudioProjects/INF-2ST-2sem-tpd/ZED/EDAWR/edawr_files/figure-markdown_strict/country-plots-48.png)![](/Users/michal/StudioProjects/INF-2ST-2sem-tpd/ZED/EDAWR/edawr_files/figure-markdown_strict/country-plots-49.png)![](/Users/michal/StudioProjects/INF-2ST-2sem-tpd/ZED/EDAWR/edawr_files/figure-markdown_strict/country-plots-50.png)![](/Users/michal/StudioProjects/INF-2ST-2sem-tpd/ZED/EDAWR/edawr_files/figure-markdown_strict/country-plots-51.png)![](/Users/michal/StudioProjects/INF-2ST-2sem-tpd/ZED/EDAWR/edawr_files/figure-markdown_strict/country-plots-52.png)![](/Users/michal/StudioProjects/INF-2ST-2sem-tpd/ZED/EDAWR/edawr_files/figure-markdown_strict/country-plots-53.png)![](/Users/michal/StudioProjects/INF-2ST-2sem-tpd/ZED/EDAWR/edawr_files/figure-markdown_strict/country-plots-54.png)![](/Users/michal/StudioProjects/INF-2ST-2sem-tpd/ZED/EDAWR/edawr_files/figure-markdown_strict/country-plots-55.png)![](/Users/michal/StudioProjects/INF-2ST-2sem-tpd/ZED/EDAWR/edawr_files/figure-markdown_strict/country-plots-56.png)![](/Users/michal/StudioProjects/INF-2ST-2sem-tpd/ZED/EDAWR/edawr_files/figure-markdown_strict/country-plots-57.png)![](/Users/michal/StudioProjects/INF-2ST-2sem-tpd/ZED/EDAWR/edawr_files/figure-markdown_strict/country-plots-58.png)![](/Users/michal/StudioProjects/INF-2ST-2sem-tpd/ZED/EDAWR/edawr_files/figure-markdown_strict/country-plots-59.png)![](/Users/michal/StudioProjects/INF-2ST-2sem-tpd/ZED/EDAWR/edawr_files/figure-markdown_strict/country-plots-60.png)![](/Users/michal/StudioProjects/INF-2ST-2sem-tpd/ZED/EDAWR/edawr_files/figure-markdown_strict/country-plots-61.png)![](/Users/michal/StudioProjects/INF-2ST-2sem-tpd/ZED/EDAWR/edawr_files/figure-markdown_strict/country-plots-62.png)![](/Users/michal/StudioProjects/INF-2ST-2sem-tpd/ZED/EDAWR/edawr_files/figure-markdown_strict/country-plots-63.png)![](/Users/michal/StudioProjects/INF-2ST-2sem-tpd/ZED/EDAWR/edawr_files/figure-markdown_strict/country-plots-64.png)![](/Users/michal/StudioProjects/INF-2ST-2sem-tpd/ZED/EDAWR/edawr_files/figure-markdown_strict/country-plots-65.png)![](/Users/michal/StudioProjects/INF-2ST-2sem-tpd/ZED/EDAWR/edawr_files/figure-markdown_strict/country-plots-66.png)![](/Users/michal/StudioProjects/INF-2ST-2sem-tpd/ZED/EDAWR/edawr_files/figure-markdown_strict/country-plots-67.png)![](/Users/michal/StudioProjects/INF-2ST-2sem-tpd/ZED/EDAWR/edawr_files/figure-markdown_strict/country-plots-68.png)![](/Users/michal/StudioProjects/INF-2ST-2sem-tpd/ZED/EDAWR/edawr_files/figure-markdown_strict/country-plots-69.png)![](/Users/michal/StudioProjects/INF-2ST-2sem-tpd/ZED/EDAWR/edawr_files/figure-markdown_strict/country-plots-70.png)![](/Users/michal/StudioProjects/INF-2ST-2sem-tpd/ZED/EDAWR/edawr_files/figure-markdown_strict/country-plots-71.png)![](/Users/michal/StudioProjects/INF-2ST-2sem-tpd/ZED/EDAWR/edawr_files/figure-markdown_strict/country-plots-72.png)![](/Users/michal/StudioProjects/INF-2ST-2sem-tpd/ZED/EDAWR/edawr_files/figure-markdown_strict/country-plots-73.png)![](/Users/michal/StudioProjects/INF-2ST-2sem-tpd/ZED/EDAWR/edawr_files/figure-markdown_strict/country-plots-74.png)![](/Users/michal/StudioProjects/INF-2ST-2sem-tpd/ZED/EDAWR/edawr_files/figure-markdown_strict/country-plots-75.png)![](/Users/michal/StudioProjects/INF-2ST-2sem-tpd/ZED/EDAWR/edawr_files/figure-markdown_strict/country-plots-76.png)![](/Users/michal/StudioProjects/INF-2ST-2sem-tpd/ZED/EDAWR/edawr_files/figure-markdown_strict/country-plots-77.png)![](/Users/michal/StudioProjects/INF-2ST-2sem-tpd/ZED/EDAWR/edawr_files/figure-markdown_strict/country-plots-78.png)![](/Users/michal/StudioProjects/INF-2ST-2sem-tpd/ZED/EDAWR/edawr_files/figure-markdown_strict/country-plots-79.png)![](/Users/michal/StudioProjects/INF-2ST-2sem-tpd/ZED/EDAWR/edawr_files/figure-markdown_strict/country-plots-80.png)![](/Users/michal/StudioProjects/INF-2ST-2sem-tpd/ZED/EDAWR/edawr_files/figure-markdown_strict/country-plots-81.png)![](/Users/michal/StudioProjects/INF-2ST-2sem-tpd/ZED/EDAWR/edawr_files/figure-markdown_strict/country-plots-82.png)![](/Users/michal/StudioProjects/INF-2ST-2sem-tpd/ZED/EDAWR/edawr_files/figure-markdown_strict/country-plots-83.png)![](/Users/michal/StudioProjects/INF-2ST-2sem-tpd/ZED/EDAWR/edawr_files/figure-markdown_strict/country-plots-84.png)![](/Users/michal/StudioProjects/INF-2ST-2sem-tpd/ZED/EDAWR/edawr_files/figure-markdown_strict/country-plots-85.png)![](/Users/michal/StudioProjects/INF-2ST-2sem-tpd/ZED/EDAWR/edawr_files/figure-markdown_strict/country-plots-86.png)![](/Users/michal/StudioProjects/INF-2ST-2sem-tpd/ZED/EDAWR/edawr_files/figure-markdown_strict/country-plots-87.png)![](/Users/michal/StudioProjects/INF-2ST-2sem-tpd/ZED/EDAWR/edawr_files/figure-markdown_strict/country-plots-88.png)![](/Users/michal/StudioProjects/INF-2ST-2sem-tpd/ZED/EDAWR/edawr_files/figure-markdown_strict/country-plots-89.png)![](/Users/michal/StudioProjects/INF-2ST-2sem-tpd/ZED/EDAWR/edawr_files/figure-markdown_strict/country-plots-90.png)![](/Users/michal/StudioProjects/INF-2ST-2sem-tpd/ZED/EDAWR/edawr_files/figure-markdown_strict/country-plots-91.png)![](/Users/michal/StudioProjects/INF-2ST-2sem-tpd/ZED/EDAWR/edawr_files/figure-markdown_strict/country-plots-92.png)![](/Users/michal/StudioProjects/INF-2ST-2sem-tpd/ZED/EDAWR/edawr_files/figure-markdown_strict/country-plots-93.png)![](/Users/michal/StudioProjects/INF-2ST-2sem-tpd/ZED/EDAWR/edawr_files/figure-markdown_strict/country-plots-94.png)![](/Users/michal/StudioProjects/INF-2ST-2sem-tpd/ZED/EDAWR/edawr_files/figure-markdown_strict/country-plots-95.png)![](/Users/michal/StudioProjects/INF-2ST-2sem-tpd/ZED/EDAWR/edawr_files/figure-markdown_strict/country-plots-96.png)![](/Users/michal/StudioProjects/INF-2ST-2sem-tpd/ZED/EDAWR/edawr_files/figure-markdown_strict/country-plots-97.png)![](/Users/michal/StudioProjects/INF-2ST-2sem-tpd/ZED/EDAWR/edawr_files/figure-markdown_strict/country-plots-98.png)![](/Users/michal/StudioProjects/INF-2ST-2sem-tpd/ZED/EDAWR/edawr_files/figure-markdown_strict/country-plots-99.png)![](/Users/michal/StudioProjects/INF-2ST-2sem-tpd/ZED/EDAWR/edawr_files/figure-markdown_strict/country-plots-100.png)
