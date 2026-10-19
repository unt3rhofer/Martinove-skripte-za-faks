---
title: 2 Uvjetna vjerojatnost i nezavisnost
---
# Uvjetna vjerojatnost
Bacamo dvije kocke, dakle

$$
\Omega = \{(i,j): i,j\in\{1,2,\ldots,6\}\}.
$$

- Ako je

$$
A=\{\text{zbroj je 4}\}=\{(1,3),(2,2),(3,1)\},
$$

imamo

$$
P(A)
=
\frac{|A|}{|\Omega|}
=
\frac{3}{6^2}
=
\frac{1}{12}.
$$

- Ako znamo da se dogodio

$$
B=\{\text{na prvoj kocki pala dvojka}\}
=
\{(2,1),\ldots,(2,6)\},
$$

kolika je sada vjerojatnost događaja $A$?

$\Rightarrow$ sada $B$ postaje „novi” $\Omega$ te su opet svi događaji jednako vjerojatni, pa budući da je od svih $\omega\in B$, jedino ishod $(2,2)$ povoljan za $A$, imamo

$$
\begin{aligned}
P(A\mid B)
&:= \text{„uvjetna vjerojatnost od } A \text{ uz dano } B\text{”}\\
&=
\frac{|\{(2,2)\}|}{|B|}
=
\frac{1}{6}
\left(
>
\frac{1}{12}
=
P(A)
\right).
\end{aligned}
$$

Uočimo, vrijedi

$$
P(A\mid B)
=
\frac{|A\cap B|}{|B|}
=
\frac{|A\cap B|/|\Omega|}{|B|/|\Omega|}
=
\frac{P(A\cap B)}{P(B)}.
$$


> [!definicija] Uvjetna vjerojatnost
> Neka je $(\Omega,\mathcal F,P)$ proizvoljan vjerojatnosni prostor. Ako $B\in\mathcal F$ zadovoljava $P(B)>0$, za sve $A\in\mathcal F$ definiramo
>
> $$
> P(A\mid B):=\frac{P(A\cap B)}{P(B)}.
> $$
>
>
> Vrijedi
>
> $$
> P(A\cap B)=P(A\mid B)P(B).
> $$
>
Ako je $P(B)=0$, $P(A\mid B)$ nije definirana, ali svejedno koristimo $P(A\cap B)=P(A\mid B)P(B)$
tj. u tom slučaju definiramo

$$
P(A\mid B)P(B):=0\;(=P(A\cap B)).
$$
## Formula potpune vjerojatnosti (FPV)
> [!definicija] Potpun sistem događaja (PSD)
> Konačna ili prebrojiva familija događaja $(H_i)_{i\in I}$, gdje je
>
> $$
> I=\{1,2,\ldots,n\}
> \qquad\text{ili}\qquad
> I=\mathbb N,
> $$
>
> zove se **potpun sistem događaja (PSD)** ako vrijedi:
>
> 1. događaji su u parovima disjunktni:
>
> $$
> H_i\cap H_j=\varnothing,
> \qquad \forall i\neq j,
> $$
>
> 2. njihova unija daje cijeli prostor elementarnih događaja:
>
> $$
> \bigcup_{i\in I}H_i=\Omega.
> $$
> [!bitnatvrdnja] Formula potpune vjerojatnosti (FPV)
> Za sve $A\in\mathcal F$ i bilo koji potpun sistem događaja $(H_i)_{i\in I}$ vrijedi
>
> $$
> P(A)
> =
> \sum_{i\in I} P(A\mid H_i)P(H_i).
> $$

> [!dokaz]- Dokaz
> Budući da je $A\subseteq\Omega$, imamo
>
> $$
> \begin{aligned}
> P(A)
> &=
> P(A\cap\Omega)\\
> &=
> P\left(
> A\cap\left(\bigcup_{i\in I}H_i\right)
> \right)\\
> &=
> P\left(
> \bigcup_{i\in I}(A\cap H_i)
> \right)\\
> &\underset{\text{(jer su }H_i\text{ u parovima disjunktni)}}{=}
> \sum_{i\in I}P(A\cap H_i)\\
> &=
> \sum_{i\in I}P(A\mid H_i)P(H_i).
> \end{aligned}
> $$
>
> Četvrta jednakost slijedi iz konačne/$\sigma$-aditivnosti, a zadnja iz
>
> $$
> P(A\cap B)=P(A\mid B)P(B).
> $$

Za fiksan $A\in\mathcal F$, za formulu potpune vjerojatnosti

$$
\mathbb P(A)
=
\sum_{i\in I}\mathbb P(A\mid H_i)\mathbb P(H_i)
$$

dovoljno je da vrijedi

$$
H_i\cap H_j=\emptyset,
\qquad \forall i\neq j,
$$

te

$$
A\subseteq\bigcup_{i\in I}H_i,
$$

umjesto

$$
\bigcup_{i\in I}H_i=\Omega.
$$

> [!bitnatvrdnja] Bayesova formula
> Ako je $A\in\mathcal F$ takav da je $P(A)>0$ te je $(H_i)_{i\in I}$ potpun sistem događaja, za sve $j\in I$ vrijedi
> $$
> P(H_j\mid A)
> =
> \frac{P(A\mid H_j)P(H_j)}{P(A)}
> =
> \frac{P(A\mid H_j)P(H_j)}
> {\displaystyle\sum_{i\in I}P(A\mid H_i)P(H_i)}.
> $$

> [!dokaz]- Dokaz
> Po definiciji uvjetne vjerojatnosti,
>
> $$
> P(H_j\mid A)
> =
> \frac{P(H_j\cap A)}{P(A)}.
> $$
>
> Budući da
>
> $$
> P(H_j\cap A)
> =
> P(A\mid H_j)P(H_j),
> $$
>
> slijedi
>
> $$
> P(H_j\mid A)
> =
> \frac{P(A\mid H_j)P(H_j)}{P(A)}.
> $$
>
> Po formuli potpune vjerojatnosti,
>
> $$
> P(A)
> =
> \sum_{i\in I}P(A\mid H_i)P(H_i).
> $$
>
> Uvrštavanjem dobivamo
>
> $$
> P(H_j\mid A)
> =
> \frac{P(A\mid H_j)P(H_j)}
> {\displaystyle\sum_{i\in I}P(A\mid H_i)P(H_i)}.
> $$

### Ostala svojstva uvjetne vjerojatnosti
> [!istaknuto] Vjerojatnost presjeka $n$ događaja
> Neka su $A_j\in\mathcal F$, $j=1,\ldots,n$, takvi da je
>
> $$
> P(A_1\cap\cdots\cap A_{n-1})>0.
> $$
>
> Tada vrijedi
>
> $$
> \begin{aligned}
> P(A_1\cap A_2\cap\cdots\cap A_n)
> &=
> P(A_1)
> P(A_2\mid A_1)
> P(A_3\mid A_1\cap A_2)
> \cdots\\
> &\qquad\cdots
> P(A_n\mid A_1\cap\cdots\cap A_{n-1}).
> \end{aligned}
> $$

> [!dokaz]- Dokaz
> Raspisujemo desnu stranu po definiciji uvjetne vjerojatnosti:
>
> $$
> \begin{aligned}
> &P(A_1)
> P(A_2\mid A_1)
> P(A_3\mid A_1\cap A_2)
> \cdots
> P(A_n\mid A_1\cap\cdots\cap A_{n-1})
> \\[4pt]
> &=
> P(A_1)
> \frac{P(A_1\cap A_2)}{P(A_1)}
> \frac{P(A_1\cap A_2\cap A_3)}
> {P(A_1\cap A_2)}
> \cdots
> \frac{P(A_1\cap\cdots\cap A_n)}
> {P(A_1\cap\cdots\cap A_{n-1})}.
> \end{aligned}
> $$
>
> Svi se članovi pokrate osim brojnika posljednjeg faktora. Vizualno:
>
> $$
> \require{cancel}
> \begin{aligned}
> &\cancel{P(A_1)}
> \cdot
> \frac{\cancel{P(A_1\cap A_2)}}{\cancel{P(A_1)}}
> \cdot
> \frac{\cancel{P(A_1\cap A_2\cap A_3)}}
> {\cancel{P(A_1\cap A_2)}}
> \cdots\\
> &\qquad\cdots
> \frac{\cancel{P(A_1\cap\cdots\cap A_{n-1})}}
> {\cancel{P(A_1\cap\cdots\cap A_{n-2})}}
> \cdot
> \frac{P(A_1\cap\cdots\cap A_n)}
> {\cancel{P(A_1\cap\cdots\cap A_{n-1})}}
> \\[4pt]
> &=
> P(A_1\cap\cdots\cap A_n).
> \end{aligned}
> $$
>
> Time je tvrdnja dokazana.


# Nezavisnost
> [!definicija] Nezavisnost događaja
> **(i)** Događaji $A,B\in\mathcal F$ su **nezavisni** ako vrijedi
>
> $$
> P(A\cap B)=P(A)P(B).
> $$
>
> **(ii)** Događaji $A,B\in\mathcal F$ su **uvjetno nezavisni uz dani $C\in\mathcal F$**, $P(C)>0$, ako vrijedi
>
> $$
> P(A\cap B\mid C)
> =
> P(A\mid C)P(B\mid C),
> $$
>
> to jest ako su nezavisni s obzirom na $P_C$.
> [!istaknuto] Karakterizacija nezavisnosti događaja
> **(i)** Ako je $P(B)>0$ i $A\in\mathcal F$ proizvoljan, nezavisnost događaja $A$ i $B$ je ekvivalentno s
>
> $$
> P(A\mid B)=P(A), 
> $$
>
> što daje intuitivniju definiciju nezavisnosti.
>
> **(ii)** Ako je $P(B)=0$ ili $1$, $A$ i $B$ su nezavisni za svaki $A\in\mathcal F$.
>
> **(iii)** Ako je $P(B\cap C)>0$ (tj. $P_C(B)>0$) i $A\in\mathcal F$ proizvoljan, nezavisnost $A$ i $B$ uz dano $C$ je ekvivalentno s
>
> $$
> P(A\mid B\cap C)=P(A\mid C). 
> $$
>
> **(iv)** Ako je $P(B\mid C)=0$ ili $1$, uvjetna nezavisnost $A$ i $B$ za dani $C$ vrijedi za svaki $A\in\mathcal F$.

> [!dokaz]- Dokaz
> **(i)**
> Pretpostavimo da su $A$ i $B$ nezavisni, odnosno
>
> $$
> P(A\cap B)=P(A)P(B).
> $$
>
> Tada
>
> $$
> P(A\mid B)
> =
> \frac{P(A\cap B)}{P(B)}
> =
> \frac{P(A)\cancel{P(B)}}{\cancel{P(B)}}
> =
> P(A).
> $$
>
> Obratno, pretpostavimo da vrijedi
>
> $$
> P(A\mid B)=P(A).
> $$
>
> Tada
>
> $$
> P(A)
> =
> \frac{P(A\cap B)}{P(B)}
> \implies
> P(A)P(B)=P(A\cap B),
> $$
>
> pa su $A$ i $B$ nezavisni.
> **(ii)**
> Ako je $P(B)=0$, budući da je $A\cap B\subseteq B$, po monotonosti vrijedi
>
> $$
> 0\leq P(A\cap B)\leq P(B)=0,
> $$
>
> pa je
>
> $$
> P(A\cap B)=0=P(A)P(B).
> $$
>
> Ako je $P(B)=1$, tada je
>
> $$
> P(B^c)=1-P(B)=0.
> $$
>
> Budući da je
>
> $$
> A=(A\cap B)\cup(A\cap B^c)
> $$
>
> disjunktna unija te je $A\cap B^c\subseteq B^c$, slijedi
>
> $$
> P(A\cap B^c)=0.
> $$
>
> Zato
>
> $$
> P(A)
> =
> P(A\cap B)+P(A\cap B^c)
> =
> P(A\cap B),
> $$
>
> odnosno
>
> $$
> P(A\cap B)=P(A)=P(A)P(B).
> $$
>
> Dakle, u oba slučaja $A$ i $B$ su nezavisni.
> **(iii)** i **(iv)** slijede direktno iz **(i)** i **(ii)** kada se primjene na $\mathbb{P}_{C}$


Ako su $A,B\in\mathcal F$ nezavisni, onda su nezavisni i parovi događaja:
$$
A^c \text{ i } B,\qquad
A \text{ i } B^c,\qquad
A^c \text{ i } B^c.
$$

> [!dokaz]- Dokaz
> Za $A^c$ i $B$ imamo
>
> $$
> \begin{aligned}
> P(A^c\cap B)
> &=P(B\setminus A)\\
> &=P(B)-P(A\cap B)\\
> &\overset{\text{nezavisnost}}{=}P(B)-P(A)P(B)\\
> &=P(B)(1-P(A))\\
> &=P(B)P(A^c).
> \end{aligned}
> $$
>
> Dakle, $A^c$ i $B$ su nezavisni.
>
> Za $A$ i $B^c$ imamo
>
> $$
> \begin{aligned}
> P(A\cap B^c)
> &=P(A\setminus B)\\
> &=P(A)-P(A\cap B)\\
> &\overset{\text{nezavisnost}}{=}P(A)-P(A)P(B)\\
> &=P(A)(1-P(B))\\
> &=P(A)P(B^c).
> \end{aligned}
> $$
>
> Dakle, $A$ i $B^c$ su nezavisni.
>
> Konačno,
>
> $$
> \begin{aligned}
> P(A^c\cap B^c)
> &=P((A\cup B)^c)\\
> &=1-P(A\cup B)\\
> &=1-\bigl(P(A)+P(B)-P(A\cap B)\bigr)\\
> &\overset{\text{nezavisnost}}{=}
> 1-\bigl(P(A)+P(B)-P(A)P(B)\bigr)\\
> &=1-\bigl(P(A)(1-P(B))+P(B)\bigr)\\
> &=1-P(A)P(B^c)-P(B)\\
> &=1-P(B)-P(A)P(B^c)\\
> &=P(B^c)-P(A)P(B^c)\\
> &=P(B^c)(1-P(A))\\
> &=P(A^c)P(B^c).
> \end{aligned}
> $$
>
> Dakle, $A^c$ i $B^c$ su nezavisni.

## Nezavisnost familije događaja

> [!definicija] Nezavisnost familije događaja
> Familija događaja $(A_i)_{i\in I}$ pri čemu $I$ može biti proizvoljan skup, je
>
> (i) **nezavisna** ako vrijedi
>
> $$
> P\left(\bigcap_{i\in F} A_i\right)
> =
> \prod_{i\in F} P(A_i),
> $$
>
> za svaki konačan i neprazan podskup $F\subseteq I$.
>
> (ii) **uvjetno nezavisna uz dano** $C\in\mathcal F$, $P(C)>0$, ako je nezavisna [u smislu definicije (i)] s obzirom na $P_C$.
>
> (iii) **u parovima nezavisna** ako su $A_i$ i $A_j$ nezavisni za sve $i,j\in I$, $i\neq j$.
>
 
 Na primjer, $A,B,C\in\mathcal F$ su nezavisni ako vrijedi

 1. $P(A\cap B)=P(A)P(B)$, $P(A\cap C)=P(A)P(C)$, $P(B\cap C)=P(B)P(C)$,

 te još

 2. $P(A\cap B\cap C)=P(A)P(B)P(C)$.

Zašto ne samo 2?
> [!odgovor]- Odgovor
> Uzmite na primjer $C=\emptyset$, onda bi za sve $A,B$ imali da su $A,B,C$ nezavisni što očito nema smisla.


> [!istaknuto] Karakterizacija nezavisnosti familije događaja
> Ako su $(A_i)_{i\in I}$ nezavisni, vrijedi
>
> $$
> P\left(
> \left.
> \bigcap_{i\in F_2} A_i
> \,\right|\,
> \bigcap_{j\in F_1} A_j
> \right)
> =
> P\left(\bigcap_{i\in F_2} A_i\right)
> =
> \prod_{i\in F_2} P(A_i),
> $$
>
> za sve konačne, neprazne i disjunktne podskupove $F_1,F_2\subseteq I$, pri čemu pretpostavljamo da je
>
> $$
> P\left(\bigcap_{i\in F_1}A_i\right)>0.
> $$

> [!dokaz]- Dokaz.
> Po definiciji uvjetne vjerojatnosti,
>
> $$
> P\left(
> \left.
> \bigcap_{i\in F_2}A_i
> \,\right|\,
> \bigcap_{j\in F_1}A_j
> \right)
> =
> \frac{
> P\left(
> \bigcap_{i\in F_2}A_i
> \cap
> \bigcap_{j\in F_1}A_j
> \right)
> }{
> P\left(\bigcap_{j\in F_1}A_j\right)
> }.
> $$
>
> Budući da su $F_1$ i $F_2$ disjunktni i familija $(A_i)_{i\in I}$ nezavisna,
>
> $$
> =
> \frac{
> \prod_{k\in F_1\cup F_2}P(A_k)
> }{
> \prod_{j\in F_1}P(A_j)
> }
> =
> \prod_{i\in F_2}P(A_i).
> $$
>
> Opet po nezavisnosti,
>
> $$
> \prod_{i\in F_2}P(A_i)
> =
> P\left(\bigcap_{i\in F_2}A_i\right).
> $$
> Nadalje, imamo iduću napomenu koja pokazuje da naša definicija i intuitivno ima smisla.


> [!istaknuto] Uočimo!
> **Nezavisnost u parovima općenito ne povlači nezavisnost!**

Bacamo dvije kocke te neka je

$$
A=\{\text{na prvoj kocki 3}\},
$$

$$
B=\{\text{na drugoj kocki 4}\},
$$

$$
C=\{\text{zbroj je 7}\}.
$$

Pokazali smo da su $A,B,C$ u parovima nezavisni, ali tvrdimo da nisu nezavisni.

To slijedi iz

$$
P(A\mid B\cap C)
=
1
\neq
\frac16
=
P(A),
$$

što je kontradikcija s tvrdnjom da bi za nezavisne $A,B,C$ moralo vrijediti

$$
P(A\mid B\cap C)=P(A),
$$

ili iz

$$
P(A\cap B\cap C)
=
P(\{(3,4)\})
=
\frac1{36}
\neq
\frac16\cdot\frac16\cdot\frac6{36}
=
P(A)P(B)P(C).
$$


> [!istaknuto] Nezavisnost familije komplemenata
> Ako je familija događaja $(A_i)_{i\in I}$ nezavisna, tada je nezavisna i svaka familija događaja $(B_i)_{i\in I}$ pri čemu je
>
> $$
> B_i=A_i
> \quad \text{ili} \quad
> B_i=A_i^c,
> \qquad \forall i\in I.
> $$

Dokaz se ne ispituje.