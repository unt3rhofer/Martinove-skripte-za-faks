---
title: 2 Uvjetna vjerojatnost i nezavisnost
---
## Uvjetna vjerojatnost

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
\mathbb{P}(A)
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
\mathbb{P}(A\mid B)
&:= \text{„uvjetna vjerojatnost od } A \text{ uz dano } B\text{”}\\
&=
\frac{|\{(2,2)\}|}{|B|}
=
\frac{1}{6}
\left(
>
\frac{1}{12}
=
\mathbb{P}(A)
\right).
\end{aligned}
$$

Uočimo, vrijedi

$$
\mathbb{P}(A\mid B)
=
\frac{|A\cap B|}{|B|}
=
\frac{|A\cap B|/|\Omega|}{|B|/|\Omega|}
=
\frac{\mathbb{P}(A\cap B)}{\mathbb{P}(B)}.
$$



> [!definicija] Uvjetna vjerojatnost
> Neka je $(\Omega,\mathcal F,\mathbb{P})$ proizvoljan vjerojatnosni prostor. Ako $B\in\mathcal F$ zadovoljava $\mathbb{P}(B)>0$, za sve $A\in\mathcal F$ definiramo
>
> $$
> \mathbb{P}(A\mid B):=\frac{\mathbb{P}(A\cap B)}{\mathbb{P}(B)}.
> $$
>
>
> Vrijedi
>
> $$
> \mathbb{P}(A\cap B)=\mathbb{P}(A\mid B)\mathbb{P}(B).
> $$

Neka je $(\Omega,\mathcal F,\mathbb P)$ vjerojatnosni prostor i $C\in\mathcal F$ takav da je $\mathbb P(C)>0$. Tada je funkcija

$$
\mathbb P_C(A):= \mathbb{P}(A \mid C) = \frac{\mathbb P(A\cap C)}{\mathbb P(C)},\qquad A\in\mathcal F,
$$

**vjerojatnost na $(\Omega,\mathcal F)$**, odnosno $(\Omega,\mathcal F,\mathbb P_C)$ je vjerojatnosni prostor.

> [!dokaz]- Dokaz.
> **(i) Nenegativnost**
>
> Za svaki $A\in\mathcal F$ vrijedi
>
> $$
> \mathbb P_C(A)=\frac{\mathbb P(A\cap C)}{\mathbb P(C)}\ge 0,
> $$
>
> jer je $\mathbb P$ nenegativna i $\mathbb P(C)>0$.
>
> **(ii) Normiranost**
>
> Budući da je $\Omega\cap C=C$, vrijedi
>
> $$
> \mathbb P_C(\Omega)
> =\frac{\mathbb P(\Omega\cap C)}{\mathbb P(C)}
> =\frac{\mathbb P(C)}{\mathbb P(C)}
> =1.
> $$
>
> **(iii) $\sigma$-aditivnost**
>
> Neka je $(A_n)_{n\in\mathbb N}$ niz u parovima disjunktnih događaja iz $\mathcal F$. Tada je i niz $(A_n\cap C)_{n\in\mathbb N}$ u parovima disjunktan pa, koristeći $\sigma$-aditivnost od $\mathbb P$, dobivamo
>
> $$
> \begin{aligned}
> \mathbb P_C\left(\bigcup_{n=1}^{\infty}A_n\right)
> &=\frac{\mathbb P\left(\bigcup_{n=1}^{\infty}(A_n\cap C)\right)}{\mathbb P(C)}\\
> &=\frac{\sum_{n=1}^{\infty}\mathbb P(A_n\cap C)}{\mathbb P(C)}\\
> &=\sum_{n=1}^{\infty}\mathbb P_C(A_n).
> \end{aligned}
> $$
>
> Time su provjerena sva tri aksioma vjerojatnosti.

Ako je $\mathbb{P}(B)=0$, $\mathbb{P}(A\mid B)$ nije definirana, ali svejedno koristimo $\mathbb{P}(A\cap B)=\mathbb{P}(A\mid B)\mathbb{P}(B)$
tj. u tom slučaju definiramo

$$
\mathbb{P}(A\mid B)\mathbb{P}(B):=0\;(=\mathbb{P}(A\cap B)).
$$

### Formula potpune vjerojatnosti (FPV)

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
> \mathbb{P}(A)
> =
> \sum_{i\in I} \mathbb{P}(A\mid H_i)\mathbb{P}(H_i).
> $$

> [!dokaz]- Dokaz.
> Budući da je $A\subseteq\Omega$, imamo
>
> $$
> \begin{aligned}
> \mathbb{P}(A)
> &=
> \mathbb{P}(A\cap\Omega)\\
> &=
> \mathbb{P}\left(
> A\cap\left(\bigcup_{i\in I}H_i\right)
> \right)\\
> &=
> \mathbb{P}\left(
> \bigcup_{i\in I}(A\cap H_i)
> \right)\\
> &\underset{\text{(jer su }H_i\text{ u parovima disjunktni)}}{=}
> \sum_{i\in I}\mathbb{P}(A\cap H_i)\\
> &=
> \sum_{i\in I}\mathbb{P}(A\mid H_i)\mathbb{P}(H_i).
> \end{aligned}
> $$
>
> Četvrta jednakost slijedi iz konačne/$\sigma$-aditivnosti, a zadnja iz
>
> $$
> \mathbb{P}(A\cap B)=\mathbb{P}(A\mid B)\mathbb{P}(B).
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
> Ako je $A\in\mathcal F$ takav da je $\mathbb{P}((A)>0$ te je $(H_i)_{i\in I}$ potpun sistem događaja, za sve $j\in I$ vrijedi
> $$
> \mathbb{P}(H_j\mid A)
> =
> \frac{\mathbb{P}(A\mid H_j)\mathbb{P}(H_j)}{P(A)}
> =
> \frac{\mathbb{P}(A\mid H_j)\mathbb{P}(H_j)}
> {\displaystyle\sum_{i\in I}\mathbb{P}(A\mid H_i)\mathbb{P}(H_i)}.
> $$

> [!dokaz]- Dokaz.
> Po definiciji uvjetne vjerojatnosti,
>
> $$
> \mathbb{P}(H_j\mid A)
> =
> \frac{\mathbb{P}(H_j\cap A)}{\mathbb{P}(A)}.
> $$
>
> Budući da
>
> $$
> \mathbb{P}(H_j\cap A)
> =
> \mathbb{P}(A\mid H_j)\mathbb{\mathbb{P}}(H_j),
> $$
>
> slijedi
>
> $$
> \mathbb{P}(H_j\mid A)
> =
> \frac{\mathbb{P}(A\mid H_j)\mathbb{P}(H_j)}{\mathbb{P}(A)}.
> $$
>
> Po formuli potpune vjerojatnosti,
>
> $$
> \mathbb{P}(A)
> =
> \sum_{i\in I}\mathbb{P}(A\mid H_i)\mathbb{P}(H_i).
> $$
>
> Uvrštavanjem dobivamo
>
> $$
> \mathbb{P}(H_j\mid A)
> =
> \frac{\mathbb{P}(A\mid H_j)\mathbb{P}(H_j)}
> {\displaystyle\sum_{i\in I}\mathbb{P}(A\mid H_i)\mathbb{P}(H_i)}.
> $$


### Ostala svojstva uvjetne vjerojatnosti

> [!istaknuto] Vjerojatnost presjeka $n$ događaja
> Neka su $A_j\in\mathcal F$, $j=1,\ldots,n$, takvi da je
>
> $$
> \mathbb{P}(A_1\cap\cdots\cap A_{n-1})>0.
> $$
>
> Tada vrijedi
>
> $$
> \begin{aligned}
> \mathbb{P}(A_1\cap A_2\cap\cdots\cap A_n)
> &=
> \mathbb{P}(A_1)
> \mathbb{P}(A_2\mid A_1)
> \mathbb{P}(A_3\mid A_1\cap A_2)
> \cdots\\
> &\qquad\cdots
> \mathbb{P}(A_n\mid A_1\cap\cdots\cap A_{n-1}).
> \end{aligned}
> $$

> [!dokaz]- Dokaz.
> Raspisujemo desnu stranu po definiciji uvjetne vjerojatnosti:
>
> $$
> \begin{aligned}
> &\mathbb{P}(A_1)
> \mathbb{P}(A_2\mid A_1)
> \mathbb{P}(A_3\mid A_1\cap A_2)
> \cdots
> \mathbb{P}(A_n\mid A_1\cap\cdots\cap A_{n-1})
> \\[4pt]
> &=
> \mathbb{P}(A_1)
> \frac{\mathbb{P}(A_1\cap A_2)}{\mathbb{P}(A_1)}
> \frac{\mathbb{P}(A_1\cap A_2\cap A_3)}
> {\mathbb{P}(A_1\cap A_2)}
> \cdots
> \frac{\mathbb{P}(A_1\cap\cdots\cap A_n)}
> {\mathbb{P}(A_1\cap\cdots\cap A_{n-1})}.
> \end{aligned}
> $$
>
> Svi se članovi pokrate osim brojnika posljednjeg faktora. Vizualno:
>
> $$
> \require{cancel}
> \begin{aligned}
> &\cancel{\mathbb{P}(A_1)}
> \cdot
> \frac{\cancel{\mathbb{P}(A_1\cap A_2)}}{\cancel{\mathbb{P}(A_1)}}
> \cdot
> \frac{\cancel{\mathbb{P}(A_1\cap A_2\cap A_3)}}
> {\cancel{\mathbb{P}(A_1\cap A_2)}}
> \cdots\\
> &\qquad\cdots
> \frac{\cancel{\mathbb{P}(A_1\cap\cdots\cap A_{n-1})}}
> {\cancel{\mathbb{P}(A_1\cap\cdots\cap A_{n-2})}}
> \cdot
> \frac{\mathbb{P}(A_1\cap\cdots\cap A_n)}
> {\cancel{\mathbb{P}(A_1\cap\cdots\cap A_{n-1})}}
> \\[4pt]
> &=
> \mathbb{P}(A_1\cap\cdots\cap A_n).
> \end{aligned}
> $$
>
> Time je tvrdnja dokazana.

## Nezavisnost

> [!definicija] Nezavisnost događaja
> **(i)** Događaji $A,B\in\mathcal F$ su **nezavisni** ako vrijedi
>
> $$
> \mathbb{P}(A\cap B)=\mathbb{P}(A)\mathbb{P}(B).
> $$
>
> **(ii)** Događaji $A,B\in\mathcal F$ su **uvjetno nezavisni uz dani $C\in\mathcal F$**, $\mathbb{P}(C)>0$, ako vrijedi
>
> $$
> \mathbb{P}(A\cap B\mid C)
> =
> \mathbb{P}(A\mid C)\mathbb{P}(B\mid C),
> $$
>
> to jest ako su nezavisni s obzirom na $\mathbb{P}_C$.

> [!istaknuto] Karakterizacija nezavisnosti događaja
> **(i)** Ako je $
\mathbb{P}(B)>0$ i $A\in\mathcal F$ proizvoljan, nezavisnost događaja $A$ i $B$ je ekvivalentno s
>
> $$
> \mathbb{P}(A\mid B)=\mathbb{P}(A), 
> $$
>
> što daje intuitivniju definiciju nezavisnosti.
>
> **(ii)** Ako je $\mathbb{P}(B)=0$ ili $1$, $A$ i $B$ su nezavisni za svaki $A\in\mathcal F$.
>
> **(iii)** Ako je $\mathbb{P}(B\cap C)>0$ (tj. $\mathbb{P}_C(B)>0$) i $A\in\mathcal F$ proizvoljan, nezavisnost $A$ i $B$ uz dano $C$ je ekvivalentno s
>
> $$
> \mathbb{P}(A\mid B\cap C)=\mathbb{P}(A\mid C). 
> $$
>
> **(iv)** Ako je $\mathbb{P}(B\mid C)=0$ ili $1$, uvjetna nezavisnost $A$ i $B$ za dani $C$ vrijedi za svaki $A\in\mathcal F$.

> [!dokaz]- Dokaz.
> **(i)**
> Pretpostavimo da su $A$ i $B$ nezavisni, odnosno
>
> $$
> \mathbb{P}(A\cap B)=\mathbb{P}(A)\mathbb{P}(B).
> $$
>
> Tada
>
> $$
> \mathbb{P}(A\mid B)
> =
> \frac{\mathbb{P}(A\cap B)}{\mathbb{P}(B)}
> =
> \frac{\mathbb{P}(A)\cancel{\mathbb{P}(B)}}{\cancel{\mathbb{P}(B)}}
> =
> \mathbb{P}(A).
> $$
>
> Obratno, pretpostavimo da vrijedi
>
> $$
> \mathbb{P}(A\mid B)=\mathbb{P}(A).
> $$
>
> Tada
>
> $$
> \mathbb{P}(A)
> =
> \frac{\mathbb{P}(A\cap B)}{\mathbb{P}(B)}
> \implies
> \mathbb{P}(A)\mathbb{P}(B)=\mathbb{P}(A\cap B),
> $$
>
> pa su $A$ i $B$ nezavisni.
> **(ii)**
> **Slučaj $\mathbb{P}(B)=0$:**
>
> Budući da je $A\cap B\subseteq B$, vrijedi
>
> $$
> 0\le \mathbb{P}(A\cap B)\le \mathbb{P}(B)=0.
> $$
>
> Dakle,
>
> $$
> \mathbb{P}(A\cap B)=0=\mathbb{P}(A)\mathbb{P}(B).
> $$
>
> **Slučaj $\mathbb{P}(B)=1$:**
>
> Tada je $\mathbb{P}(B^c)=0$, pa vrijedi
>
> $$
> \begin{aligned}
> \mathbb{P}(A\cap B)
> &=1-\mathbb{P}((A\cap B)^c)\\
> &=1-\mathbb{P}(A^c\cup B^c)\\
> &=1-\left[\mathbb{P}(A^c)+\mathbb{P}(B^c)-\mathbb{P}(A^c\cap B^c)\right]\\
> &=1-\mathbb{P}(A^c)-0+0\\
> &=\mathbb{P}(A)\\
> &=\mathbb{P}(A)\cdot 1\\
> &=\mathbb{P}(A)\mathbb{P}(B).
> \end{aligned}
> $$
> **(iii)** i **(iv)** slijede direktno iz **(i)** i **(ii)** kada se primjene na $\mathbb{\mathbb{P}}_{C}$



Ako su $A,B\in\mathcal F$ nezavisni, onda su nezavisni i parovi događaja:
$$
A^c \text{ i } B,\qquad
A \text{ i } B^c,\qquad
A^c \text{ i } B^c.
$$

> [!dokaz]- Dokaz.
> Za $A^c$ i $B$ imamo
>
> $$
> \begin{aligned}
> \mathbb{P}(A^c\cap B)
> &=\mathbb{P}(B\setminus A)\\
> &=\mathbb{P}(B)-\mathbb{P}(A\cap B)\\
> &\overset{\text{nezavisnost}}{=}\mathbb{P}(B)-\mathbb{P}(A)\mathbb{P}(B)\\
> &=\mathbb{P}(B)(1-\mathbb{P}(A))\\
> &=\mathbb{P}(B)\mathbb{P}(A^c).
> \end{aligned}
> $$
>
> Dakle, $A^c$ i $B$ su nezavisni.
>
> Za $A$ i $B^c$ imamo
>
> $$
> \begin{aligned}
> \mathbb{P}(A\cap B^c)
> &=\mathbb{P}(A\setminus B)\\
> &=\mathbb{P}(A)-\mathbb{P}(A\cap B)\\
> &\overset{\text{nezavisnost}}{=}\mathbb{P}(A)-\mathbb{P}(A)\mathbb{P}(B)\\
> &=\mathbb{P}(A)(1-\mathbb{P}(B))\\
> &=\mathbb{P}(A)\mathbb{P}(B^c).
> \end{aligned}
> $$
>
> Dakle, $A$ i $B^c$ su nezavisni.
>
> Konačno,
>
> $$
> \begin{aligned}
> \mathbb{P}(A^c\cap B^c)
> &=\mathbb{P}((A\cup B)^c)\\
> &=1-\mathbb{P}(A\cup B)\\
> &=1-\bigl(\mathbb{P}(A)+\mathbb{P}(B)-\mathbb{P}(A\cap B)\bigr)\\
> &\overset{\text{nezavisnost}}{=}
> 1-\bigl(\mathbb{P}(A)+\mathbb{P}(B)-\mathbb{P}(A)\mathbb{P}(B)\bigr)\\
> &=1-\bigl(\mathbb{P}(A)(1-\mathbb{P}(B))+\mathbb{P}(B)\bigr)\\
> &=1-\mathbb{P}(A)\mathbb{P}(B^c)-\mathbb{P}(B)\\
> &=1-\mathbb{P}(B)-\mathbb{P}(A)\mathbb{P}(B^c)\\
> &=\mathbb{P}(B^c)-\mathbb{P}(A)\mathbb{P}(B^c)\\
> &=\mathbb{P}(B^c)(1-\mathbb{P}(A))\\
> &=\mathbb{P}(A^c)\mathbb{P}(B^c).
> \end{aligned}
> $$
>
> Dakle, $A^c$ i $B^c$ su nezavisni.

### Nezavisnost familije događaja

> [!definicija] Nezavisnost familije događaja
> Familija događaja $(A_i)_{i\in I}$ pri čemu $I$ može biti proizvoljan skup, je
>
> **(i)** **nezavisna** ako vrijedi
>
> $$
> \mathbb{P}\left(\bigcap_{i\in F} A_i\right)
> =
> \prod_{i\in F} \mathbb{P}(A_i),
> $$
>
> za svaki konačan i neprazan podskup $F\subseteq I$.
>
> **(ii)** **uvjetno nezavisna uz dano** $C\in\mathcal F$, $\mathbb{P}(C)>0$, ako je nezavisna [u smislu definicije (i)] s obzirom na $\mathbb{P}_C$.
>
> **(iii)** **u parovima nezavisna** ako su $A_i$ i $A_j$ nezavisni za sve $i,j\in I$, $i\neq j$.
>

 Na primjer, $A,B,C\in\mathcal F$ su nezavisni ako vrijedi

 1. $\mathbb{P}(A\cap B)=\mathbb{P}(A)\mathbb{P}(B)$, $\mathbb{P}(A\cap C)=\mathbb{P}(A)\mathbb{P}(C)$, $\mathbb{P}(B\cap C)=\mathbb{P}(B)\mathbb{P}(C)$,

 te još

 2. $\mathbb{P}(A\cap B\cap C)=\mathbb{P}(A)\mathbb{P}(B)\mathbb{P}(C)$.

Zašto ne samo 2?
> [!odgovor]- Odgovor.
> Uzmite na primjer $C=\emptyset$, onda bi za sve $A,B$ imali da su $A,B,C$ nezavisni što očito nema smisla.

> [!istaknuto] Karakterizacija nezavisnosti familije događaja
> Ako su $(A_i)_{i\in I}$ nezavisni, vrijedi
>
> $$
> \mathbb{P}\left(
> \left.
> \bigcap_{i\in F_2} A_i
> \,\right|\,
> \bigcap_{j\in F_1} A_j
> \right)
> =
> \mathbb{P}\left(\bigcap_{i\in F_2} A_i\right)
> =
> \prod_{i\in F_2} \mathbb{P}(A_i),
> $$
>
> za sve konačne, neprazne i disjunktne podskupove $F_1,F_2\subseteq I$, pri čemu pretpostavljamo da je
>
> $$
> \mathbb{P}\left(\bigcap_{i\in F_1}A_i\right)>0.
> $$

> [!dokaz]- Dokaz.
> Po definiciji uvjetne vjerojatnosti,
>
> $$
> \mathbb{P}\left(
> \left.
> \bigcap_{i\in F_2}A_i
> \,\right|\,
> \bigcap_{j\in F_1}A_j
> \right)
> =
> \frac{
> \mathbb{P}\left(
> \bigcap_{i\in F_2}A_i
> \cap
> \bigcap_{j\in F_1}A_j
> \right)
> }{
> \mathbb{P}\left(\bigcap_{j\in F_1}A_j\right)
> }.
> $$
>
> Budući da su $F_1$ i $F_2$ disjunktni i familija $(A_i)_{i\in I}$ nezavisna,
>
> $$
> =
> \frac{
> \prod_{k\in F_1\cup F_2}\mathbb{P}(A_k)
> }{
> \prod_{j\in F_1}\mathbb{P}(A_j)
> }
> =
> \prod_{i\in F_2}\mathbb{P}(A_i).
> $$
>
> Opet po nezavisnosti,
>
> $$
> \prod_{i\in F_2}\mathbb{P}(A_i)
> =
> \mathbb{P}\left(\bigcap_{i\in F_2}A_i\right).
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
\mathbb{P}(A\mid B\cap C)
=
1
\neq
\frac16
=
\mathbb{P}(A),
$$

što je kontradikcija s tvrdnjom da bi za nezavisne $A,B,C$ moralo vrijediti

$$
\mathbb{P}(A\mid B\cap C)=\mathbb{P}(A),
$$

ili iz

$$
\mathbb{P}(A\cap B\cap C)
=
\mathbb{P}(\{(3,4)\})
=
\frac1{36}
\neq
\frac16\cdot\frac16\cdot\frac6{36}
=
\mathbb{P}(A)\mathbb{P}(B)\mathbb{P}(C).
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

### Borel-Cantelli leme

> [!bitnatvrdnja] Prva Borel-Cantelli lema
> Ako za niz događaja $A_1,A_2,\ldots\in\mathcal F$ vrijedi
>
> $$
> \sum_{i=1}^{\infty}\mathbb{P}(A_i)<\infty,
> $$
>
> onda je
>
> $$
> \mathbb{P}\left(
> \bigcap_{n=1}^{\infty}
> \bigcup_{k=n}^{\infty}A_k
> \right)=0.
> $$

> [!dokaz]- Dokaz.
> Stavimo
>
> $$
> B_n:=\bigcup_{k=n}^{\infty}A_k.
> $$
>
> Niz $(B_n)_{n\in\mathbb N}$ je padajući, pa po neprekidnosti vjerojatnosti
>
> $$
> \mathbb{P}\left(
> \bigcap_{n=1}^{\infty}\bigcup_{k=n}^{\infty}A_k
> \right)
> =
> \lim_{n\to\infty}
> \mathbb{P}\left(\bigcup_{k=n}^{\infty}A_k\right).
> $$
>
> Po $\sigma$-subaditivnosti,
>
> $$
> \mathbb{P}\left(\bigcup_{k=n}^{\infty}A_k\right)
> \leq
> \sum_{k=n}^{\infty}\mathbb{P}(A_k).
> $$
>
> Kako je $\sum_{k=1}^{\infty}\mathbb{P}(A_k)<\infty$, ostatak konvergentnog reda teži u $0$, pa
>
> $$
> \mathbb{P}\left(
> \bigcap_{n=1}^{\infty}\bigcup_{k=n}^{\infty}A_k
> \right)=0.
> $$

 Prva Borel–Cantellijeva lema kaže:

 $$
 \sum_{i=1}^{\infty} \mathbb{P}(A_i) < \infty
 \implies
 \mathbb{P}\left(
 \bigcap_{n=1}^{\infty}
 \bigcup_{k=n}^{\infty} A_k
 \right)
 =0.
 $$

 Događaj

 $$
 \bigcap_{n=1}^{\infty}
 \bigcup_{k=n}^{\infty} A_k
 $$

 znači da se dogodilo **beskonačno mnogo događaja $A_n$**.

 Za svaki fiksni $n$, događaj

 $$
 \bigcup_{k=n}^{\infty} A_k
 $$

 znači:

 **dogodio se barem jedan od $A_n,A_{n+1},A_{n+2},\ldots$**

 odnosno, nakon trenutka $n$ dogodio se barem još jedan $A_k$.

 Sada uzimamo presjek po svim $n$:

 $$
 \bigcap_{n=1}^{\infty}
 \bigcup_{k=n}^{\infty} A_k.
 $$

 To znači da prethodna tvrdnja mora vrijediti za svaki $n$:

 - nakon $n=1$ postoji neki $A_k$ koji se dogodio;
 - nakon $n=10$ postoji neki kasniji $A_k$;
 - nakon $n=1000$ opet postoji neki kasniji $A_k$;
 - koliko god daleko otišli u nizu, uvijek se kasnije dogodi još neki $A_k$.

 To je moguće **ako i samo ako se događaji $A_n$ događaju beskonačno mnogo puta**.

 To se skraćeno označava s:

 $$
 \boxed{A_n \text{ b.m.p.}}
 $$


> [!bitnatvrdnja] Druga Borel-Cantelli lema
> Ako je $A_1,A_2,\ldots\in\mathcal F$ niz nezavisnih događaja takvih da vrijedi
>
> $$
> \sum_{n=1}^{\infty}\mathbb{P}(A_n)=\infty,
> $$
>
> onda je
>
> $$
> \mathbb{P}(\{A_n\text{ b.m.p.}\})=1.
> $$

> [!dokaz]- Dokaz.
> Definirajmo niz događaja $(B_n)_{n\in\mathbb{N}}$ formulom
>
> $$
> B_n=\bigcup_{k=n}^{\infty}A_k.
> $$
>
> To je **padajući niz događaja**, pa po neprekidnosti vjerojatnosti imamo
>
> $$
> \mathbb{P}\left(\bigcap_{n=1}^{\infty}\bigcup_{k=n}^{\infty}A_k\right)
> =
> \mathbb{P}\left(\bigcap_{n=1}^{\infty}B_n\right)
> =
> \lim_{n\to\infty}\mathbb{P}(B_n).
> $$
>
> Dakle,
>
> $$
> \mathbb{P}\left(\bigcap_{n=1}^{\infty}\bigcup_{k=n}^{\infty}A_k\right)=1
> \iff
> \lim_{n\to\infty}\mathbb{P}(B_n)=1.
> $$
>
> Budući da je $(B_n)_n$ padajući niz, vrijedi
>
> $$
> \lim_{n\to\infty}\mathbb{P}(B_n)=1
> \iff
> \mathbb{P}(B_n)=1
> \quad(\forall n\in\mathbb{N}).
> $$
>
> Slijedi
>
> $$
> \mathbb{P}\left(\bigcap_{n=1}^{\infty}\bigcup_{k=n}^{\infty}A_k\right)=1
> \iff
> \mathbb{P}(B_n^c)=0
> \quad(\forall n\in\mathbb{N}).
> $$
>
> Prelazimo na komplement kako bismo u dokazu mogli iskoristiti **nezavisnost događaja $A_k$, odnosno $A_k^c$**.
>
> Računamo za proizvoljan fiksan $n\in\mathbb{N}$:
>
> $$
> \begin{aligned}
> \mathbb{P}(B_n^c)
> &=\mathbb{P}\left(\left(\bigcup_{k=n}^{\infty}A_k\right)^c\right)\\
> &=\mathbb{P}\left(\bigcap_{k=n}^{\infty}A_k^c\right)\\
> &=\prod_{k=n}^{\infty}\mathbb{P}(A_k^c)\\
> &=\lim_{m\to\infty}\prod_{k=n}^{m}\mathbb{P}(A_k^c)\\
> &=\lim_{m\to\infty}\prod_{k=n}^{m}(1-\mathbb{P}(A_k)).
> \end{aligned}
> $$
>
> Iskoristimo činjenicu
>
> $$
> 1-x\le e^{-x},\qquad \forall x\ge 0.
> $$
>
> Dobivamo
>
> $$
> \begin{aligned}
> \mathbb{P}(B_n^c)
> &\le \lim_{m\to\infty}\prod_{k=n}^{m}e^{-\mathbb{P}(A_k)}\\
> &=\lim_{m\to\infty}e^{-\sum_{k=n}^{m}\mathbb{P}(A_k)}\\
> &=e^{-\lim_{m\to\infty}\sum_{k=n}^{m}\mathbb{P}(A_k)}.
> \end{aligned}
> $$
>
> Prema pretpostavci,
>
> $$
> \lim_{m\to\infty}\sum_{k=n}^{m}\mathbb{P}(A_k)=\infty.
> $$
>
> Stoga smo dokazali
>
> $$
> \mathbb{P}(B_n^c)\le e^{-\infty}=0.
> $$
>
> Kako je $\mathbb{P}$ nenegativna, vrijedi
>
> $$
> 0\le\mathbb{P}(B_n^c)\le 0
> \implies
> \boxed{\mathbb{P}(B_n^c)=0}.
> $$
>
> Time smo dokazali traženu tvrdnju.

Druga Borel–Cantellijeva lema je svojevrsni obrat prve, ali uz **dodatnu pretpostavku nezavisnosti**.

Vrijedi

$$
\sum_{n=1}^{\infty}\mathbb{P}(A_n)=\infty
\qquad\text{i}\qquad
(A_n)\text{ nezavisni}
$$

povlači

$$
\mathbb{P}(\{A_n\text{ b.m.p.}\})=1.
$$

Dakle:

**Ako su događaji nezavisni i njihove se vjerojatnosti zbrajaju u beskonačno, tada će se gotovo sigurno beskonačno mnogo događaja $A_n$ dogoditi.**