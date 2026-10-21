---
title: 3 Diskretne slučajne varijable
---
## Definicija i osnovna svojstva

> [!definicija] Slučajna varijabla
> Slučajna varijabla je svaka funkcija
>
> $$
> X:\Omega\to\mathbb R
> $$
>
> takva da vrijedi
>
> $$
> \{X\le x\}\in\mathcal F,
> \qquad \forall x\in\mathbb R,
> $$
>
> pri čemu je
>
> $$
> \{X\le x\}
> :=
> \{\omega\in\Omega:X(\omega)\le x\}
> =
> X^{-1}((-\infty,x]).
> $$

> [!objasnjenje] Objašnjenje
> Intuitivno, slučajna varijabla svakom ishodu $\omega\in\Omega$ pridružuje broj $X(\omega)$. Uvjet $\{X\le x\}\in\mathcal F$ osigurava da je pitanje „je li $X\le x$?” događaj kojem možemo pridružiti vjerojatnost.

Za [[Slucajna varijabla|slučajnu varijablu]] $X:\Omega\to\mathbb R$, neka je

$$
D_X:=\operatorname{Im}(X)=\{X(\omega):\omega\in\Omega\},
$$

skup svih vrijednosti koje $X$ može poprimiti.

Za [[Slucajna varijabla|slučajnu varijablu]] $X:\Omega \to \mathbb{R}$ kažmo da je je **diskretna** ako je $D_{X}$ konačan ili prebrojiv.

## Distribucija diskretne slučajne varijable

> [!definicija] Distribucija diskretne slučajne varijable
> Za diskretnu slučajnu varijablu $X$, skup
>
> $$
> D_X=\{a_i:i\in I\}
> $$
>
> zajedno s vjerojatnostima
>
> $$
> p_i:=\mathbb P(X=a_i),\qquad i\in I,
> $$
>
> zovemo **distribucijom (ili razdiobom) slučajne varijable $X$**.
>
> Distribuciju često zapisujemo u obliku tablice
>
> $$
> X\sim
> \begin{pmatrix}
> a_1 & a_2 & \cdots \\
> p_1 & p_2 & \cdots
> \end{pmatrix}.
> $$

Distribucija slučajne varijable $X$ inducira vjerojatnost na njezinim mogućim vrijednostima: za $B\subseteq\mathbb R$ vrijedi

$$
\mathbb P(X\in B)=\sum_{a_i\in B}p_i.
$$

Zato je za većinu pitanja o $X$ dovoljna njegova distribucija, bez poznavanja konkretnog vjerojatnosnog prostora na kojem je $X$ definiran.

> [!definicija] Vjerojatnosna funkcija mase
> Za diskretnu slučajnu varijablu $X$ definiramo njenu **vjerojatnosnu funkciju mase** ili **diskretnu (vjerojatnosnu) funkciju gustoće**
>
> $$
> f_X:\mathbb R\to[0,1]
> $$
>
> sa
>
> $$
> f_X(x):=\mathbb P(X=x),\qquad x\in\mathbb R.
> $$

Očito vrijedi

$$
X\sim
\begin{pmatrix}
a_1 & a_2 & \cdots \\
p_1 & p_2 & \cdots
\end{pmatrix}
\quad \Longleftrightarrow \quad
f_X(x)=
\begin{cases}
p_i, & \text{ako }x=a_i\text{ za neki }i\in I,\\
0, & \text{inače}.
\end{cases}
$$



> [!istaknuto] Postojanje slučajne varijable sa zadanom distribucijom
> Neka je $D=\{a_i:i\in I\}\subseteq\mathbb{R}$ konačan ili prebrojiv skup i neka je $(p_i:i\in I)$ proizvoljna distribucija na $D$.
>
> Tada postoji vjerojatnosni prostor $(\Omega,\mathcal{F},\mathbb{P})$ i diskretna slučajna varijabla $X:\Omega\to D$ čija je distribucija upravo $(p_i:i\in I)$, odnosno
>
> $$
> \boxed{\mathbb{P}(X=a_i)=p_i,\quad \forall i\in I.}
> $$

> [!dokaz]- Dokaz.
> **Cilj dokaza:** Za proizvoljnu distribuciju $(p_i:i\in I)$ na konačnom ili prebrojivom skupu $D=\{a_i:i\in I\}$ želimo konstruirati:
>
> **(i)** Vjerojatnosni prostor $(\Omega,\mathcal{F},\mathbb{P})$.
>
> **(ii)** Diskretnu slučajnu varijablu $X:\Omega\to D$ takvu da vrijedi
>
> $$
> \mathbb{P}(X=a_i)=p_i,\quad \forall i\in I.
> $$
>
> **Konstrukcija vjerojatnosnog prostora**
>
> Definiramo
>
> $$
> \Omega:=D,\qquad \mathcal{F}:=\mathcal{P}(D).
> $$
>
> Dakle, **elementarni ishodi upravo su elementi skupa $D$**, a događaji su svi njegovi podskupovi.
>
> Vjerojatnost definiramo tako da svakom elementarnom ishodu $a_i$ pridružimo zadanu vjerojatnost $p_i$:
>
> $$
> \mathbb{P}(\{a_i\}):=p_i,\quad \forall i\in I.
> $$
>
> Preciznije, za svaki $A\subseteq D$ definiramo
>
> $$
> \mathbb{P}(A):=\sum_{i:a_i\in A}p_i.
> $$
>
> Budući da je $(p_i:i\in I)$ distribucija, vrijedi
>
> $$
> p_i\ge 0,\qquad \sum_{i\in I}p_i=1.
> $$
>
> Iz tih svojstava slijedi da je $\mathbb{P}$ nenegativna, normirana i $\sigma$-aditivna, pa je $(\Omega,\mathcal{F},\mathbb{P})$ vjerojatnosni prostor.
>
> **Konstrukcija slučajne varijable**
>
> Definiramo $X:\Omega\to D$ kao identitetu:
>
> $$
> \boxed{X(\omega):=\omega,\quad \forall\omega\in\Omega.}
> $$
>
> Drugim riječima, slučajna varijabla svakom ishodu pridružuje njegovu vlastitu vrijednost.
> Sjetimo se, $D$ je zadan kao $\subseteq \mathbb{R}$.
>
> Budući da je $\mathcal{F}=\mathcal{P}(D)$, funkcija $X$ je izmjeriva, a kako je $D$ konačan ili prebrojiv, ona je diskretna slučajna varijabla.
>
> **Provjera tražene distribucije**
>
> Preostaje dokazati da konstruirana slučajna varijabla ima upravo zadanu distribuciju.
>
> Kako je $X$ identiteta, događaj $\{X=a_i\}$ sastoji se od jedinog ishoda $a_i$, odnosno
>
> $$
> \{X=a_i\}=\{a_i\}.
> $$
>
> Stoga za svaki $i\in I$ vrijedi
>
> $$
> \begin{aligned}
> \mathbb{P}(X=a_i)
> &=\mathbb{P}(\{\omega\in\Omega:X(\omega)=a_i\})\\
> &=\mathbb{P}(\{a_i\})\\
> &=p_i.
> \end{aligned}
> $$
>
> Time smo konstruirali vjerojatnosni prostor i diskretnu slučajnu varijablu sa zadanom distribucijom, čime je tvrdnja dokazana. 

Neka je $X$ diskretna slučajna varijabla s distribucijom $(p_i:i\in I)$ na skupu $D=\{a_i:i\in I\}$, odnosno

$$
\mathbb{P}(X=a_i)=p_i,\quad \forall i\in I.
$$

Tada za svaki skup $B\subseteq\mathbb{R}$ vrijedi

$$
\boxed{
\mathbb{P}(X\in B)=\sum_{i\in I:a_i\in B}p_i.
}
$$

Dakle, **vjerojatnost da $X$ poprimi vrijednost iz skupa $B$ jednaka je zbroju vjerojatnosti svih mogućih vrijednosti slučajne varijable $X$ koje pripadaju skupu $B$.**

> [!dokaz]- Dokaz.
> Događaji $\{X=a_i\}$ su međusobno disjunktni, pa vrijedi
> 
> $$
> \begin{aligned}
> \mathbb{P}(X\in B)
> &=\mathbb{P}\left(\bigcup_{i\in I:a_i\in B}\{X=a_i\}\right)\\
> &=\sum_{i\in I:a_i\in B}\mathbb{P}(X=a_i)\\
> &=\sum_{i\in I:a_i\in B}p_i.
> \end{aligned}
> $$

## Neke poznate distribucije
### Diskretna uniformna razdioba na $\left\{ 1, \dots, n \right\}$

$$
\boxed{\mathbb{P}(X=k)=\frac{1}{n},\quad k\in\{1,\ldots,n\}}
$$

### Bernoullijeva razdioba
**Parametar:** $p\in[0,1]$, uz $q=1-p$.

**Oznaka:**

$$
X\sim B(p).
$$

Slučajna varijabla $X$ označava **broj uspjeha u jednom Bernoullijevom pokusu**, pa je

$$
D_X=\{0,1\}.
$$

Vrijedi

$$
\mathbb P(X=1)=p,
\qquad
\mathbb P(X=0)=q=1-p.
$$

Odnosno, distribucija je

$$
\boxed{
X\sim
\begin{pmatrix}
0 & 1\\
q & p
\end{pmatrix}
}
$$

Vjerojatnosna funkcija mase može se zapisati kao

$$
f_X(k)=\mathbb P(X=k)=p^kq^{1-k},
\qquad k\in\{0,1\}.
$$

**Primjer:** jedno bacanje nesimetričnog novčića, gdje „pismo” smatramo uspjehom s vjerojatnošću $p$.

> [!definicija] Indikator događaja
> Za događaj $A\in\mathcal F$ definiramo funkciju
>
> $$
> \mathbf 1_A:\Omega\to\{0,1\}
> $$
>
> sa
>
> $$
> \mathbf 1_A(\omega):=
> \begin{cases}
> 1, & \omega\in A,\\
> 0, & \omega\notin A.
> \end{cases}
> $$
>
> Ovu funkciju (slučajnu varijablu) nazivamo **indikator događaja $A$**.

### Binomnma razdioba
**Parametri:** $n\in\mathbb N$ i $p\in[0,1]$, uz $q=1-p$.

**Oznaka:**

$$
X\sim B(n,p).
$$

Slučajna varijabla $X$ označava **broj uspjeha u $n$ nezavisnih Bernoullijevih pokusa**, pri čemu je vjerojatnost uspjeha u svakom pokusu jednaka $p$.

Možemo je zapisati kao

$$
X=\sum_{i=1}^{n}\mathbf 1_{A_i},
$$

gdje je

$$
A_i=\{\text{uspjeh u }i\text{-tom pokusu}\},
\qquad
\mathbb P(A_i)=p.
$$

Skup mogućih vrijednosti je

$$
D_X=\{0,1,\ldots,n\}.
$$

Distribucija je zadana s

$$
\boxed{
\mathbb P(X=k)
=
\binom nk p^kq^{\,n-k}
},
\qquad k=0,1,\ldots,n.
$$

Pri tome:
- $\binom nk$ — odabire kojih se $k$ uspjeha dogodilo,
- $p^k$ — vjerojatnost tih $k$ uspjeha,
- $q^{n-k}$ — vjerojatnost preostalih $n-k$ neuspjeha.

### Geometrijska razdioba
**Parametar:** $p\in(0,1]$, uz $q=1-p$.

**Oznaka:**

$$
T\sim G(p).
$$

Slučajna varijabla $T$ označava **broj pokusa do prvog uspjeha** u nizu nezavisnih Bernoullijevih pokusa s vjerojatnošću uspjeha $p$.

Skup mogućih vrijednosti je

$$
D_T=\mathbb N=\{1,2,\ldots\}.
$$

Distribucija je zadana s

$$
\boxed{
\mathbb P(T=k)=q^{k-1}p
},
\qquad k\in\mathbb N.
$$

Pri tome:
- $q^{k-1}$ — prvih $k-1$ pokusa su neuspjesi,
- $p$ — $k$-ti pokus je prvi uspjeh.

Ako umjesto toga definiramo

$$
\widetilde T=\text{ukupan broj neuspjeha do prvog uspjeha},
$$

tada je $\widetilde T=T-1$, $\widetilde T\in\mathbb N_0$ i

$$
\mathbb P(\widetilde T=k)=q^kp,
\qquad k\in\mathbb N_0.
$$

### Negativna binomna razdioba

**Parametri:** $r\in\mathbb N$ i $p\in(0,1]$, uz $q=1-p$.

**Oznaka:**

$$
Z\sim NB(r,p).
$$

Slučajna varijabla $Z$ označava **broj neuspjeha do ukupno $r$ uspjeha** u nizu nezavisnih Bernoullijevih pokusa s vjerojatnošću uspjeha $p$.

Skup mogućih vrijednosti je

$$
D_Z=\mathbb N_0=\{0,1,2,\ldots\}.
$$

Distribucija je zadana s

$$
\boxed{
\mathbb P(Z=m)
=
\binom{m+r-1}{r-1}q^m p^r
},
\qquad m\in\mathbb N_0.
$$

Pri tome:
- $\binom{m+r-1}{r-1}$ — raspoređujemo prvih $r-1$ uspjeha među prvih $m+r-1$ pokusa,
- $q^m$ — dogodilo se $m$ neuspjeha,
- $p^r$ — dogodilo se ukupno $r$ uspjeha, pri čemu je zadnji pokus $r$-ti uspjeh.

Za $r=1$ dobivamo geometrijsku razdiobu na $\mathbb N_0$.

## Funkcija slučajne varijable

> [!definicija] Funkcija slučajne varijable
> Ako je $X$ diskretna slučajna varijabla i
> 
> $$
> g:D_X\to\mathbb R
> $$
> 
> proizvoljna funkcija, tada je funkcija
> 
> $$
> g(X):\Omega\to\mathbb R
> $$
> 
> definirana sa
> 
> $$
> g(X)(\omega):=g(X(\omega)),
> \qquad \omega\in\Omega,
> $$
> 
> ponovno diskretna slučajna varijabla jer je
> 
> $$
> D_{g(X)}=g(D_X)
> $$
> 
> ponovno najviše prebrojiv skup.

> [!istaknuto] distribucija $g(X)$ preko $X$
> Ako je poznato
>
> $$
> X\sim
> \begin{pmatrix}
> a_1 & a_2 & \cdots \\
> p_1 & p_2 & \cdots
> \end{pmatrix}
> $$
>
> i definira se
>
> $$
> Y=g(X),
> $$
>
> onda za odrediti distribuciju od $Y$:
>
> 1. Izračunamo $g(a_i)$ za svaku moguću vrijednost $a_i$.
> 2. Ako više različitih $a_i$ daje istu vrijednost $b$, njihove vjerojatnosti zbrojimo.
>
> Formalno, ako je
>
> $$
> D_X=\{a_i:i\in I\}
> $$
>
> te
>
> $$
> D_{g(X)}=\{g(a_i):i\in I\}=:\{b_j:j\in J\},
> $$
>
> distribucija od $g(X)$ dana je s
>
> $$
> \mathbb P(g(X)=b_j)
> =
> \sum_{i\in I:\,g(a_i)=b_j}
> \mathbb P(X=a_i),
> \qquad \forall j\in J.
> $$

> [!dokaz]- Dokaz.
> Uočimo da vrijedi
>
> $$
> \{\omega:g(X(\omega))=b_j\}
> =
> \{\omega:X(\omega)\in g^{-1}(\{b_j\})\}.
> $$
>
> Po tome imamo
>
> $$
> \begin{aligned}
> \mathbb{P}(g(X)=b_j)
> &=\mathbb{P}\left(X\in g^{-1}(\{b_j\})\right)\\[6pt]
> &=\sum_{a_i\in g^{-1}(\{b_j\})}\mathbb{P}(X=a_i)\\[6pt]
> &=\sum_{a_i:\,g(a_i)=b_j}\mathbb{P}(X=a_i).
> \end{aligned}
> $$