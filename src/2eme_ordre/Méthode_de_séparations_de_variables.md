# Méthode de séparation des variables

La méthode de séparation de variables est encore une façon de transformer nos problèmes aux dérivées partielles en un système plus simple d'EDOs (Thème récurent au cours du livre vous l'aurez remarqué).

Afin d'expliquer cette méthode de résolution intéressons nous au cas vu au cours : L'équation de Laplace.
$$
\nabla^2u = 0 \Leftrightarrow \frac{\partial^2 u}{\partial x^2} + \frac{\partial^2u}{\partial y^2} = 0 \quad(dans\space notre\space cas) 
$$
## Les conditions limites

Les conditions initiales peuvent avoir plusieurs formes :
- Dirichlet $\rightarrow$ $u$ est donné sur la limite de la fonction
- Neumann $\rightarrow$ $\frac{\partial u}{\partial n}$ est donné sur la limite de la fonction ($n$ étant une des variables de $u$)
- Robin $\rightarrow$ $\frac{\partial u}{\partial n} + f(x, y, ...) \cdot u$ est donné sur la limite de la fonction 
Ici notées en ordre croissant de la difficulté des calculs qui vont suivre afin de résoudre l'EDP

## La séparation de variables

Le principe est simple, on suppose, de façon totalement arbitraire et injustifiée, que $u$ est une équation sous la forme : 
$$
u = X(x)\cdot Y(y)
$$
A partir de cette assomption nous pouvons formuler un raisonnement simple, on commence par remplacer le terme $u$ dans notre équation initiale :
$$
\frac{\partial^2 u}{\partial x^2} + \frac{\partial^2u}{\partial y^2} = 0 
$$
$$
\Leftrightarrow 
\frac{\partial^2 X(x)}{\partial x^2}Y(y) + \frac{\partial^2 Y}{\partial y^2} X(x) = 
X''(x)Y(y) + Y''(y)X(x) = 0
$$
$$\Leftrightarrow 
\frac{X''(x)}{X(x)} = \frac{-Y''(y)}{Y(y)}$$

Ici on se rends compte que le membre de droite et le membre de gauche dépendent tout deux de variables différentes donc afin qu'ils soient égaux il faut qu'ils soient chacun égaux à une même constante :
$$
\frac{X''(x)}{X(x)} = \frac{-Y''(y)}{Y(y)} = \pm k^2
$$
```admonish note
Ladite constante est notée $\pm$ afin qu'elle soit réele et elle est au carré afin que la réponse finale soit plus jolie
```

A partir d'ici il faut voir les 3 cas possibles ($-k^2, k^2, k^2 = 0$) en choisissant ceux qui permettent une solution non triviale en fonctions des conditions limites.