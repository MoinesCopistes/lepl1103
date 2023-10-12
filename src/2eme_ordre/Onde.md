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

$t = \frac{1}{2}(\eta - \xi)$

Chaque point $(x,t)$ peut donc être associé a un point $(\eta, \xi)$.

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
$$\phi(\xi, \eta) = f_1(\xi) + f_2(\eta) $$
$$\boxed{ \phi(x, t) = f_1(x-ct) + f_2(x+ct) }$$


```admonish warning title="Important"

$f_1$ et $f_2$ apparaissent avec les constantes d'intégration (en effet, intégrer 0 en $\eta$ donne une constante **par rapport à** $\eta$ qu'on appelle $c_1$ **mais qui pouvant dépendre** de $\xi$)

```

Maintenant que nous connaissons la forme de la solution, pourquoi ne pas essayer de trouver cette solution !

Comme c'est le cas pour toutes les EDP du deuxième ordre, il nous faut 2 conditions initiales afin de pouvoir trouver une solution. 

Explorons différent cas !

### Le cas le plus simple

Prenons comme courbe $\Gamma$ définie par $x(s) = s$ et $ct(s) = 0$ (autrement dit, l'axe $Ox$ ) 

Et prenons comme conditions initiales :

$$ \phi(s, 0) = f(s)$$
$$ \frac{\partial \phi}{\partial t}(s,0) = 0 $$

Connaissant la forme de la solution: $\phi(x,y) = f_1(x-ct) + f_2(x+ct)$, on sait que:

$$\phi(s,0) = f(s) = f_1(x) + f_2(x)$$

Et comme nous le dit la première condition initiale:

$$\frac{\partial \phi}{\partial t}(s,0) = 0$$
$$f_1'(\xi) {\color{#e74c3c} \frac{\partial \xi}{\partial t}} + f_2'(\eta) {\color{#8e44ad} \frac{\partial \eta}{\partial t} }= 0$$
$${\color{#e74c3c} -c}f_1'(\xi) + f_2'(\eta){\color{#8e44ad} c} = 0$$
$$f_1' = f_2'$$

Et selon le théorème fondamental de l'analyse:

$$f_1 = f_2 + C$$

On peut donc conclure que $f_1$ est égal à $f_2$ a une constante près. On peut substituer $f_1$ par $f_2 + C$ dans l'expression de la solution pour écrire:

$$\phi(x,0) = f(x) = f_2(x) + f_2(x) + C$$
$$f_2(x) = \frac{f(x) - C}{2}$$

et en suivant le même raisonnement dans l'autre sens:

$$f_1(x) = \frac{f(x) + C}{2}$$

Et que donc:

$$\phi(x, t) = \frac{1}{2}(f_1(x - ct) + f_2(x+ ct)$$

```admonish warning title="Important"

Cela peut paraitre contre-intuitif de dire que si on connait $\phi(x, 0)$ on connait $\phi(x, t)$ mais étant donné que $f_1$ et $f_2$ sont des fonctions avec un paramètre $x \pm ct$, peu importe le t c'est comme si on avait un autre x en t = 0

Par exemple, prenons $c = 1$, $t=0$, $x=2$ avec $f_1(2) = 5$

Et bien je connaitrai $f_1$ pour $c=1$, $t=2$, $x=0$ car $f_1(0 + 2) = f_1(2) = 5$ )  



 
```