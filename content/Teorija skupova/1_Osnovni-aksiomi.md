---
title: 1 Osnovni aksiomi
---
## Aksiom ekstenzionalnosti
**Motivacija**
Ideja je da je skup u potpunosti određen svojim elementima: **redoslijed elemenata nije bitan, niti ima smisla koliko se puta neki element pojavljuje**. Zato dva skupa koji imaju potpuno iste elemente trebamo smatrati jednakima. Upravo to formalizira aksiom ekstenzionalnosti.

> [!bitnatvrdnja] Aksiom ekstenzionalnosti
> $$\forall z (z \in x \iff z \in y) \implies x = y$$

Intuitivno, aksiom ekstenzionalnosti znači da su dva skupa jednaka ako i samo ako imaju potpuno iste elemente. Skup je time u cjelini određen isključivo svojim elementima, bez obzira na njihov redoslijed ili ponavljanje.

Obrat aksioma ekstenzionalnosti glasi:
$$x = y \implies \forall z (z \in x \iff z \in y)$$

Logički obrat aksioma ekstenzionalnosti kaže da **jednaki skupovi imaju iste elemente**.

Ako je $x=y$, tada se $x$ i $y$ mogu međusobno zamijeniti u svakoj formuli bez promjene istinitosti. Posebno, za proizvoljan skup $z$ vrijedi

$$
x=y \implies (z\in x \iff z\in y).
$$

Dakle, iz jednakosti skupova slijedi da svaki element jednog skupa pripada i drugome, i obratno. Za razliku od aksioma ekstenzionalnosti, ovaj smjer ne zahtijeva poseban aksiom, nego slijedi iz **logičkog značenja jednakosti**.

## Aksiom praznog skupa
**Motivacija**
Kako bismo uopće mogli započeti izgradnju kumulativne hijerarhije, nužno je postulirati da je početna, prazna razina $V_0$ doista skup.

Čim smo dokazali (ili propisali kao aksiom) formulu $\exists y \forall z(z \in y \iff \varphi)$, možemo uvesti funkcijsku oznaku za $y$, jer takav $y$ uvijek mora biti jedinstven.
> [!dokaz]- Dokaz.
> Pretpostavimo da su $y_1$ i $y_2$ takvi da vrijedi:
> $$\forall z(z \in y_1 \iff \varphi) \quad \text{i} \quad \forall z(z \in y_2 \iff \varphi)$$
> 
> Tada za svaki $z$ imamo da su sve tri formule ($z \in y_1$, $\varphi$ i $z \in y_2$) ekvivalentne, pa specijalno vrijedi:
> $$z \in y_1 \iff z \in y_2$$
> 
> Po aksiomu ekstenzionalnosti, iz toga slijedi $y_1 = y_2$.

> [!bitnatvrdnja] Aksiom praznog skupa
> $$\exists y \forall z (z \notin y)$$

Antitautologija (formula koja je uvijek lažna za svaki objekt, npr. $z \neq z$) u općem obliku $\exists y \forall z (z \in y \iff \varphi)$ osigurava postojanje skupa koji ne sadrži niti jedan element.

Po Napomeni 1.1. takav je skup jedinstven jer iz postojanja formule oblika $\exists y \forall z (z \in y \iff \varphi)$ izravno slijedi jedinstvenost skupa $y$.

Zato je opravdano uvesti oznaku za prazan skup, $\emptyset$
##  Aksiom partitivnog skupa

**Motivacija**
Aksiom partitivnog skupa potreban nam je kako bismo nastavili izgrađivati kumulativnu hijerarhiju (definiranjem $V_{\alpha+1} := \mathcal{P}(V_\alpha)$) uz garanciju da svaka nova razina svih podskupova doista ostaje skup.

> [!bitnatvrdnja] Aksiom partitivnog skupa
> $$\forall x \exists y \forall z (z \in y \iff z \subseteq x)$$

Striktno govoreći, kvantifikator $\forall x$ nije nužan.
Intuitivno, aksiom kaže da postoji neki skup $y$ čiji su elementi podskupovi nekog skupa $x$.

## Aksiom unije
**Motivacija**
Aksiom unije uvodimo zato što pri izgradnji kumulativne hijerarhije trebamo osigurati da je **unija već formirane familije skupova ponovno skup**.

To je posebno važno za granične razine poput $V_\omega$, koje nastaju kao unija svih prethodnih razina.

> [!bitnatvrdnja] Aksiom unije
> $$\forall x \exists y \forall z (z \in y \iff (\exists t \in x)(z \in t))$$

- $x$ je neki proizvoljan skup shvaćen kao familija $\{t : t \in x\}$.
- $\bigcup_{t \in x} t$ tada sadrži *sve one $z$ koji se nalaze barem u jednom $t \in x$*.
- Službena oznaka je $\bigcup x$ iako se $\bigcup_{t \in x} t$  koristi zbog jasnoće.

Za svaki skup $x$ vrijedi:
$$\bigcup \mathscr{P}(x) = x$$

> [!dokaz]- Dokaz.
> Po aksiomu ekstenzionalnosti dovoljno je dokazati dvije inkluzije:
> $$\bigcup \mathscr{P}(x) \subseteq x \quad \text{i} \quad x \subseteq \bigcup \mathscr{P}(x)$$
> 
> - **Inkluzija $\bigcup \mathscr{P}(x) \subseteq x$:**
>   Neka je $z \in \bigcup \mathscr{P}(x)$ proizvoljan.
>   Po definiciji unije postoji $t \in \mathscr{P}(x)$ takav da je $z \in t$.
>   Iz $t \in \mathscr{P}(x)$ slijedi $t \subseteq x$, pa po definiciji podskupa iz $z \in t$ slijedi $z \in x$.
> 
> - **Inkluzija $x \subseteq \bigcup \mathscr{P}(x)$:**
>   Neka je $z \in x$ proizvoljan.
>   Odabirom $t := x$ imamo $x \subseteq x$, odnosno $x \in \mathscr{P}(x)$.
>   Budući da vrijedi $z \in x \land x \in \mathscr{P}(x)$, po definiciji unije slijedi $z \in \bigcup \mathscr{P}(x)$.

Za razliku od jednakosti $x = \bigcup \mathscr{P}(x)$ koja uvijek vrijedi, izraz $x = \mathscr{P}(\bigcup x)$ općenito ne vrijedi.

Uvijek vrijedi inkluzija:
$$x \subseteq \mathscr{P}(\bigcup x)$$

Dok obratna inkluzija $\mathscr{P}(\bigcup x) \subseteq x$ općenito ne vrijedi.

> [!detaljnije]- Obrazloženje
> Za skup $x = \{\{1\}, \{2\}\}$ imamo:
> $$\bigcup x = \{1, 2\}$$
> $$\mathscr{P}(\bigcup x) = \{\varnothing, \{1\}, \{2\}, \{1, 2\}\}$$
> 
> Vrijedi $x \subseteq \mathscr{P}(\bigcup x)$, ali $\mathscr{P}(\bigcup x) \nsubseteq x$ jer $\varnothing, \{1, 2\} \notin x$.
> 
> > **Razlog:** Za konačne skupove $\mathscr{P}(\bigcup x)$ uvijek ima $2^k$ elemenata, pa jednakost propada čim broj elemenata od $x$ nije potencija broja 2 ili $x$ ne sadrži sve podskupove svoje unije.
> 
> > [!dokaz]- Dokaz.
> > Neka je $u \in x$ proizvoljan.
> > Želimo pokazati $u \in \mathscr{P}(\bigcup x)$, odnosno $u \subseteq \bigcup x$.
> > 
> > Neka je $z \in u$ proizvoljan.
> > Kako je $z \in u \land u \in x$, po definiciji unije vrijedi:
> > $$z \in \bigcup x$$
> > 
> > Budući da to vrijedi za svaki $z \in u$, slijedi:
> > $$u \subseteq \bigcup x \implies u \in \mathscr{P}(\bigcup x)$$
> > 
> > Time je dokazano $x \subseteq \mathscr{P}(\bigcup x)$.

| Objekt | Kako razmišljati o njemu |
|---|---|
| $R$ | Sam skup i njegovi elementi |
| $\bigcup R$ | Svi elementi elemenata od $R$ |
| $\mathscr{P}(R)$ | Svi podskupovi od $R$ |
## Aksiom para
**Motivacija**
Aksiom para uvodi se kako bismo osigurali postojanje skupova koji nemaju potenciju broja dva elemenata (poput tročlanih skupova) te omogućili definiciju binarne unije $a \cup b$ kao unije dvočlane familije $\{a, b\}$.

> [!bitnatvrdnja] Aksiom para
> $$\forall a \forall b \exists y \forall z (z \in y \iff z = a \lor z = b)$$
Neka je $k \in \mathbb{N}$ prirodan broj, te $x_1, x_2, \ldots, x_k$ skupovi. Tada je i klasa
$$\{x_1, \ldots, x_k\} := \{x : x = x_1 \lor x = x_2 \lor \cdots \lor x = x_k\}$$
skup.

> [!dokaz]- Dokaz.
> **BAZA**
> Za $k = 0$ je klasa prazna pa je po aksiomu praznog skupa ona skup.
> 
> **PRETPOSTAVKA**
> Neka su $x_1, \ldots, x_k$ skupovi.
> Pretpostavimo da postoji $k \in \mathbb{N}$ t.d. je $\{x_1, \ldots, x_k\}$ skup.
> 
> **KORAK**
> Neka su $x_1, \ldots, x_k, x_{k+1}$ skupovi.
> Prema aksiomu para je singleton $\{x_{k+1}\}$ skup, a prema pretpostavci indukcije je i $\{x_1, \ldots, x_k\}$ skup.
> Sada prema aksiomima para i unije slijedi da je $\{x_1, \ldots, x_k\} \cup \{x_{k+1}\} = \{x_1, \ldots, x_{k+1}\}$ ponovno skup.

## Uređeni par
>[!definicija] Uređeni par
> Neka su $x$ i $y$ skupovi. Oznakom $(x, y)$ označavamo skup $\{\{x\}, \{x, y\}\}$.

Primijetimo da je $(x, y)$ doista skup, trostrukom primjenom aksioma para: jednom na $x$ i $x$, drugi put na $x$ i $y$, te treći put na tako dobivene skupove $\{x\}$ i $\{x, y\}$.
Za bilo koje skupove $x$, $y$ i $z$, jednakost $\{x,y\}=\{x,z\}$ povlači $y=z$.

> [!dokaz]- Dokaz
> Po aksiomu para je $y=x \lor y=z$, i također $z=x \lor z=y$. U tri od četiri tako dobivena slučaja je odmah $y=z$, a u četvrtom je $y=x$ i $z=x$, pa je opet $y=z$.
Neka su $a$, $b$, $c$ i $d$ skupovi. Ako je $(a,b)=(c,d)$, tada je $a=c$ i $b=d$.

> [!dokaz]- Dokaz.
> Po definiciji uređenog para imamo
>
> $$
> (a,b)=\{\{a\},\{a,b\}\},
> \qquad
> (c,d)=\{\{c\},\{c,d\}\}.
> $$
>
> Zato pretpostavka $(a,b)=(c,d)$ zapravo znači
>
> $$
> \{\{a\},\{a,b\}\}
> =
> \{\{c\},\{c,d\}\}.
> $$
>
> Prvo želimo dokazati da je $a=c$.
>
> Znamo da je
>
> $$
> \{a\}\in\{\{a\},\{a,b\}\},
> $$
>
> jer je $\{a\}$ jedan od elemenata tog para. Budući da su vanjski skupovi jednaki, isti objekt mora pripadati i desnom skupu:
>
> $$
> \{a\}\in\{\{c\},\{c,d\}\}.
> $$
>
> Sada primjenjujemo aksiom para. Za skup $\{X,Y\}$ vrijedi
>
> $$
> Z\in\{X,Y\}\iff Z=X\lor Z=Y.
> $$
>
> U ovom slučaju uzimamo
>
> $$
> Z=\{a\},\qquad X=\{c\},\qquad Y=\{c,d\}.
> $$
>
> Zato iz
>
> $$
> \{a\}\in\{\{c\},\{c,d\}\}
> $$
>
> slijedi
>
> $$
> \{a\}=\{c\}\lor\{a\}=\{c,d\}.
> $$
>
> Dakle, imamo dva slučaja.
>
> **Prvi slučaj:**
>
> $$
> \{a\}=\{c\}.
> $$
>
> Budući da je
>
> $$
> c\in\{c\},
> $$
>
> iz jednakosti $\{a\}=\{c\}$ slijedi
>
> $$
> c\in\{a\}.
> $$
>
> **Drugi slučaj:**
>
> $$
> \{a\}=\{c,d\}.
> $$
>
> Budući da je
>
> $$
> c\in\{c,d\},
> $$
>
> iz jednakosti $\{a\}=\{c,d\}$ ponovno slijedi
>
> $$
> c\in\{a\}.
> $$
>
> Dakle, bez obzira na to koji slučaj vrijedi, dobivamo
>
> $$
> c\in\{a\}.
> $$
>
> Skup $\{a\}$ možemo promatrati kao par $\{a,a\}$. Po aksiomu para vrijedi
>
> $$
> c\in\{a\}
> \iff
> c=a\lor c=a.
> $$
>
> Prema tome,
>
> $$
> c=a.
> $$
>
> Time smo dokazali prvi dio:
>
> $$
> a=c.
> $$
>
> Sada se vraćamo na početnu jednakost
>
> $$
> \{\{a\},\{a,b\}\}
> =
> \{\{c\},\{c,d\}\}.
> $$
>
> Budući da smo dokazali $c=a$, možemo $c$ zamijeniti s $a$, pa dobivamo
>
> $$
> \{\{a\},\{a,b\}\}
> =
> \{\{a\},\{a,d\}\}.
> $$
>
> Sada je ova jednakost oblika iz Leme 1.6:
>
> $$
> \{x,y\}=\{x,z\}\implies y=z.
> $$
>
> Uzmemo
>
> $$
> x=\{a\},\qquad
> y=\{a,b\},\qquad
> z=\{a,d\}.
> $$
>
> Primjenom Leme 1.6 dobivamo
>
> $$
> \{a,b\}=\{a,d\}.
> $$
>
> Na tu jednakost ponovno primijenimo Lemu 1.6, sada uz
>
> $$
> x=a,\qquad y=b,\qquad z=d.
> $$
>
> Iz
>
> $$
> \{a,b\}=\{a,d\}
> $$
>
> slijedi
>
> $$
> b=d.
> $$
>
> Dakle, iz
>
> $$
> (a,b)=(c,d)
> $$
>
> dobili smo
>
> $$
> a=c
> \quad\text{i}\quad
> b=d.
> $$
>
> Cijeli tok dokaza može se sažeti ovako:
>
> $$
> (a,b)=(c,d)
> $$
>
> $$
> \Downarrow
> $$
>
> $$
> \{\{a\},\{a,b\}\}
> =
> \{\{c\},\{c,d\}\}
> $$
>
> $$
> \Downarrow
> $$
>
> $$
> \{a\}\in\{\{c\},\{c,d\}\}
> $$
>
> $$
> \Downarrow
> $$
>
> $$
> \{a\}=\{c\}\lor\{a\}=\{c,d\}
> $$
>
> $$
> \Downarrow
> $$
>
> $$
> c\in\{a\}
> $$
>
> $$
> \Downarrow
> $$
>
> $$
> c=a
> $$
>
> $$
> \Downarrow
> $$
>
> $$
> \{\{a\},\{a,b\}\}
> =
> \{\{a\},\{a,d\}\}
> $$
>
> $$
> \Downarrow
> $$
>
> $$
> \{a,b\}=\{a,d\}
> $$
>
> $$
> \Downarrow
> $$
>
> $$
> b=d.
> $$
>
> Ključna ideja je da najprije pomoću aksioma para dokažemo jednakost prvih komponenti $a=c$, a zatim dvaput primijenimo Lemu 1.6. Prva primjena daje $\{a,b\}=\{a,d\}$, a druga iz toga daje $b=d$.
Ako je $x \in a$ i $y \in b$, tada je

$$
(x,y) \in \mathscr{P}(\mathscr{P}(a \cup b)).
$$

> [!dokaz]- Dokaz.
> Iz $x \in a \in \{a,b\}$ slijedi
>
> $$
> x \in \bigcup \{a,b\}=a \cup b,
> $$
>
> iz čega je
>
> $$
> \{x\} \subseteq a \cup b,
> $$
>
> odnosno
>
> $$
> \{x\} \in \mathscr{P}(a \cup b).
> $$
>
> Analogno je $y \in a \cup b$, te je
>
> $$
> \{x,y\} \subseteq a \cup b,
> $$
>
> dakle
>
> $$
> \{x,y\} \in \mathscr{P}(a \cup b).
> $$
>
> Iz tog dvojeg slijedi
>
> $$
> (x,y)=\{\{x\},\{x,y\}\} \subseteq \mathscr{P}(a \cup b),
> $$
>
> odnosno tvrdnja leme.
Ako je $(x,y)\in R$, tada su $x,y\in\bigcup\bigcup R$.
> [!dokaz]- Dokaz.
> $$(x,y)=\{\{x\},\{x,y\}\}\in R 
> \implies \{x\},\{x,y\}\in\bigcup R
> \implies x,y\in\bigcup\bigcup R.
> $$

## Shema aksioma separacije
**Motivacija**
Klase općenito ne moraju biti skupovi jer mogu biti „prevelike”. Međutim, ako klasu ograničimo tako da uzimamo samo one objekte koji već pripadaju nekom skupu $x$, tada dobivamo skup. Upravo to formalizira shema aksioma separacije.

> [!bitnatvrdnja] Shema aksioma separacije
> $$
> \exists y\,\forall z\bigl(z\in y\iff(z\in x\land\varphi)\bigr),
> $$
>
> gdje je $\varphi$ proizvoljna formula koja ne sadrži slobodnu varijablu $y$.

Aksiom govori da iz već postojećeg skupa $x$ možemo **izdvojiti sve elemente koji zadovoljavaju neko svojstvo $\varphi$**, a rezultat tog izdvajanja ponovno je skup.

To je **shema**, a ne jedan aksiom, jer za svaku moguću formulu $\varphi$ dobivamo zaseban aksiom.

> [!zaokruzeno]
> Jednom kad imamo **shemu aksioma separacije**, neki drugi aksiomi više ne moraju odmah konstruirati točno željeni skup. Dovoljno je da garantiraju postojanje nekog većeg skupa koji sadrži sve željene elemente, jer separacijom iz njega možemo izdvojiti upravo ono što želimo.

> [!objasnjenje]- Objašnjenje
> Uzmimo prvo **aksiom partitivnog skupa**. U punom obliku želimo skup $\mathscr{P}(x)$ koji sadrži **točno sve podskupove od $x$**:
> 
> $$
> z \in \mathscr{P}(x) \iff z \subseteq x.
> $$
> 
> Bez separacije aksiom zato mora osigurati oba smjera:
> 
> $$
> z \subseteq x \implies z \in \mathscr{P}(x)
> $$
> 
> i
> 
> $$
> z \in \mathscr{P}(x) \implies z \subseteq x.
> $$
> 
> Ali nakon što imamo separaciju, možemo zahtijevati mnogo manje. Dovoljno je reći:
> 
> $$
> \forall x\,\exists y\,\forall z
> \bigl(z \subseteq x \implies z \in y\bigr).
> $$
> 
> To znači: za svaki $x$ postoji neki skup $y$ koji sadrži **sve podskupove od $x$**.
> 
> Važno je da $y$ možda sadrži i neke druge, neželjene elemente. Dakle, ne tvrdimo
> 
> $$
> y=\mathscr{P}(x).
> $$
> 
> Tvrdimo samo
> 
> $$
> \mathscr{P}(x)\subseteq y.
> $$
> 
> Sada koristimo separaciju. Iz skupa $y$ izdvojimo samo one elemente $z$ koji zadovoljavaju svojstvo
> 
> $$
> z\subseteq x.
> $$
> 
> Dobivamo skup
> 
> $$
> \{z\in y:z\subseteq x\}.
> $$
> 
> Budući da $y$ po pretpostavci već sadrži **svaki** podskup od $x$, ovaj izdvojeni skup je upravo
> 
> $$
> \mathscr{P}(x).
> $$
> 
> Dakle, shema separacije omogućuje nam prijelaz
> 
> $$
> \text{pronađi dovoljno velik skup}
> $$
> 
> $$
> \Downarrow
> $$
> 
> $$
> \text{separacijom ukloni sve što ne želiš}.
> $$
> 
> To je ono što se misli kada se kaže da ostale aksiome možemo zapisati u **slabijem obliku, navodeći samo jedan smjer**.
> 
> **Aksiom unije**
> 
> Ista ideja vrijedi za aksiom unije. Umjesto da odmah zahtijevamo postojanje točnog skupa
> 
> $$
> \bigcup x=\{z:(\exists t\in x)(z\in t)\},
> $$
> 
> dovoljno je zahtijevati
> 
> $$
> \exists y\,(\forall t\in x)(t\subseteq y).
> $$
> 
> To znači da za svaki $t\in x$ vrijedi
> 
> $$
> t\subseteq y.
> $$
> 
> Prema tome, svi elementi svih skupova iz $x$ već se nalaze u $y$. Drugim riječima,
> 
> $$
> \bigcup x\subseteq y.
> $$
> 
> Ali $y$ možda ima dodatnih elemenata. Zato separacijom iz $y$ uzmemo samo one $z$ za koje postoji $t\in x$ takav da je $z\in t$:
> 
> $$
> \{z\in y:(\exists t\in x)(z\in t)\}.
> $$
> 
> To je upravo
> 
> $$
> \bigcup x.
> $$
> 
> Dakle, ponovno prvo pronađemo **nadskup**, a zatim ga separacijom suzimo na točno željeni skup.
> 
> **Aksiom para**
> 
> Jednaka ideja vrijedi i za aksiom para. Umjesto da aksiom odmah kaže da postoji skup čiji su **točno** elementi $a$ i $b$, dovoljno je reći
> 
> $$
> \exists y\,(a\in y\ni b).
> $$
> 
> Zapis
> 
> $$
> a\in y\ni b
> $$
> 
> znači
> 
> $$
> a\in y\land b\in y.
> $$
> 
> Dakle, postoji neki skup $y$ koji sadrži $a$ i $b$. On možda sadrži i druge elemente.
> 
> Separacijom sada iz $y$ uzmemo samo one elemente koji zadovoljavaju
> 
> $$
> z=a\lor z=b.
> $$
> 
> Dobivamo
> 
> $$
> \{z\in y:z=a\lor z=b\}=\{a,b\}.
> $$
> 
> Zato ni aksiom para, kada već imamo separaciju, ne mora sam jamčiti da skup nema nikakvih drugih elemenata. Dovoljno je da nam da **neki skup u kojem se $a$ i $b$ nalaze**, a separacija zatim iz njega izdvoji upravo $\{a,b\}$.
> 
> Cijela se napomena može pamtiti kao razlika:
> 
> $$
> \text{Bez separacije: aksiom mora dati točno željeni skup.}
> $$
> 
> dok je sa separacijom dovoljno:
> 
> $$
> \text{Aksiom daje dovoljno velik skup}
> $$
> 
> $$
> \Downarrow
> $$
> 
> $$
> \text{separacija iz njega izdvaja točno željeni skup.}
> $$
> 
> Zato se novi oblici aksioma nazivaju **slabijima**. Primjerice,
> 
> $$
> z\subseteq x\implies z\in y
> $$
> 
> govori samo da su **svi potrebni elementi u $y$**, ali ne govori da **u $y$ nema ničega drugoga**.
> 
> Upravo taj nedostajući drugi smjer možemo nadoknaditi separacijom.
> 
> Iako se aksiomi na ovaj način mogu zapisati kraće, u skripti se zadržavaju njihovi raniji oblici jer su razumljiviji. Ova tehnika postaje posebno korisna kod kompliciranijih aksioma, primjerice kod zapisa aksioma beskonačnosti.

## Kartezijev produkt
**Motivacija**
Kartezijev produkt uvodimo kako bismo skup svih uređenih parova elemenata dvaju skupova mogli koristiti za modeliranje odnosa među tim skupovima.

Neka su $a$ i $b$ skupovi. Tada je klasa

$$
\{(x,y):x\in a,\ y\in b\}
$$

(što je pokrata za $\{p:(\exists x\in a)(\exists y\in b)(p=(x,y))\}$) skup.

> [!dokaz]- Dokaz.
> Taj skup možemo dobiti primjenom aksioma separacije. Formula piše u iskazu propozicije, ali iz kojeg skupa mora biti $p$?
>
> Ako je $x \in a$ i $y \in b$, tada je
>
> $$
> (x,y)\in\mathscr{P}(\mathscr{P}(a\cup b)).
> $$
>
> Prema tome, svaki uređeni par elemenata iz $a$ i iz $b$, dakle svaki $p$ koji zadovoljava tu formulu, mora biti u skupu $\mathscr{P}(\mathscr{P}(a\cup b))$. Dakle,
>
> $$
> a\times b=\{p\in\mathscr{P}(\mathscr{P}(a\cup b)):(\exists x\in a)(\exists y\in b)(p=(x,y))\}
> $$
>
> je skup po aksiomu separacije.