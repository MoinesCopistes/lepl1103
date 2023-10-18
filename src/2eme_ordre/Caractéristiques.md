# Méthode des caractéristiques

En vrai on met cette méthode dans le livre par soucis de "rigueur" mais en vrai vous l'utiliserez probablement jamais (et ça sert à R).

## Problème de Cauchy

On a $\phi(s)$ et $\frac{\partial \phi}{\partial n} (s)$ donné le long de $\Gamma \equiv (x(s), y(s))$ avec $n(s)$ la normale à la courbe. Si à partir de ces données on peut trouver trouver $\phi(x,y)$ avec le point $(x,y)$ dans la proximité de $\Gamma$ on pourra répéter la manoeuvre afin de trouver la valeur suivante et ainsi de suite. *C'est le problème de Cauchy.*

Par des jeux de changements de variables on peut obtenir de gradient de $\phi$ le long de $\Gamma$ dans le repère $(x,y)$ soit $(\frac{\partial \phi}{\partial x}(s), \frac{\partial \phi}{\partial y}(s))$  et afin d'obtenir notre système on réécrit la dérivée en $s$ du gradient :
$$
\frac{\partial}{\partial x} ( \frac{ \partial \phi }{ \partial x }) \frac{dx}{ds} +
\frac{\partial}{\partial x} ( \frac{ \partial \phi }{ \partial x }) \frac{dy}{ds} =
\frac{\partial ^ 2 \phi}{\partial x ^ 2} {\color{ORANGE} \frac{dx}{ds}} +
\frac{\partial ^ 2 \phi}{\partial x \partial y} {\color{GREEN} \frac{dy}{ds}} =
\frac{d}{ds} \frac{\partial \phi}{\partial x}
\tag{1}
$$
$$
\frac{\partial}{\partial x} ( \frac{ \partial \phi }{ \partial y }) \frac{dx}{ds} +
\frac{\partial}{\partial x} ( \frac{ \partial \phi }{ \partial y }) \frac{dy}{ds} =
\frac{\partial ^ 2 \phi}{\partial y \partial x} {\color{RED}\frac{dx}{ds}} +
\frac{\partial ^ 2 \phi}{\partial y ^ 2} {\color{PINK}\frac{dy}{ds}} =
\frac{d}{ds} \frac{\partial \phi}{\partial y} 
\tag{2}
$$
Et les plus assidus auront remarqué que ça nous arrange fort pour résoudre notre [EDP](./Généralités.md) :
$$
\begin{bmatrix}
A & B & C \\
{\color{ORANGE}\frac{dx}{ds}} & {\color{GREEN}\frac{dy}{ds}} & 0 \\
0 & {\color{RED} \frac{dx}{ds}} & {\color{PINK}\frac{dy}{ds}}
\end{bmatrix}
\begin{bmatrix}
\frac{\partial ^ 2 \phi}{\partial x ^ 2} \\
\frac{\partial ^ 2 \phi}{\partial x \partial y} \\
\frac{\partial ^ 2 \phi}{\partial y ^ 2}
\end{bmatrix}
=
\begin{bmatrix}
R \\
\frac{d}{ds} \frac{\partial \phi}{\partial x}  \\
\frac{d}{ds} \frac{\partial \phi}{\partial y} 
\end{bmatrix}
$$
Tant que le determinant n'est pas $0$ le système est solvable $\Rightarrow$ On peut trouver $\frac{\partial \phi}{dx}$, $\frac{\partial \phi}{\partial y}$ et $\phi$ dans l'entourage de $\Gamma$ $\Rightarrow$ Le problème de Cauchy est bien posé
```admonish note
Allez voir le cours pour la partie calculatoire (et inutile en mon opinion).
```

## Résolution : 

On raisonne de la même façon que pour une EDP du premier ordre : on considère des directions $(dx, dy)$ non parallèles à $\Gamma$. On notera aussi $\frac{\partial \phi}{\partial x} = u$ et $\frac{\partial \phi}{\partial y} = v$ (C'est plus subtile que ça mais on laisse ça pour le [bas de la page](#bas-de-la-page-)

On réécrit notre gradient dérivé en s *(les équations (1) et (2))*:
$$
\frac{\partial u}{\partial x} dx +
\frac{\partial v}{\partial x} dy =
du
\tag{3}
$$
$$
\frac{\partial v}{\partial x} dx +
\frac{\partial v}{\partial x} dy =
dv
\tag{4}
$$
Et on réécrit notre système :
$$
\begin{bmatrix}
A & B & C \\
dx & dy & 0 \\
0 & dx & dy
\end{bmatrix}
\begin{bmatrix}
\frac{\partial u}{\partial x} \\
\frac{\partial u}{\partial y} \small{ou} \frac{\partial v}{\partial x} \\
\frac{\partial v}{\partial y}
\end{bmatrix}
=
\begin{bmatrix}
R \\
du\\
dv 
\end{bmatrix}
$$
Les directions caractéristiques sont telles que le déterminant de la matrice s'annule. Si l'équation du déterminant nul donne **deux racines réelles distinctes** l'équation est alors dite ***Hyperbolique***, si il n'y a **qu'une racine** elle est alors dite ***Parabolique*** et enfin si les racines sont ***complexes*** elle est ***Elliptique***.

Si elle est hyperbolique, on procède de la même façon que pour une EDP du premier ordre, on réduit celle-ci a une EDO par caractéristique en remplaçant une colonne de la matrice par le membre de droite de l'équation et on trouve quand le déterminant est nul.

Pour trouver la solution c'est assez calculatoire *(d'ailleurs mm dans le correctif ils ont la flemme de le faire jusqu'au bout mdr)*, 2 caractéristiques qui se croisent donnent les données pour un système qui donne au bout du compte $\phi$.

### Bas de la page :

On n'as pas noté $\frac{\partial \phi}{\partial x} = u$ et $\frac{\partial \phi}{\partial y} = v$ juste pour faire plus concis, $u$ et $v$ peuvent être définis comme bon vous semble tant que ça vous aide à résoudre le calcul *(mais normalement c'est donné)*.
Par exemple, dans l'APE 3 2023 exercice 1, $u = c \frac{\partial \phi}{\partial x}$ et $v = \frac{\partial \phi}{\partial y}$. 
