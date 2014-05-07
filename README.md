paleobiologyDB
==============

## Exploring the new R API to the paleobiologyDB.

Preliminary loading of required packages.  


```r
library(devtools)

if (!require(paleobioDB)) {
    install_github("ropensci/paleobioDB")
    library(paleobioDB)
}
```


Now we get all PaleobioDB occurrences for Quaternary bovids.  


```r
bovidae <- pbdb_occurrences(limit = "all", base_name = "bovidae", interval = "Quaternary", 
    show = c("coords", "phylo", "ident"))
head(bovidae)
```

```
##        oid typ   cid                      tna rnk    tid
## 1:1 138836 occ 11803              Gazella sp.   5  42774
## 1:2 138837 occ 11803        Dama mesopotamica   3 149388
## 1:3 150048 occ 13293          Bubalus bubalus   3  42755
## 1:4 150049 occ 13293   Megalovis guangxiensis   3  42796
## 1:5 150050 occ 13293 Capricornis sumatraensis   3 149670
## 1:6 150894 occ 13456                  Bos sp.   5  42753
##                    oei   eag    lag   rid    lng   lat     fml   fmn
## 1:1   Late Pleistocene 0.126 0.0117 10604  35.05 32.72 Bovidae 42742
## 1:2   Late Pleistocene 0.126 0.0117 10604  35.05 32.72 Bovidae 42742
## 1:3 Middle Pleistocene 0.781 0.0117  4412 111.57 22.77 Bovidae 42742
## 1:4 Middle Pleistocene 0.781 0.0117  4412 111.57 22.77 Bovidae 42742
## 1:5 Middle Pleistocene 0.781 0.0117  4412 111.57 22.77 Bovidae 42742
## 1:6   Late Pleistocene 0.126 0.0000  6077  87.00 23.50 Bovidae 42742
##              odn   odl      cll   cln      phl   phn         idt
## 1:1 Artiodactyla 87634 Mammalia 36651 Chordata 33815     Gazella
## 1:2 Artiodactyla 87634 Mammalia 36651 Chordata 33815        Dama
## 1:3 Artiodactyla 87634 Mammalia 36651 Chordata 33815     Bubalus
## 1:4 Artiodactyla 87634 Mammalia 36651 Chordata 33815   Megalovis
## 1:5 Artiodactyla 87634 Mammalia 36651 Chordata 33815 Capricornis
## 1:6 Artiodactyla 87634 Mammalia 36651 Chordata 33815         Bos
##              ids                          mna mra              oli  rss
## 1:1          sp.                         <NA>  NA             <NA> <NA>
## 1:2 mesopotamica Antilope (Dama) mesopotamica  NA             <NA> <NA>
## 1:3      bubalus                      Bubalus   5 Late Pleistocene <NA>
## 1:4 guangxiensis                    Megalovis   5 Late Pleistocene <NA>
## 1:5 sumatraensis                         <NA>  NA Late Pleistocene <NA>
## 1:6          sp.                         <NA>  NA         Holocene <NA>
##      rst eid  idf
## 1:1 <NA>  NA <NA>
## 1:2 <NA>  NA <NA>
## 1:3 <NA>  NA <NA>
## 1:4 <NA>  NA <NA>
## 1:5 <NA>  NA <NA>
## 1:6 <NA>  NA <NA>
```


Plot the number of subtaxa in the data set 


```r
pbdb_subtaxa(bovidae, do.plot = TRUE)
```

![plot of chunk plotsubtaxa](figure/plotsubtaxa.png) 

```
##   species genera families orders classes phyla
## 1     164     86        1      1       1     1
```


