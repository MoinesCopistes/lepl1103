# Équation d'onde

Avant de commencer a en parler, commençons par définir l'équation d'onde. 

La voici, dans la plus classique de ses formes:

$$ c² \frac{\partial² \phi}{\partial x²} - \frac{\partial²\phi}{\partial t²} = 0$$


## Méthodes des caractéristiques

//TODO

## Méthode du changement de variable

Il existe, pour cette EDO en tout cas, un changement de variable très malin permettant de la résoudre assez directement.

$$ \xi = x - ct $$
$$ \eta = x + ct $$

Prenons donc $\xi$ et $\eta$ comme variables.

La fonction $\phi(x,t)$ deviendra donc $\phi(\xi, \eta$

```admonish note

Malgré ce changement de variables, $\phi$ reste défini pour tout l'espace. On sait que 

$x = \frac{1}{2}(\eta + \xi)$

$y = \frac{1}{2}(\eta - \xi)$

Chaque point $(x,y)$ peut donc être associé a un point $(\eta, \xi)$.

```

Suite a ce changement de variable, nous pouvons également calculer les opérateurs différenciels $\frac{\partial}{\partial x}$ et $\frac{\partial}{\partial t}$ 
vis a vis de ces variables. (En utilisant la **règle de la chaine**)

$$\frac{\partial}{\partial x} = \frac{\partial}{\partial \xi} \frac{\partial \xi}{\partial x} + \frac{\partial}{\partial \eta} \frac{\partial \eta}{\partial x}$$

$$\frac{\partial}{\partial t} = \frac{\partial}{\partial \xi} \frac{\partial \xi}{\partial t} + \frac{\partial}{\partial \eta} \frac{\partial \eta}{\partial t}$$

Et comme nous connaissons l'expression de $\xi$ et $\eta$, nous connaissons également leur dérivées. 
Ce qui permet d'écrire plus simplement (en remplaçant les dérivées connues par leur valeur):

$$\frac{\partial}{\partial x} = \frac{\partial}{\partial \xi} + \frac{\partial}{\partial \eta}$$

$$\frac{\partial}{\partial t} =  c \frac{\partial}{\partial \eta} -c \frac{\partial}{\partial \xi} $$

Il est également possible de calculer les opérateurs de dérivée seconde en mettant chacune des expressions au carré:

$$\color{#e67e22} \frac{\partial ²}{\partial x²} = \frac{\partial²}{\partial \xi²} + 2\frac{\partial}{\partial \xi}\frac{\partial}{\partial \eta} + \frac{\partial²}{\partial \eta²}$$

$$\color{#16a085} \frac{\partial ²}{\partial t²} = c²(\frac{\partial²}{\partial \xi²} - 2\frac{\partial}{\partial \xi\partial \eta} + \frac{\partial²}{\partial \eta²})$$


Maintenant que nous avons fait tout ce travail fastidieu, on peut enfin remplacer tout cela dans l'équation d'onde:

$$ c² \frac{\partial² \phi}{\partial x²} - \frac{\partial²\phi}{\partial t²} = 0$$

$$c²({\color{#e67e22} \frac{\partial²}{\partial \xi²} + 2\frac{\partial}{\partial \xi\partial \eta} + \frac{\partial²}{\partial \eta²}}) - {\color{#16a085} c²(\frac{\partial²}{\partial \xi²} - 2\frac{\partial}{\partial \xi\partial \eta} + \frac{\partial²}{\partial \eta²})} = 0$$

Ce qui équivaut après simplification a une fonction d'onde bien plus simple:

$$4c²\frac{\partial}{\partial \xi\partial \eta} = 0$$

Ce qui mène donc a la conclusion que :

$$\frac{\partial}{\partial \xi \partial\eta} = 0$$

Il est donc possible de connaitre la forme de $\phi(\xi, \eta)$ en intégrant cette équation:

$$\int d\eta \int \frac{\partial}{\partial \xi \partial \eta} d\xi= \int d\xi \int 0 d\eta$$
$$\phi(\xi, \eta) = \int c_1(\xi) d\xi $$
$$\boxed{ \phi(\xi, \eta) = f_1(\xi) + f_2(\eta) }$$


```admonish warning title="Important"

$f_1$ et $f_2$ apparaissent avec les constantes d'intégration (en effet, intégrer 0 en $\eta$ donne une constante **par rapport à** $\eta$ qu'on appelle $c_1$ **mais qui pouvant dépendre** de $\xi$)

```




