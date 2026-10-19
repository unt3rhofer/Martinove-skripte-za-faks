---
title: 2 Uvod, jezik i motivacija
---
## Klase
> [!definicija] Klasa
> Kolekcija skupova s nekim zajedničkim preciziranim svojstvom.

> [!istaknuto] Elementi skupova
> Elementi skupova su skupovi.

**Prva posljedica**
U teoriji skupova ne proučavamo skupove svakodnevnih predmeta ili pojava, već nas isključivo zanimaju skupovi matematičkih objekata. Pri tome je ključno da se ti matematički objekti na prirodan način mogu i sami reprezentirati kao skupovi.

**Druga posljedica**
Općenite klase ne mogu biti elementi skupova, iz čega proizlazi da ne postoji skup svih klasa, kao niti klasa svih klasa. Klase jednostavno ne pripadaju onim matematičkim objektima koji se mogu prirodno reprezentirati kao skupovi.

**Treća posljedica**
Iako klase i skupovi nisu isti pojmovi, neke dovoljno male klase zapravo jesu skupovi, odnosno predstavljaju kolekciju istih elemenata. Velik dio početnog razvoja teorije skupova bavi se upravo utvrđivanjem koje su klase zapravo skupovi, pri čemu se vodimo intuicijom da jedini način na koji klasa može ne biti skup jest taj da je ona prevelika.
## Russelov Paradoks
> [!bitnatvrdnja] Russellov paradoks
> Postoji klasa koja nije skup (tzv. prava klasa).

> [!dokaz]- Dokaz
> Promotrimo klasu $R$ svih skupova koji nisu elementi samih sebe. Dakle, svojstvo skupa $x$ koje karakterizira elemente klase $R$ je $x \notin x$. To znači da za svaki skup $x$ vrijedi: $x \in R$ ako i samo ako $x \notin x$.
> 
> Kad bi $R$ bio skup, tad bismo mogli tu ekvivalenciju primijeniti na $x := R$ i dobiti da je $R \in R$ ako i samo ako $R \notin R$, što je očito nemoguće.
> 
> Jedini izlaz je da prihvatimo da je pretpostavka da je $R$ skup pogrešna. (Tada paradoks nestaje, jer doista ne vrijedi $x \in x$ za $x = R$, ali iz toga ne možemo zaključiti $R \in R$ jer $R$ nije skup. $R$ sadrži skupove koji nisu elementi samih sebe.)
## Izgradnja kumulativne hijerarhije
> [!definicija] Kumulativna hijerarhija
> Pojam hijerarhija ima mnogo definicija, ali sve u sebi sadrže neku ideju stupnja, ranga odnosno razine (nivoa). Tako i kumulativna hijerarhija ima razine, što smo već nagovijestili kada smo kazali da su elementi skupova ponovo skupovi.
> 
> Kako smo u Russellovu paradoksu vidjeli da je problematična relacija „$x \in x$”, jedan prirodni način da je izbjegnemo je da skupove gradimo po razinama: elementi skupa $A$ jesu također skupovi, ali „niže razine” nego $A$.
> 
> Kumulativna hijerarhija počinje praznim skupom, koji se (jedini) nalazi na prvoj razini $V_{1}$. Obično smatramo da ispod nje postoji još jedna razina $V_{0}$, koja je prazna (nema elemenata).

Pojam „kumulativna” znači da hijerarhija raste, odnosno akumulira sve dosad izgrađene skupove: $V_{n} \subseteq V_{n+1}$ za $n \in \mathbb{N}$, ili općenito $V_{\alpha} \subseteq V_{\beta}$ za $\alpha < \beta$. Zato, kad kažemo da pri izgradnji skupova na razini $n > 0$ možemo koristiti samo elemente na razinama manjima od $n$, zapravo je dovoljno tražiti da koristimo elemente razine $V_{n-1}$ — svi ispod, recimo oni s razine $V_{n-3}$ ako takva postoji, bit će također u $V_{n-1}$.

Na taj način, svaki element razine $V_{n+1}$ zapravo ima sve svoje elemente na razini $V_{n}$, odnosno podskup je od $V_{n}$. Štoviše, svaki podskup od $V_{n}$ je na razini $V_{n+1}$, odnosno $V_{n+1}$ je upravo klasa svih podskupova klase $V_{n}$.

> [!istaknuto] Razine kao partitivni skupovi
> Pokazat će se da su sve razine kumulativne hijerarhije skupovi, pa vrijedi:
> $$V_{\alpha+1} = \mathscr{P}(V_{\alpha})$$
> Iz toga već znamo izračunati $V_{n}$ za sve $n \in \mathbb{N}$: recimo, $V_{3} = \mathscr{P}(\mathscr{P}(\mathscr{P}(\varnothing)))$ (ima $2^{2^{2^{0}}} = 4$ elementa).
> 
> Lako je vidjeti indukcijom po $n$ da su svi $V_{n}$ konačni, a tada su i svi njihovi podskupovi konačni, dakle taj dio kumulativne hijerarhije ($V_{n}, n \in \mathbb{N}$) pokriva samo konačne skupove.

> [!detaljnije]- Objašnjenje partitivnih skupova praznog skupa
> Razlika je u razlikovanju **praznog skupa** $\varnothing$ (skup bez ijednog elementa) i **skupa čiji je element prazan skup** $\{\varnothing\}$ (skup s jednim elementom).
> 
> Partitivni skup skupa $A$, u oznaci $\mathscr{P}(A)$, jest skup svih podskupova skupa $A$:
> $$\mathscr{P}(A) = \{X : X \subseteq A\}$$
> Ako skup $A$ ima $n$ elemenata, njegov partitivni skup $\mathscr{P}(A)$ ima $2^n$ elemenata.
> 
> **Izgradnja prvih razina:**
> - **Razina $V_0$:**
>   $$V_0 = \varnothing$$
>   Prazan skup ima $0$ elemenata ($|V_0| = 0$).
> - **Razina $V_1 = \mathscr{P}(V_0) = \mathscr{P}(\varnothing)$:**
>   Jedini podskup praznog skupa je on sam ($\varnothing \subseteq \varnothing$).
>   Zato je:
>   $$V_1 = \{\varnothing\}$$
>   Ovaj skup ima $2^0 = 1$ element (prazan skup $\varnothing$ mu je element), stoga $V_1$ **nije** prazan skup.
> - **Razina $V_2 = \mathscr{P}(V_1) = \mathscr{P}(\{\varnothing\})$:**
>   Podskupovi skupa $\{\varnothing\}$ su trivijalni podskup $\varnothing$ i cijeli skup $\{\varnothing\}$:
>   $$V_2 = \{\varnothing, \{\varnothing\}\}$$
>   Ovdje imamo $2^1 = 2$ elementa.
> - **Razina $V_3 = \mathscr{P}(V_2)$:**
>   Budući da $V_2$ ima $2$ elementa, njegov partitivni skup ima $2^2 = 4$ elementa:
>   $$V_3 = \{\varnothing, \{\varnothing\}, \{\{\varnothing\}\}, \{\varnothing, \{\varnothing\}\}\}$$
> 
> Partitivni skup bilo kojeg skupa $X$ **nikada ne može biti prazan** jer uvijek vrijedi $\varnothing \subseteq X$, pa je barem $\varnothing \in \mathscr{P}(X)$. Čak i za sam prazan skup vrijedi $\mathscr{P}(\varnothing) = \{\varnothing\} \neq \varnothing$.

Da bismo dobili beskonačne skupove, morat ćemo napraviti novu razinu, koja sadrži sve dosad izgrađene skupove:
$$V_{\omega} := \bigcup_{n \in \mathbb{N}} V_{n}$$
i onda skupiti sve podskupove toga: $V_{\omega+1} := \mathscr{P}(V_{\omega})$.

> [!bitnatvrdnja] Pravila za izgradnju kumulativne hijerarhije
> Sva pravila za izgradnju kumulativne hijerarhije su:
> $$V_{0} := \varnothing, \quad V_{\alpha+1} := \mathscr{P}(V_{\alpha}), \quad V_{\lambda} := \bigcup_{\gamma < \lambda} V_{\gamma} \text{ za granični } \lambda.$$

> [!objasnjenje]- Granični ordinal $\lambda$
> U kontekstu kumulativne hijerarhije i teorije skupova, oznaka **granični $\lambda$** odnosi se na **granični ordinal** (ordinalni broj).
> 
> **Pojam i podjela ordinala**
> Ordinali su „generalizirani redni brojevi” koji formaliziraju poredak i služe kao indeksi razina kumulativne hijerarhije ($V_{0}, V_{1}, V_{2}, \dots$). Dok je svaki prirodni broj ili $0$ ili neposredni sljedbenik svog prethodnika ($n = m + 1$), ordinali se dijele u tri tipa:
> 1. **Nula ($0$):** početni ordinal.
> 2. **Sljedbenik ($\alpha + 1$ odnosno $\alpha^{+}$):** ordinal koji ima svog neposrednog prethodnika $\alpha$.
> 3. **Granični ordinal ($\lambda$):** ordinal različit od nule koji **nema neposrednog prethodnika** (odnosno nije sljedbenik nijednog ordinala).
> 
> **Primjer graničnog ordinala**
> Prvi i osnovni primjer graničnog ordinala je $\omega$ (skup svih prirodnih brojeva). On dolazi neposredno nakon svih konačnih ordinala $0, 1, 2, 3, \dots$, a nema svog neposrednog prethodnika jer bi to morao biti „najveći prirodni broj”, koji ne postoji.
> 
> **Značenje za pravilo $V_{\lambda} := \bigcup_{\gamma < \lambda} V_{\gamma}$**
> - Kada se gradi razina koja je **sljedbenik** ($\alpha + 1$), točno se zna koja je razina bila neposredno prije nje ($V_{\alpha}$), pa se primjenjuje partitivni skup:
>   $$V_{\alpha+1} := \mathscr{P}(V_{\alpha})$$
> - Kada se dođe do **graničnog ordinala** $\lambda$ (poput $\omega$), ne postoji „zadnja razina” prije $\lambda$ na koju bi se mogao primijeniti partitivni skup. Zato se provodi prijelaz preko unije, odnosno skupljaju se sve dotad izgrađene niže razine:
>   $$V_{\lambda} := \bigcup_{\gamma < \lambda} V_{\gamma}$$
## Jezik teorije skupova
> [!istaknuto] Pravila za formule
> Formule su dobivene isključivo sljedećim pravilima:
> * Ako su $x$ i $y$ varijable, tada su $x \in y$ i $x = y$ formule (tzv. atomarne formule).
> * Ako su $\varphi$ i $\psi$ formule, tada su $\neg \varphi$, $(\varphi \wedge \psi)$, $(\varphi \vee \psi)$, $(\varphi \rightarrow \psi)$ i $(\varphi \leftrightarrow \psi)$ formule.
> * Ako je $\varphi$ formula i $x$ varijabla, tada su $\forall x \varphi$ i $\exists x \varphi$ formule.

> [!definicija] Vezane i slobodne definicije
> **Vezane varijable** su one koje se unutar formule nalaze pod djelovanjem kvantifikatora (poput $\forall x \varphi$ ili $\exists x \varphi$). U kontekstu teorije skupova, ključno je znati da takve varijable uvijek predstavljaju isključivo skupove, a nikada klase.
> 
> **Slobodne varijable** su one koje se u formuli pojavljuju izvan dosega kvantifikatora (dakle, nisu vezane). O njima izravno ovisi smisao i značenje same formule. Ako proglasimo neku formulu sa slobodnim varijablama istinitom, bez da smo im zadali konkretne vrijednosti, prešutno podrazumijevamo da ta formula vrijedi univerzalno za sve moguće izbore tih varijabli.