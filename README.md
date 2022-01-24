# Python : listes, tuples et tableaux

Les **listes**, les **tuples** et les **tableaux** servent à stocker plusieurs items dans une seule variable

## Les listes

Pour créer une liste, on utilise des **crochets**

Une liste peut stocker différents types de données (string, int, bool...)

> NB : On peut afficher la longueur d'une liste grâce à la méthode `len()`


```python
ma_liste = ["un", "deux", "trois"]
print(ma_liste)

print(len(ma_liste))
```

    ['un', 'deux', 'trois']
    3


Les listes :
- sont **ordonnées**
- autorisent **plusieurs fois une même valeur**
- sont **modifiables**

On peut donc modifier, ajouter ou supprimer des items à une liste   

> NB : Si on ajoute un nouvel élément à une liste avec la méthode `append()`, il sera placé à la fin 


```python
ma_liste.append("quatre")
print(ma_liste)
```

    ['un', 'deux', 'trois', 'quatre']



```python
ma_liste.remove("deux")
print(ma_liste)
```

    ['un', 'trois', 'quatre']



```python
ma_liste[0] = "1"
print(ma_liste)
```

    ['1', 'trois', 'quatre']


## Les tuples

Pour créer un tuple, on utilise des **parenthèses**

Un tuple peut stocker différents types de données (string, int, bool...)

> NB : Comme pour les listes, on peut afficher la longueur d'un tuple grâce à la méthode `len()`


```python
mon_tuple = ("un", "deux", "trois")
print(mon_tuple)

print(len(mon_tuple))
```

    ('un', 'deux', 'trois')
    3


Les tuples :
- sont **ordonnés**
- autorisent **plusieurs fois la même valeur**
- **ne sont pas modifiables**

On ne peut donc pas modifier, ajouter ni supprimer d'items à un tuple

Si l'on cherche à modifier la première valeur de notre tuple, on obtient alors une *erreur* :


```python
mon_tuple[0] = "un"
print(mon_tuple)
```


    ---------------------------------------------------------------------------

    TypeError                                 Traceback (most recent call last)

    ~\AppData\Local\Temp/ipykernel_17528/1610019807.py in <module>
    ----> 1 mon_tuple[0] = "un"
          2 print(mon_tuple)


    TypeError: 'tuple' object does not support item assignment


## Les tableaux

En python, pour utiliser des tableaux, il faut importer un **module** : comme `array` ou `numpy`

> NB : Les tableaux du module `array` n'autorisent pas différents types de données pour un même tableau et il faut préciser le type, contrairement au module `numpy`


```python
import array

mon_tableau = array.array("i", [1, 5, 6, 9, 10])  # le "i" indique que les éléments sont des entiers
print(type(mon_tableau), mon_tableau)
```

    <class 'array.array'> array('i', [1, 5, 6, 9, 10])



```python
import numpy

mon_tableau2 = numpy.array(["un", "deux", 3, True])
print(type(mon_tableau2), mon_tableau2)
```

    <class 'numpy.ndarray'> ['un' 'deux' '3' 'True']


Tout comme les listes, les tableaux :
- sont **ordonnés**
- autorisent **plusieurs fois la même valeur**
- sont **modifiables**

**Cependant**, 

- Les listes sont intégrées à Python contrairement aux tableaux
- On peut effectuer des opérations mathématiques sur l'ensemble des éléments d'un tableau mais pas d'une liste
- Les tableaux sont plus efficaces pour stocker un grand nombre de données, ils prennent moins de mémoire que les listes
- Les tableaux sont généralement plus rapides


```python
mon_tableau3 = numpy.array([4, 12, 29, 56, 85])

div = mon_tableau3 / 4
print(div)
```

    [ 1.    3.    7.25 14.   21.25]



```python
ma_liste2 = [4, 12, 29, 56, 85]

div = ma_liste2 / 4
print(div)
```


    ---------------------------------------------------------------------------

    TypeError                                 Traceback (most recent call last)

    ~\AppData\Local\Temp/ipykernel_17528/2924357583.py in <module>
          1 ma_liste2 = [4, 12, 29, 56, 85]
          2 
    ----> 3 div = ma_liste2 / 4
          4 print(div)


    TypeError: unsupported operand type(s) for /: 'list' and 'int'

