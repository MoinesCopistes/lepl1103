# Méthode des caractéristique


La méthode des caractéristiques consiste à traduire notre EDP en une EDO plus facile à résoudre
## Problème de Cauchy

Si on a $\large u$ paramétrisé par la courbe $\large \Gamma \equiv(x(s),y(s))$, donc $\large u(x(s),y(s))=u(s)$ est une fonction donnée. Alors on peut obtenir $\large u$ dans le voisinage de $\large \Gamma$ et donc petit-à-petit construire la solution complète $\large u$ (qui est encore une fois une surface). *C'est le problème de Cauchy.*

Puisque $\large u(s)$ est connue le long de $\large \Gamma$, $\large \frac{\text{d}u}{\text{d}s}$ est aussi connu le long de $\large \Gamma$ et on peut écrire :
$$
\large \frac{\partial u}{\partial x} \frac{\text{d}x}{\text{d}s} + \frac{\partial u}{\partial y} \frac{\text{d}y}{\text{d}s}=\frac{\text{d}u}{\text{d}s}
$$
Qu'on peut mettre ensemble avec l'EDP originale pour former le système :
$$
\large \begin{bmatrix}
P & Q \\
\frac{\text{d}x}{\text{d}s} & \frac{\text{d}y}{\text{d}s} \\ 
\end{bmatrix}
\begin{bmatrix} \frac{\partial u}{\partial x} \\ \frac{\partial u}{\partial y} \\ \end{bmatrix}
= \begin{bmatrix} R \\ \frac{\text{d}u}{\text{d}s} \\ \end{bmatrix}

$$
Si le déterminant est $\large \neq 0$, on peut résoudre ce système et donc obtenir (grâce à la règle de Cramer) $\large \frac{\partial u}{\partial x}$ et $\large \frac{\partial u}{\partial y}$ le long de $\large \Gamma$. 
$$
\large \frac{\partial u}{\partial x}=
\frac{\begin{vmatrix}
R & Q \\
\frac{\text{d}u}{\text{d}s} & \frac{\text{d}y}{\text{d}s} \\ 
\end{vmatrix}}{\begin{vmatrix}
P & Q \\
\frac{\text{d}x}{\text{d}s} & \frac{\text{d}y}{\text{d}s} \\ 
\end{vmatrix}} \quad\quad\text{et} \quad\quad
\frac{\partial u}{\partial y}=
\frac{\begin{vmatrix}
P & R \\
\frac{\text{d}x}{\text{d}s} & \frac{\text{d}u}{\text{d}s} \\ 
\end{vmatrix}}{\begin{vmatrix}
P & Q \\
\frac{\text{d}x}{\text{d}s} & \frac{\text{d}y}{\text{d}s} \\ 
\end{vmatrix}}
$$
Ce qui nous permet de trouver $\large u$ proche de $\large \Gamma$ :
$$
\large u(x+\text{d}x, y+\text{d}y)=u(x,y)+\text{d}x\frac{\partial u}{\partial x}(x,y)+\text{d}y\frac{\partial u}{\partial y}(x,y)
$$
Ceci correspond à la formule du plan tangent à une surface pour tout point infiniment proche de la courbe $\large \Gamma$, cette relation est donc exacte parce qu'elle ne concerne pas des points à une distance finie de la courbe. *En répétant la procédure, on peut donc (du moins en principe) se propager petit pas par petit pas et obtenir la solution de l’EDP de plus en plus loin de la courbe $\large \Gamma$*. Mais pas dingue comme méthode. On dit que le problème de Cauchy est bien posé si la courbe $\large \Gamma$ est telle que le déterminant $\large \neq 0$ pour tout ses points.
## Résolution :

On considère maintenant un problème bien posé. Pour une direction $\large (\text{d}x,\text{d}y)$ non parallèle à $\large \Gamma$, la variation $\large \text{d}u$ qui y correspond est liée à $\large \text{d}x$ et $\large \text{d}y$ par :
$$
\large \frac{\partial u}{\partial x}\text{d}x+\frac{\partial u}{\partial y}\text{d}y=\text{d}u
$$
On peut donc, de nouveau former, avec l'EDP elle-même, le système :
$$
\large \begin{bmatrix}
P & Q \\
\text{d}x & \text{d}y \\ 
\end{bmatrix}
\begin{bmatrix} \frac{\partial u}{\partial x} \\ \frac{\partial u}{\partial y} \\ \end{bmatrix}
= \begin{bmatrix} R \\ \text{d}u \\ \end{bmatrix}
$$
Dont la solution est :
$$
\large \frac{\partial u}{\partial x}=
\frac{\begin{vmatrix}
R & Q \\
\text{d}u & \text{d}y \\ 
\end{vmatrix}}{\begin{vmatrix}
P & Q \\
\text{d}x & \text{d}y \\ 
\end{vmatrix}} \quad\quad\text{et} \quad\quad
\frac{\partial u}{\partial y}=
\frac{\begin{vmatrix}
P & R \\
\text{d}x & \text{d}u \\ 
\end{vmatrix}}{\begin{vmatrix}
P & Q \\
\text{d}x & \text{d}y \\ 
\end{vmatrix}}
$$
Qui est inutile car $\large \text{d}u$ n'est pas connu. Mais il existe un direction locale $\large (\text{d}x,\text{d}y)$ telle que le déterminant du dénominateur $\large =0$. Elle est donnée par :
$$
\large P\text{d}y=Q\text{d}x
$$
C'est la ***direction caractéristique***. Ceci nous donne une EDO ($\large \neq$ EDP) d'ordre 1 qui, lorsque intégrée en partant de $\large (x(s),y(s))$, déterminera la ***courbe caractéristique***. Même si on a une division par $\large 0$ on peut toujours trouver une solution si le numérateur est nul également, ce qui donne :
$$
\large P\, \text{d}u=R\,\text{d}x \quad\ \Leftrightarrow \quad\ Q\, \text{d}u=R\, \text{d}y
$$


