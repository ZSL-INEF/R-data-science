# 作者简介 {#author .unnumbered}

上不了厅堂，下得了厨房。敲得了代码，逮得住蟑螂。

## 你好

```r
library(MASS)
library(tidyverse)
```

```
## ── Attaching packages ─────────────────────────────────────── tidyverse 1.3.2 ──
## ✔ ggplot2 3.4.0      ✔ purrr   0.3.5 
## ✔ tibble  3.1.8      ✔ dplyr   1.0.10
## ✔ tidyr   1.2.1      ✔ stringr 1.4.1 
## ✔ readr   2.1.3      ✔ forcats 0.5.2 
## ── Conflicts ────────────────────────────────────────── tidyverse_conflicts() ──
## ✖ dplyr::filter() masks stats::filter()
## ✖ dplyr::lag()    masks stats::lag()
## ✖ dplyr::select() masks MASS::select()
```

```r
library(ggplot2)
library(openxlsx)
df <- read.xlsx("~/desktop/UEFA.xlsx")
str(df)
```

```
## 'data.frame':	2476 obs. of  34 variables:
##  $ Season                 : chr  "2011-2012" "2011-2012" "2011-2012" "2011-2012" ...
##  $ Match.Type             : num  1 1 1 1 1 1 1 1 1 1 ...
##  $ Team                   : chr  "Chelsea" "Bayer Leverkusen" "Genk" "Valencia" ...
##  $ League                 : chr  "Premier League" "Bundesliga" "Other Leagues" "La Liga" ...
##  $ Qualified.o.No         : num  1 1 0 0 0 1 0 1 1 1 ...
##  $ Results                : chr  "Winners" "Round of 16" "Group stage" "Group stage" ...
##  $ Point.of.group.stage   : num  11 10 3 8 9 10 4 11 16 9 ...
##  $ Opponent               : chr  "Bayer Leverkusen" "Chelsea" "Valencia" "Genk" ...
##  $ Opponent.Qualified.o.No: num  1 1 0 0 1 0 1 0 1 1 ...
##  $ Match_location         : chr  "HOME" "AWAY" "HOME" "AWAY" ...
##  $ Result                 : chr  "Win" "Draw" "LOSS" "LOSS" ...
##  $ Goal.Difference        : num  2 2 0 0 1 1 0 0 0 0 ...
##  $ Goals_Scored           : num  2 0 0 0 0 1 1 1 2 2 ...
##  $ Goals_Against          : num  0 2 0 0 1 0 1 1 2 2 ...
##  $ Formulation            : chr  "433" "4231" "442" "4411" ...
##  $ Shots                  : num  23 11 7 22 9 13 23 9 22 6 ...
##  $ Shots-on-Target        : num  12 2 2 4 2 4 6 2 7 3 ...
##  $ Open_Play              : num  18 9 6 14 4 7 18 7 13 3 ...
##  $ Set_Piece              : num  5 2 1 7 5 4 4 2 9 3 ...
##  $ Counter_Attack         : num  0 0 0 1 0 2 1 0 0 0 ...
##  $ Possession             : num  58 42 31 69 52 48 57 43 75 25 ...
##  $ Passes                 : num  565 408 265 589 430 389 555 411 799 264 ...
##  $ Pass_Success           : num  85 72 70 87 80 73 77 73 92 71 ...
##  $ Short_passes           : num  443 336 187 512 319 326 462 340 714 217 ...
##  $ Long_Balls             : num  82 53 59 49 85 45 51 58 55 40 ...
##  $ Crosses                : num  38 16 19 25 22 16 30 7 18 4 ...
##  $ Through_Balls          : num  2 3 0 3 4 2 12 6 12 3 ...
##  $ Dribbles_Won           : num  7 4 8 4 9 12 5 12 7 5 ...
##  $ Aerila_Success         : num  52 48 47 53 37 63 47 53 63 37 ...
##  $ Corners                : num  6 2 5 7 2 3 6 4 11 2 ...
##  $ Offsides               : num  2 1 3 2 4 2 6 4 5 2 ...
##  $ Tackles                : num  21 22 23 17 21 17 41 27 12 22 ...
##  $ Fouls                  : num  17 24 19 18 21 21 13 7 10 11 ...
##  $ Yellow_Cards           : num  2 3 2 1 2 3 2 1 3 2 ...
```



```r
df1 <- df %>% select (League, Shots:Fouls) %>% 
  filter(League != "Other Leagues")
model <- lda(League ~ ., data = df1)
model
```

```
## Call:
## lda(League ~ ., data = df1)
## 
## Prior probabilities of groups:
##     Bundesliga        La Liga        Ligue 1 Premier League        Serie A 
##      0.2132546      0.2552493      0.1384514      0.2375328      0.1555118 
## 
## Group means:
##                   Shots `Shots-on-Target` Open_Play Set_Piece Counter_Attack
## Bundesliga     15.21231          5.676923 11.058462  3.412308      0.5538462
## La Liga        15.18509          5.732648 10.722365  3.735219      0.5192802
## Ligue 1        13.08057          4.715640  9.360190  3.109005      0.4739336
## Premier League 13.41436          5.193370  9.497238  3.157459      0.5193370
## Serie A        13.77215          4.991561  9.784810  3.388186      0.3839662
##                Possession   Passes Pass_Success Short_passes Long_Balls
## Bundesliga       54.72646 572.2492     82.71385     491.0646   59.42462
## La Liga          56.23290 597.2802     84.08740     516.6607   58.79434
## Ligue 1          50.17299 524.7109     82.48341     449.6967   53.58768
## Premier League   52.93204 557.5552     82.91989     480.6685   56.35635
## Serie A          49.26709 508.9747     81.76371     430.0844   58.40084
##                 Crosses Through_Balls Dribbles_Won Aerila_Success  Corners
## Bundesliga     20.36615      2.261538     9.649231       49.44308 5.621538
## La Liga        18.75064      3.087404    11.143959       51.49100 5.807198
## Ligue 1        19.22275      2.203791    11.393365       51.81991 4.971564
## Premier League 17.84807      2.709945    11.988950       54.46409 5.303867
## Serie A        18.62869      2.071730     8.894515       53.15612 5.050633
##                Offsides  Tackles    Fouls
## Bundesliga     2.258462 20.07692 12.70154
## La Liga        2.444730 18.96144 11.26221
## Ligue 1        2.781991 18.84834 12.98104
## Premier League 2.483425 17.50552 12.57459
## Serie A        2.641350 17.68776 12.86498
## 
## Coefficients of linear discriminants:
##                             LD1          LD2         LD3          LD4
## Shots             -0.0142729530 -0.053809757 -0.38062616  0.248981623
## `Shots-on-Target` -0.0454421335 -0.014912141  0.02257113  0.127105375
## Open_Play         -0.0403652644  0.148961115  0.34932086 -0.274194728
## Set_Piece         -0.0443664107  0.060638955  0.23513617 -0.494874749
## Counter_Attack    -0.0892306379  0.015082241  0.66377186 -0.078310808
## Possession        -0.0372285242 -0.026757722  0.01081110  0.031679928
## Passes             0.0331623616  0.012408640  0.05747625 -0.046097174
## Pass_Success       0.0497032869  0.036015958 -0.02062021 -0.110683928
## Short_passes      -0.0364803916 -0.014302600 -0.05588731  0.048274188
## Long_Balls        -0.0493812940 -0.012694814 -0.09394387  0.052295486
## Crosses           -0.0001546827  0.017722109  0.01006828  0.017370890
## Through_Balls     -0.0173021592 -0.141609023 -0.15442324 -0.042546893
## Dribbles_Won       0.0782062073 -0.134142517  0.07406900 -0.002672684
## Aerila_Success     0.0359665949 -0.008221768 -0.02414672  0.019168599
## Corners           -0.0497508607 -0.080095198 -0.08911521  0.127263189
## Offsides           0.1408153053  0.050020657  0.04327705 -0.144006499
## Tackles           -0.0811921209  0.011774017  0.08302617 -0.046271209
## Fouls              0.0365718930  0.041587853  0.05190990  0.126872106
## 
## Proportion of trace:
##    LD1    LD2    LD3    LD4 
## 0.5144 0.2829 0.1351 0.0676
```



```r
DAscores <- predict(model)$x
iris_DAsocres <- cbind(df1, DAscores)
head(iris_DAsocres)
```

```
##           League Shots Shots-on-Target Open_Play Set_Piece Counter_Attack
## 1 Premier League    23              12        18         5              0
## 2     Bundesliga    11               2         9         2              0
## 3        La Liga    22               4        14         7              1
## 4        Ligue 1    13               4         7         4              2
## 5     Bundesliga    23               6        18         4              1
## 6 Premier League     9               2         7         2              0
##   Possession Passes Pass_Success Short_passes Long_Balls Crosses Through_Balls
## 1         58    565           85          443         82      38             2
## 2         42    408           72          336         53      16             3
## 3         69    589           87          512         49      25             3
## 4         48    389           73          326         45      16             2
## 5         57    555           77          462         51      30            12
## 6         43    411           73          340         58       7             6
##   Dribbles_Won Aerila_Success Corners Offsides Tackles Fouls         LD1
## 1            7             52       6        2      21    17 -0.90476092
## 2            4             48       2        1      22    24  0.13641991
## 3            4             53       7        2      17    18 -0.84758193
## 4           12             63       3        2      17    21  1.35638782
## 5            5             47       6        6      41    13 -2.24619934
## 6           12             53       4        4      27     7  0.01505987
##           LD2        LD3        LD4
## 1  1.99079594  0.1096697  0.2337653
## 2  1.65042326  0.6358381  1.3980947
## 3  1.14857824 -0.1534523 -0.1793554
## 4 -0.01777622  1.0495998  1.7491141
## 5  0.79178389  1.8064765 -2.1653626
## 6 -0.97090664 -0.4300028 -1.0893925
```



