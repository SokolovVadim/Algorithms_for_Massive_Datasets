# Algorithms_for_Massive_Datasets

### Algorithms for Massive Datasets Project

## Book recommendation system

After filtering the data, making pairs with MIN_COMMON_USERS = 3:

number of item pairs with common users >= min common users: 1101
sample similarity: [(('0140860428', '0435126024'), (0.9999999999999866, 3)), (('0140860436', '0195813618'), (0.99999999999999, 4)), (('0333580443', '0708982581'), (0.9981310335652164, 10)), (('0679725393', '0708982581'), (0.9999999999999866, 3)), (('1901768945', 'B000EVI8O0'), (0.9999999999999891, 4))]

items with neighbor lists: 508

These values are too low, need to check MSE

users in history: 3582

RMSE: 0.3056909533599352
Coverage: 0.10454545454545454
Predicted test points: 529 / 5060


So we predicted only small part. And we need to fix it.

Set MIN_COMMON_USERS = 2:

```
RMSE: 0.4236984602605913
Coverage: 0.16462450592885375
Predicted test points: 833 / 5060
```

Got RMSE worse, because now it's fair larger portion of data, and improved coverage. Still small.

I took 20% of the data

```

```

rows: 85603

users: 9795

books: 13660

DataFrame[user_id: string, book_id: string, rating: double, title: string]

+----------+-----+

|   book_id|count|

+----------+-----+

|0141804459|  178|

|B000GQG7D2|  171|

|B000C1X8JC|  168|

|B000NDSX6C|  168|

|0786135034|  167|

|B000F6H01Q|  165|

|B000ILIJE0|  164|

|B000Q032UY|  164|

|B000GQG5MA|  164|

|B000GDLGSG|  164|

|1844560333|  161|

|0451513967|  159|

|B000NWQXBA|  159|

|0435126075|  158|

|1901768945|  157|

|8188280046|  157|

|B000EVI8O0|  155|

|1566190932|  150|

|B000H9R1Q0|  148|

|B000PC54NG|  145|

+----------+-----+

only showing top 20 rows

+--------------+-----+

|       user_id|count|

+--------------+-----+

|A1D2C0WDCSHUWZ|  568|

|   AFVQZQ8PW0L|  290|

|A14OJS0VWMOSWO|  266|

|A20EEWWSFMZ1PN|  212|

|A1X8VZWTOG8IS6|  211|

| AHD101501WCN1|  184|

|A1K1JW1C5CUSUZ|  179|

|A1EKTLUL24HDG8|  145|

|A1G37DFO8MQW0M|  143|

|A1N1YEMTI9DJ86|  139|

|A3QVAKVRAH657N|  136|

| AHXAPVSHPJ6OJ|  132|

|A2F6N60Z96CAJI|  131|

|A1L43KWWR05PCS|  129|

|A1T17LMQABMBN5|  117|

|A319KYEIAZ3SON|  113|

|A3M174IC0VXOS2|  111|

| AJQ1S39GZBKUG|  109|

|A3LKWMM12AF0PU|  108|

|A28WJUJF6D2ULA|  107|

+--------------+-----+

only showing top 20 rows

+----------+-----------------------------------------------------------------------------------------+---+-----------------+

|book_id   |title                                                                                    |n  |average_rating   |

+----------+-----------------------------------------------------------------------------------------+---+-----------------+

|B000OZRZ90|Milton's Paradise Lost                                                                   |12 |5.0              |

|1854596209|Hamlet (The Shakespeare Folios)                                                          |11 |5.0              |

|B000JWHH32|The Jungle Book (Companion Library)                                                      |11 |5.0              |

|B0007G64NO|The Screwtape letters & Screwtape proposes a toast (Time reading program special edition)|10 |5.0              |

|B0007J8XJ4|The varieties of religious experience: A study in human nature (Gifford lectures)        |10 |5.0              |

|0877549249|Hamlet (Mod Crit Interpret) (Bloom's Modern Critical Interpretations)                    |16 |4.9375           |

|B00088ZN1A|I, Claudius (Armed Services edition)                                                     |15 |4.933333333333334|

|B000KOYWE6|The Heart of the Matter                                                                  |14 |4.928571428571429|

|B0007FJEAK|Brideshead revisited: The sacred and profane memories of Captain Charles Ryder           |13 |4.923076923076923|

|B000JMKVF8|Blood and Thunder: An Epic of the American West                                          |12 |4.916666666666667|

|B00007FYQV|Red Storm Rising                                                                         |12 |4.916666666666667|

|B000MUCEDY|little house in the big woods                                                            |12 |4.916666666666667|

|B0006EAC1C|Our man in Havana (Heron books)                                                          |12 |4.916666666666667|

|B000H0JB7Q|The Heart of the Matter                                                                  |12 |4.916666666666667|

|B000I1VJLA|The Lord of the Rings Box Set                                                            |89 |4.910112359550562|

|B0006DJX7W|Sources and extent of groundwater contamination (AG)                                     |11 |4.909090909090909|

|B0007EW5L6|Kon-tiki: Across the Pacific by raft (A Keith Jennison book)                             |11 |4.909090909090909|

|B000KO327E|All Creatures Great and Small                                                            |11 |4.909090909090909|

|B0007DRIT6|The richest man in Babylon                                                               |11 |4.909090909090909|

|B000L2RXCK|All Creatures Great and Small                                                            |11 |4.909090909090909|

+----------+-----------------------------------------------------------------------------------------+---+-----------------+

only showing top 20 rows

train: 68323 test: 17280

number of item pairs with common users >= min common users: 22493

sample similarity: [(('1420926810', '1570020981'), (0.9374252720097401, 2)), (('B00069X44Y', 'B00086KNY4'),(0.9999999999999798, 2)), (('0792717848', 'B00005QTHG'),(0.8531145054348057, 3)), (('0520050894', 'B000GTEU8I'), (0.9999999999999908, 5)), (('B000JQXNSQ', 'B000NNOTXI'), (0.890870806374732, 3))]

items with neighbor lists: 4647

users in history: 9725

RMSE: 0.4221545207391567

Coverage: 0.37471064814814814

Predicted test points: 6475 / 17280


So, the coverage is 37%, went up from 16%, good


```
Top rated by user:
5.0  0020554303  -  House of Mirth
5.0  0060765461  -  The Lion, the Witch and the Wardrobe Movie Tie-in Edition (The Chronicles of Narnia)
5.0  0060765461  -  The Lion, the Witch and the Wardrobe Movie Tie-in Edition (The Chronicles of Narnia)
5.0  0075543893  -  Little Women
5.0  0140351310  -  Jane Eyre: Complete and Unabridged (Puffin Classics)
5.0  0140351310  -  Jane Eyre: Complete and Unabridged (Puffin Classics)
5.0  0140351310  -  Jane Eyre: Complete and Unabridged (Puffin Classics)
5.0  0140860428  -  Jane Eyre (Penguin Classics)
5.0  0140860428  -  Jane Eyre (Penguin Classics)
5.0  0140860436  -  The Age of Innocence (Classic, 20th-Century, Audio)
```

Mean centering

```
5.000 (from 2 neigh)  1593357087  -  Northern Lights
5.000 (from 2 neigh)  078625033X  -  Light in Shadow: A Whispering Springs Novel
5.000 (from 2 neigh)  0195810147  -  Journey to the Centre of the Earth (Oxford University English Readers)
5.000 (from 2 neigh)  B000JWW2G4  -  The Invisible Man
4.530 (from 2 neigh)  B0002ST9SY  -  Deception Point
4.504 (from 2 neigh)  B000GLI9HY  -  Shutter Island
4.500 (from 2 neigh)  B000I3NFKG  -  THE CATCHER IN THE RYE
```



what we seeing is a a real property of the dataset and a predictor :

* Many users (and many book editions) have  many 5 star tatings , so the weighted-average predictor will often output exactly 5.0 .
* Mean-centering helps when users have different “generosity”, but if a user’s ratings are still mostly 5, the centered deviations are 0, so we still land near the user mean (=5).
* For our second user we see non-5 predictions (4.53, 4.50, …), which means the centered model is working.


If only a few neighbor contributions exist, pull the prediction toward the user mean
