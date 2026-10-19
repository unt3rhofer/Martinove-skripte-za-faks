# 1.2. Vjerojatnosni prostor $(\Omega,\mathcal F,P)$
**Vjerojatnosni prostor** je matematički model za dani pokus.
Sastoji se od tri komponente:

(i) skup svih mogućih ishoda pokusa, $\Omega$
- elemente iz $\Omega$ zovemo **elementarni događaji**
- $\Omega$ nazivamo **prostor el. događaja**

(ii) familija podskupova od $\Omega$, $\mathcal F$
$$
\mathcal F\subseteq\mathcal P(\Omega)
$$
- elemente iz $\mathcal F$ zovemo **događaji**

(iii) vjerojatnost koju pridružujemo svakom događaju, $P(\cdot)$
## 1.2.1. Događaji

Događaj $A\in\mathcal F$ se **dogodio** ako se dogodio ishod $\omega\in\Omega$ takav da je $\omega\in A$.

Za $A,B\in\mathcal F$:

> [!istaknuto] Operacije nad događajima
> $$
> \begin{aligned}
> A^c &\rightarrow \text{„$A$ se nije dogodio”} \\
> A\cup B &\rightarrow \text{„dogodio se $A$ ili $B$”} \\
> A\cap B &\rightarrow \text{„dogodili su se $A$ i $B$”} \\
> A\setminus B &\rightarrow \text{„dogodio se $A$, ali ne i $B$”} \\
> A\subseteq B &\rightarrow \text{„ako se dogodio $A$, dogodio se i $B$”}
> \end{aligned}
> $$

> [!istaknuto] Posebni događaji
> $$
> \begin{aligned}
> A\cap B=\varnothing &\rightarrow \text{„$A$ i $B$ ne mogu se istovremeno dogoditi”} \\
> \Omega &\rightarrow \text{„siguran događaj”} \\
> \varnothing &\rightarrow \text{„nemoguć događaj”}
> \end{aligned}
> $$

> [!definicija] $\sigma$-algebra
> Neka je $\mathcal F$ familija podskupova od $\Omega$.
>
> $\mathcal F$ je $\sigma$-algebra ako:
>
> (i) *$\Omega$ pripada familiji $\mathcal F$:*
>
> $$
> \Omega\in\mathcal F
> $$
>
> (ii) *zatvorenost na komplement:*
>
> $$
> A\in\mathcal F\Rightarrow A^c\in\mathcal F
> $$
>
> (iii) *zatvorenost na prebrojive unije:*
>
> $$
> (\forall j\in\mathbb N)\ A_j\in\mathcal F
> \Rightarrow
> \bigcup_{j\in\mathbb N}A_j\in\mathcal F
> $$


### Napomena 1.3.
> [!istaknuto] Svojstva $\sigma$-algebre
> Ako je $\mathcal F$ $\sigma$-algebra, vrijedi i:
>
> (a) *$\mathcal F$ sadrži prazan skup:*
>
> $$
> \varnothing\in\mathcal F
> $$
>
> (b) *zatvorenost na konačne unije:*  
> ako su $A_1,\ldots,A_n\in\mathcal F$, onda
>
> $$
> \bigcup_{j=1}^{n}A_j\in\mathcal F.
> $$
>
> (c) *zatvorenost na prebrojive presjeke:*  
> ako je $A_j\in\mathcal F$ za sve $j\in\mathbb N$, onda
>
> $$
> \bigcap_{j=1}^{\infty}A_j\in\mathcal F.
> $$

> [!dokaz]- Dokaz
> **(a)**
>
> $$
> \Omega\in\mathcal F
> \Rightarrow
> \Omega^c\in\mathcal F
> \Rightarrow
> \varnothing\in\mathcal F.
> $$
>
> **(b)**  
> Neka su $A_1,\ldots,A_n\in\mathcal F$.
>
> Definiramo
>
> $$
> B_j=
> \begin{cases}
> A_j, & j\leq n,\\
> \varnothing, & j>n.
> \end{cases}
> $$
>
> Tada je $B_j\in\mathcal F$ za sve $j\in\mathbb N$, pa
>
> $$
> \bigcup_{j=1}^{\infty}B_j\in\mathcal F
> \Rightarrow
> \bigcup_{j=1}^{n}A_j\in\mathcal F.
> $$
>
> **(c)**  
> Ako je $A_j\in\mathcal F$ za sve $j\in\mathbb N$, onda
>
> $$
> A_j^c\in\mathcal F
> \qquad
> \forall j\in\mathbb N.
> $$
>
> Stoga
>
> $$
> \bigcup_{j=1}^{\infty}A_j^c\in\mathcal F.
> $$
>
> Zatvorenost na komplement i De Morganov zakon daju
>
> $$
> \left(\bigcup_{j=1}^{\infty}A_j^c\right)^c\in\mathcal F
> \Rightarrow
> \bigcap_{j=1}^{\infty}A_j\in\mathcal F.
> $$

## 1.2.2. Definicija vjerojatnosti i osnovna svojstva

> [!definicija] Kolmogorovljevi aksiomi
> Vjerojatnost na $(\Omega,\mathcal F)$ je svaka funkcija
>
> $$
> P:\mathcal F\to\mathbb R
> $$
>
> koja zadovoljava sljedeća tri aksioma:
>
> **(A1)** *nenegativnost:*
>
> $$
> (\forall A\in\mathcal F)\qquad P(A)\geq0
> $$
>
> **(A2)** *normiranost:*
>
> $$
> P(\Omega)=1
> $$
>
> **(A3)** *$\sigma$-aditivnost:*  
> ako su $A_1,A_2,\ldots\in\mathcal F$ u parovima disjunktni, onda
>
> $$
> P\left(\bigcup_{j=1}^{\infty}A_j\right)
> =
> \sum_{j=1}^{\infty}P(A_j).
> $$


### Napomena 1.6.
> [!istaknuto] Svojstva vjerojatnosti
> (i)
>
> $$
> P(\varnothing)=0,
> \qquad
> P(A)\in[0,1].
> $$
>
> (ii) *$P$ je konačno aditivna:*  
> ako su $A_1,\ldots,A_n\in\mathcal F$ u parovima disjunktni, onda
>
> $$
> P\left(\bigcup_{j=1}^{n}A_j\right)
> =
> \sum_{j=1}^{n}P(A_j).
> $$

> [!dokaz]- Dokaz.
> Iz aksioma (A1)–(A3) najprije pokažimo da je
>
> $$
> \mathbb{P}(\emptyset)=0.
> $$
>
> Uzmimo
>
> $$
> A_1=\Omega,
> \qquad
> A_j=\emptyset,\quad j\ge 2.
> $$
>
> Događaji $A_1,A_2,\ldots$ su u parovima disjunktni, pa iz $\sigma$-aditivnosti slijedi
>
> $$
> \begin{aligned}
> 1
> &=
> \mathbb{P}(\Omega)
> =
> \mathbb{P}\left(\bigcup_{j=1}^{\infty}A_j\right)
> \\
> &=
> \sum_{j=1}^{\infty}\mathbb{P}(A_j)
> =
> \mathbb{P}(\Omega)+\sum_{j=2}^{\infty}\mathbb{P}(\emptyset)
> \\
> &=
> 1+\sum_{j=2}^{\infty}\mathbb{P}(\emptyset).
> \end{aligned}
> $$
>
> Budući da je $\mathbb{P}(\emptyset)\ge 0$ po (A1), mora vrijediti
>
> $$
> \mathbb{P}(\emptyset)=0.
> $$
>
> Sada pokažimo konačnu aditivnost. Neka su $A_1,\ldots,A_n\in\mathcal F$ u parovima disjunktni. Definiramo
>
> $$
> B_j=
> \begin{cases}
> A_j, & j\le n,\\
> \emptyset, & j>n.
> \end{cases}
> $$
>
> Tada su $B_1,B_2,\ldots$ u parovima disjunktni, pa iz (A3) slijedi
>
> $$
> \begin{aligned}
> \mathbb{P}\left(\bigcup_{j=1}^{n}A_j\right)
> &=
> \mathbb{P}\left(\bigcup_{j=1}^{\infty}B_j\right)
> \\
> &=
> \sum_{j=1}^{\infty}\mathbb{P}(B_j)
> \\
> &=
> \sum_{j=1}^{n}\mathbb{P}(A_j)
> +
> \sum_{j=n+1}^{\infty}\mathbb{P}(\emptyset)
> \\
> &=
> \sum_{j=1}^{n}\mathbb{P}(A_j).
> \end{aligned}
> $$
>
> Dakle, $\mathbb{P}$ je konačno aditivna.
>
> Konačno, za proizvoljan $A\in\mathcal F$ vrijedi
>
> $$
> \Omega=A\cup A^c,
> \qquad
> A\cap A^c=\emptyset.
> $$
>
> Prema konačnoj aditivnosti,
>
> $$
> 1
> =
> \mathbb{P}(\Omega)
> =
> \mathbb{P}(A)+\mathbb{P}(A^c).
> $$
>
> Kako je po (A1) $\mathbb{P}(A^c)\ge 0$, slijedi
>
> $$
> \mathbb{P}(A)\le 1.
> $$
>
> S druge strane, opet po (A1), $\mathbb{P}(A)\ge 0$. Prema tome,
>
> $$
> \mathbb{P}(A)\in[0,1].
> $$
### Primjer 1.7. — Laplaceov model

Ako je $|\Omega|<\infty$ te su zbog simetrije svi $\omega\in\Omega$ jednako vjerojatni:

> [!istaknuto] Laplaceov model
> $$
> P(A)=\frac{|A|}{|\Omega|},
> \qquad A\in\mathcal F.
> $$

Pri tome uzimamo

$$
\mathcal F=\mathcal P(\Omega).
$$

### Primjer 1.8. — Geometrijska vjerojatnost

> [!istaknuto] Geometrijska vjerojatnost
> $$
> P(A)=\frac{\lambda(A)}{\lambda(\Omega)},
> \qquad A\in\mathcal F.
> $$

- $\Omega$ $\rightarrow$ neki skup s površinom
- $\mathcal F$ $\rightarrow$ Borelova $\sigma$-algebra

### Propozicija 1.9.

> [!istaknuto] Osnovna svojstva vjerojatnosti
> **(a)**
>
> $$
> P(\varnothing)=0.
> $$
>
> **(b)** $P$ je konačno aditivna.
>
> **(c)**
>
> $$
> P(B\setminus A)
> =
> P(B)-P(A\cap B).
> $$
>
> **(d)** Ako je $A\subseteq B$, onda
>
> $$
> P(B\setminus A)=P(B)-P(A)
> $$
>
> i
>
> $$
> P(A)\leq P(B).
> $$
>
> **(e)**
>
> $$
> P(A^c)=1-P(A).
> $$
>
> **(f)** Za sve $A,B\in\mathcal F$ vrijedi
>
> $$
> P(A\cup B)
> =
> P(A)+P(B)-P(A\cap B).
> $$

> [!dokaz]- Dokaz
> **(a)** Neka je
>
> $$
> A_j=\varnothing,\qquad \forall j\in\mathbb N.
> $$
>
> Stavimo
>
> $$
> p:=P(\varnothing).
> $$
>
> Tada iz $\sigma$-aditivnosti slijedi
>
> $$
> \begin{aligned}
> p
> &=
> P(\varnothing)\\
> &=
> P\left(\bigcup_{j=1}^{\infty}A_j\right)\\
> &=
> \sum_{j=1}^{\infty}P(\varnothing)\\
> &=
> \sum_{j=1}^{\infty}p.
> \end{aligned}
> $$
>
> Dakle,
>
> $$
> p=0.
> $$
>
> **(b)** Neka su $A_1,\ldots,A_n\in\mathcal F$ u parovima disjunktni događaji.
>
> Definiramo
>
> $$
> B_j=
> \begin{cases}
> A_j, & j\leq n,\\
> \varnothing, & j>n.
> \end{cases}
> $$
>
> Zbog $\sigma$-aditivnosti vrijedi
>
> $$
> \begin{aligned}
> P\left(\bigcup_{j=1}^{n}A_j\right)
> &=
> P\left(\bigcup_{j=1}^{\infty}B_j\right)\\
> &=
> \sum_{j=1}^{\infty}P(B_j)\\
> &=
> \sum_{j=1}^{n}P(A_j).
> \end{aligned}
> $$
>
> **(c)** Vrijedi
>
> $$
> B=(B\setminus A)\cup(A\cap B),
> $$
>
> pri čemu su skupovi $B\setminus A$ i $A\cap B$ disjunktni.
>
> Zato
>
> $$
> P(B)=P(B\setminus A)+P(A\cap B),
> $$
>
> pa
>
> $$
> P(B\setminus A)=P(B)-P(A\cap B).
> $$
>
> **(d)** Ako je $A\subseteq B$, tada je
>
> $$
> A\cap B=A.
> $$
>
> Prema (c),
>
> $$
> P(B\setminus A)=P(B)-P(A)\geq0,
> $$
>
> pa slijedi
>
> $$
> P(A)\leq P(B).
> $$
>
> **(e)** Budući da je
>
> $$
> A^c=\Omega\setminus A,
> $$
>
> prema (c) vrijedi
>
> $$
> \begin{aligned}
> P(A^c)
> &=
> P(\Omega)-P(A)\\
> &=
> 1-P(A).
> \end{aligned}
> $$
>
> **(f)** Uniju možemo zapisati kao disjunktnu uniju
>
> $$
> A\cup B
> =
> (A\cap B)\cup(A\setminus B)\cup(B\setminus A).
> $$
>
> Zato
>
> $$
> \begin{aligned}
> P(A\cup B)
> &=
> P(A\cap B)+P(A\setminus B)+P(B\setminus A)\\
> &=
> P(A\cap B)
> +P(A)-P(A\cap B)
> +P(B)-P(A\cap B)\\
> &=
> P(A)+P(B)-P(A\cap B).
> \end{aligned}
> $$



## 1.2.3. Diskretan vjerojatnosni prostor

Neka je $\Omega$ konačan ili prebrojiv, $\mathcal F=\mathcal P(\Omega)$ te $P$ vjerojatnost na $(\Omega,\mathcal F)$.

Za svaki $A\in\mathcal F$ vrijedi

> [!bitnatvrdnja] Vjerojatnost događaja u diskretnom prostoru
> $$
> \begin{aligned}
> P(A)
> &=
> P\left(\bigcup_{\omega\in A}\{\omega\}\right)\\
> &=
> \sum_{\omega\in A}P(\{\omega\}).
> \end{aligned}
> $$

> [!istaknuto]
> Svaka vjerojatnost na diskretnom vjerojatnosnom prostoru u potpunosti je određena vrijednostima
>
> $$
> P(\{\omega\}),\qquad \omega\in\Omega.
> $$


### Primjer 1.11.

Ako je $\Omega$ prebrojivo beskonačan, nije moguće uspostaviti Laplaceov model.

To slijedi iz nenegativnosti vjerojatnosti i činjenice da mora vrijediti

$$
\sum_{i=1}^{\infty}P(\{\omega_i\})=1,
$$

pa ne postoji vjerojatnost $P$ na $(\Omega,\mathcal F)$ takva da je

$$
P(\{\omega_i\})=P(\{\omega_j\})
$$

za sve $i,j$.


### Propozicija 1.12.

> [!istaknuto]
> Neka je
>
> $$
> \Omega=\{\omega_1,\ldots,\omega_n\},
> \qquad n\in\mathbb N,
> $$
>
> te
>
> $$
> \mathcal F=\mathcal P(\Omega).
> $$
>
> Za svaki vektor
>
> $$
> p=(p_1,\ldots,p_n)
> $$
>
> koji zadovoljava
>
> $$
> p_i\geq0,
> \qquad i=1,\ldots,n,
> $$
>
> i
>
> $$
> \sum_{i=1}^{n}p_i=1,
> $$
>
> postoji vjerojatnost $P$ na $(\Omega,\mathcal F)$ takva da
>
> $$
> P(\{\omega_i\})=p_i,
> \qquad i=1,\ldots,n.
> $$

> [!istaknuto]
> Na konačnom prostoru dovoljno je zadati vjerojatnosti pojedinačnih ishoda.
>
> Time su automatski određene vjerojatnosti svih događaja.


# 1.3. Laplaceov model
## 1.3.1. Formula uključivanja-isključivanja
### Propozicija 1.16 

Neka je $n\in\mathbb N$ i $A_1,\ldots,A_n\in\mathcal F$. Tada

>[!bitnatvrdnja] FUI
>$$
>P\left(\bigcup_{i=1}^{n}A_i\right)
>=
>\sum_{i=1}^{n}P(A_i)
>-\sum_{1\le i<j\le n}P(A_i\cap A_j)
>+\cdots
>+(-1)^{n+1}P(A_1\cap\cdots\cap A_n).
>$$

> [!dokaz]- Dokaz
> Dokazujemo indukcijom po $n$.
>
> Za $n=1$:
>
> $$
> P(A_1)=P(A_1),
> $$
>
> pa istaknuto očito vrijedi.
>
> Za $n=2$:
>
> $$
> P(A_1\cup A_2)
> =
> P(A_1)+P(A_2)-P(A_1\cap A_2),
> $$
>
> što je poznata formula uključivanja-isključivanja za dva događaja.
>
> Pretpostavimo sada da istaknuto vrijedi za $n$ događaja. Za $n+1$ imamo
>
> $$
> \begin{aligned}
> P\left(\bigcup_{i=1}^{n+1}A_i\right)
> &=
> P\left(\left(\bigcup_{i=1}^{n}A_i\right)\cup A_{n+1}\right)\\
> &=
> P\left(\bigcup_{i=1}^{n}A_i\right)
> +P(A_{n+1})
> -P\left(\bigcup_{i=1}^{n}(A_i\cap A_{n+1})\right).
> \end{aligned}
> $$
>
> Na prvi član primijenimo pretpostavku indukcije:
>
> $$
> \begin{aligned}
> P\left(\bigcup_{i=1}^{n+1}A_i\right)
> &=
> \sum_{i=1}^{n}P(A_i)
> -\sum_{1\le i<j\le n}P(A_i\cap A_j)
> +\cdots
> +(-1)^{n+1}P(A_1\cap\cdots\cap A_n)\\
> &\qquad
> +P(A_{n+1})
> -P\left(\bigcup_{i=1}^{n}B_i\right),
> \end{aligned}
> $$
>
> gdje je
>
> $$
> B_i:=A_i\cap A_{n+1}.
> $$
>
> Na događaje $B_1,\ldots,B_n$ ponovno primijenimo pretpostavku indukcije:
>
> $$
> P\left(\bigcup_{i=1}^{n}B_i\right)
> =
> \sum_{i=1}^{n}P(B_i)
> -\sum_{1\le i<j\le n}P(B_i\cap B_j)
> +\cdots
> +(-1)^{n+1}P(B_1\cap\cdots\cap B_n).
> $$
>
> Po definiciji $B_i=A_i\cap A_{n+1}$, pa
>
> $$
> \begin{aligned}
> P\left(\bigcup_{i=1}^{n}B_i\right)
> &=
> \sum_{i=1}^{n}P(A_i\cap A_{n+1})\\
> &\quad-
> \sum_{1\le i<j\le n}
> P(A_i\cap A_j\cap A_{n+1})\\
> &\quad+\cdots
> +(-1)^{n+1}P(A_1\cap\cdots\cap A_n\cap A_{n+1}).
> \end{aligned}
> $$
>
> Uvrštavanjem dobivamo
>
> $$
> \begin{aligned}
> P\left(\bigcup_{i=1}^{n+1}A_i\right)
> &=
> \sum_{i=1}^{n}P(A_i)+P(A_{n+1})\\
> &\quad-
> \left[
> \sum_{1\le i<j\le n}P(A_i\cap A_j)
> +
> \sum_{i=1}^{n}P(A_i\cap A_{n+1})
> \right]\\
> &\quad+\cdots
> +(-1)^{n+2}P(A_1\cap\cdots\cap A_{n+1})\\
> &=
> \sum_{i=1}^{n+1}P(A_i)
> -\sum_{1\le i<j\le n+1}P(A_i\cap A_j)
> +\cdots
> +(-1)^{n+2}P(A_1\cap\cdots\cap A_{n+1}).
> \end{aligned}
> $$
>
> To je upravo formula uključivanja-isključivanja za $n+1$ događaja.
>**Raspis s tročlanim presjecima**
> $$
> \begin{aligned}
> P\left(\bigcup_{i=1}^{n+1}A_i\right)
> &=
> \sum_{i=1}^{n}P(A_i)+P(A_{n+1})\\
> &\quad-
> \left[
> \sum_{1\le i<j\le n}P(A_i\cap A_j)
> +
> \sum_{i=1}^{n}P(A_i\cap A_{n+1})
> \right]\\
> &\quad+
> \left[
> \sum_{1\le i<j<k\le n}P(A_i\cap A_j\cap A_k)
> +
> \sum_{1\le i<j\le n}P(A_i\cap A_j\cap A_{n+1})
> \right]\\
> &\quad+\cdots
> +(-1)^{n+2}P(A_1\cap\cdots\cap A_{n+1})\\
> &=
> \sum_{i=1}^{n+1}P(A_i)
> -\sum_{1\le i<j\le n+1}P(A_i\cap A_j)
> +\sum_{1\le i<j<k\le n+1}P(A_i\cap A_j\cap A_k)
> +\cdots
> +(-1)^{n+2}P(A_1\cap\cdots\cap A_{n+1}).
> \end{aligned}
> $$


# 1.4. Nizovi događaja
## 1.4.1. Subaditivnost
### Propozicija 1.18 — subaditivnost vjerojatnosti

Neka je $(A_j)_{j\in\mathbb N}$ niz događaja iz $\mathcal F$. Tada vrijedi

>[!istaknuto] $\sigma$-subaditivnost
>$$
>P\left(\bigcup_{j=1}^{\infty} A_j\right)
>\le
>\sum_{j=1}^{\infty} P(A_j).
>$$

To svojstvo nazivamo **$\sigma$-subaditivnost**.

Specijalno, za svaki $n\in\mathbb N$ vrijedi

>[!istaknuto] konačna subaditivnost
>$$
>P\left(\bigcup_{j=1}^{n} A_j\right)
>\le
>\sum_{j=1}^{n} P(A_j).
>$$

To svojstvo nazivamo **konačna subaditivnost**.

> [!dokaz]- Dokaz
> Definiramo novi niz $(B_j)_{j\in\mathbb N}$ po parovima disjunktnih događaja. Ideja je da iz svakog događaja $A_j$ uklonimo sve dijelove koji su se već pojavili u prethodnim događajima.
>
> Stavimo
>
> $$
> B_1:=A_1,
> $$
>
> a za $j\ge 2$
>
> $$
> B_j
> :=
> A_j\setminus\bigcup_{i=1}^{j-1}A_i
> =
> A_j\setminus(A_1\cup\cdots\cup A_{j-1}).
> $$
>
> Vrijedi $B_j\in\mathcal F$ za svaki $j\in\mathbb N$. Naime,
>
> $$
> \bigcup_{i=1}^{j-1}A_i\in\mathcal F
> $$
>
> jer je $\mathcal F$ zatvorena na konačne unije, pa je i
>
> $$
> \left(\bigcup_{i=1}^{j-1}A_i\right)^c\in\mathcal F.
> $$
>
> Stoga
>
> $$
> B_j
> =
> A_j\cap
> \left(\bigcup_{i=1}^{j-1}A_i\right)^c
> \in\mathcal F,
> $$
>
> jer je $\mathcal F$ zatvorena i na konačne presjeke.
>
> Vrijede sljedeće tvrdnje:
>
> **(a)**
> $$
> \begin{aligned}
> \bigcup_{j=1}^{n} B_j
> &=
> \bigcup_{j=1}^{n} A_j,
> \qquad n\in\mathbb N,\\[6pt]
> \bigcup_{j=1}^{\infty} B_j
> &=
> \bigcup_{j=1}^{\infty} A_j.
> \end{aligned}
> $$
> **(b)**
> $$
> B_j\subseteq A_j,
> \qquad j\in\mathbb N.
> $$
> **(c)** Događaji $(B_j)_{j\in\mathbb N}$ su po parovima disjunktni.
>
> Iz $\sigma$-aditivnosti i monotonosti vjerojatnosti sada slijedi
>
> $$
> \begin{aligned}
> P\left(\bigcup_{j=1}^{\infty}A_j\right)
> &\overset{(a)}{=}
> P\left(\bigcup_{j=1}^{\infty}B_j\right)\\
> &\overset{(c)}{=}
> \sum_{j=1}^{\infty}P(B_j)\\
> &\overset{(b)}{\le}
> \sum_{j=1}^{\infty}P(A_j).
> \end{aligned}
> $$
> Time je dokazana $\sigma$-subaditivnost. Konačna subaditivnost dokazuje se potpuno analogno, koristeći konačnu aditivnost.
>
>**Skica konstrukcije niza $(B_j)_{j \in \mathbb{N}}$**
>![](file:///home/martin/Documents/Obsidian/Martin/90%20Attachments/prop118.png.png)


## 1.4.2. Neprekidnost vjerojatnosti

> [!definicija] Rastući i padajući niz događaja
> Za niz događaja $A_1,A_2,\ldots\in\mathcal F$ kažemo da je
> 
> - **rastući** ako je $A_n\subseteq A_{n+1}$ za sve $n\in\mathbb N$,
> - **padajući** ako je $A_{n+1}\subseteq A_n$ za sve $n\in\mathbb N$.


### Propozicija 1.22. (Neprekidnost vjerojatnosti s obzirom na rastući/padajući niz događaja)

(a) Ako je niz $A_1,A_2,\ldots\in\mathcal F$ rastući, vrijedi

> [!bitnatvrdnja] neprekidnost, rastući
> $$
> P\left(\bigcup_{j=1}^{\infty}A_j\right)
> =
> \lim_{n\to\infty}P(A_n).
> $$

(b) Ako je niz $A_1,A_2,\ldots\in\mathcal F$ padajući, vrijedi

> [!bitnatvrdnja] neprekidnost, padajući
> $$
> P\left(\bigcap_{j=1}^{\infty}A_j\right)
> =
> \lim_{n\to\infty}P(A_n).
> $$

> [!dokaz]- Dokaz
> **(a)** Konstruiramo niz $B_1,B_2,\ldots\in\mathcal F$ kao u Propoziciji 1.18.
>
> Stavimo
>
> $$
> B_1:=A_1,
> $$
>
> a za $j\ge 2$
>
> $$
> B_j
> :=
> A_j\setminus\bigcup_{i=1}^{j-1}A_i
> =
> A_j\setminus(A_1\cup\cdots\cup A_{j-1}).
> $$
>
> Budući da je $A_j\subseteq A_{j+1}$, za sve $n\in\mathbb N$ imamo
>
> $$
> \bigcup_{j=1}^{n}B_j
> =
> \bigcup_{j=1}^{n}A_j
> =
> A_n.
> $$
>
> $B_1,B_2,\ldots$ su u parovima disjunktni događaji pa vrijedi:
>
> $$
> \begin{aligned}
> P\left(\bigcup_{j=1}^{\infty}A_j\right)
> &=
> P\left(\bigcup_{j=1}^{\infty}B_j\right)
> =
> \sum_{j=1}^{\infty}P(B_j)\\
> &=
> \lim_{n\to\infty}\sum_{j=1}^{n}P(B_j)\\
> &=
> \lim_{n\to\infty}P\left(\bigcup_{j=1}^{n}B_j\right)\\
> &=
> \lim_{n\to\infty}P(A_n).
> \end{aligned}
> $$
> **(b)** Budući da je niz $(A_n)_{n\in\mathbb N}$ padajući, niz $(A_n^c)_{n\in\mathbb N}$ je rastući.
>
> Po (a) vrijedi
>
> $$
> P\left(\bigcup_{j=1}^{\infty}A_j^c\right)
> =
> \lim_{n\to\infty}P(A_n^c).
> $$
>
> Po De Morganovom zakonu i svojstvu komplementa,
>
> $$
> \begin{aligned}
> 1-P\left(\bigcap_{j=1}^{\infty}A_j\right)
> &=
> P\left(\left(\bigcap_{j=1}^{\infty}A_j\right)^c\right)\\
> &=
> P\left(\bigcup_{j=1}^{\infty}A_j^c\right)\\
> &=
> \lim_{n\to\infty}P(A_n^c)\\
> &=
> \lim_{n\to\infty}\left(1-P(A_n)\right)\\
> &=
> 1-\lim_{n\to\infty}P(A_n).
> \end{aligned}
> $$
>
> Dakle,
>
> $$
> P\left(\bigcap_{j=1}^{\infty}A_j\right)
> =
> \lim_{n\to\infty}P(A_n).
> $$



## 1.4.3. $(\Omega, \mathcal{F}, \mathbb{P})$ za beskonačan niz bacanja novčića


> [!istaknuto] Beskonačan niz bacanja novčića
> $$
> \Omega
> =
> \{\omega=(\omega_1,\omega_2,\ldots):\omega_i=P\text{ ili }G,\ i\in\mathbb N\}
> =
> \{P,G\}^{\mathbb N}.
> $$
>
> Elementarni događaji su svi beskonačni nizovi simbola $P$ i $G$.
> $\Omega$ je skup svih mogućih beskonačnih nizova pisama i glava.


Uočimo da je $\Omega$ **neprebrojiv** skup!
=> nije dovoljno zadati $\mathbb(P)(\omega)$ za svaki niz $\omega$

Motivacija za uvođenje beskonačnog niza bacanja novčića je mogućnost preciznog opisivanja događaja koji ovise o proizvoljno velikom broju bacanja.

Kažemo da događaj $A$ **ovisi o prvih $n$ bacanja** ako za odluku je li se $A$ dogodio trebamo pogledati samo prvih $n$ rezultata; sve nakon toga je nebitno. 
Na primjer, neka je 
$$ A=\{\text{točno jedno pismo u prva 3 bacanja}\}. $$Tada $A$ ovisi o prva 3 bacanja jer nakon što znamo prva tri rezultata, odmah znamo je li se $A$ dogodio. Povoljni početci su $$ PGG,\qquad GPG,\qquad GGP. $$ Nakon toga može slijediti bilo što. 
Formalni zapis $$ A=\{(a_1,a_2,\ldots)\in\Omega:(a_1,\ldots,a_n)\in A_n\} $$
znači: pogledamo prvih $n$ simbola; ako taj početak pripada skupu dopuštenih početaka $A_n$, cijeli beskonačni niz pripada događaju $A$.

Ako je $A_n=\{\text{u }n\text{-tom bacanju palo je pismo}\}$, tada

$$
A_1\cup A_2\cup A_3
$$

predstavlja događaj da je pismo palo barem jednom u prva tri bacanja.

S druge strane,

$$
A_1^c\cap A_2^c\cap A_3^c
$$

predstavlja događaj da u prva tri bacanja nije palo nijedno pismo.

Analogno,

$$
\bigcap_{n=1}^{\infty}A_n^c
$$

predstavlja događaj da pismo nije palo ni u jednom bacanju.