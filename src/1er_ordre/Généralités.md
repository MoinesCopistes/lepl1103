# EDP du premier ordre

L'EDP ***quasi-linéaire*** la plus générale à 2 variables indépendantes s'écrit :
$$
 P \frac{\partial u}{\partial x} + Q \frac{\partial u}{\partial y} =R
$$
avec $P,Q,R$ qui sont fonctions de $x,y,u$

L'EDP ***linéaire*** la plus générale à 2 variables indépendantes s'écrit :
$$
 P \frac{\partial u}{\partial x} + Q \frac{\partial u}{\partial y} +Gu=F
$$
avec $P,Q,G,F$ qui sont fonctions de $x,y$ (On peut noter $R=F-Gu$). 
Elle sont homogènes quand $F=0$ et quand $R=0$.

Point important à savoir, toutes les EDP du premier ordre sont dites *hyperboliques* donc elles ont toutes des caractéristiques.

## Equation de transport 

L'équation de transport est une EDP spécifique sous la forme :
$$
c\frac{\partial u}{\partial x}+\frac{\partial u}{\partial t} = 0
$$
Avec $c$ qui peut varier en fonction de $x$ ou $t$.

Cette EDP a une particularité spécifique très intéressante qui est que l'intégrale de la fonction en $x$ est conservée pour tout $t$, d'où le nom d'équation de transport. En effet, il y a 2 cas :

- $c$ est constant :

$\quad$ La fonction $u$ a l'exacte même forme en tout t elle vas juste se déplacer dans l'éspace. 
- $c$ est fonction de x ou de $t$ : 

$\quad$ La fonction u sera déformée mais en gardant toujours cette propriété $\int\frac{\partial u}{\partial x}dt = 0$ 