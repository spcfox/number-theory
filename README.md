# Коллоквиум по курсу «Алгоритмы в математике»

## 1. Основные структуры: группа, моноид, полугруппа
$M$ — множество. Группой $G$ называется алгебраическая структура, индуцированная на множестве $M$ законом композиции, имеющим следующие свойства:
- G1. ассоциативность: $\forall x,y,z \in G: (x \cdot y) \cdot z = x \cdot (y \cdot z)$;
- G2. нейтральный элемент: $\exists e \in G: \forall x \in G: x \cdot e = e \cdot x = x$;
- G3. обратный элемент: $\forall x \in G: \exists x^{-1} \in G: x \cdot x^{-1} = x^{-1} \cdot x = e$.

Если выполняется G1, то говорят, что $G$ — **полугруппа**. Если выполняется ещё G2, то говорят, что $G$ — **моноид**. Если выполняются все три свойства, то говорят, что $G$ — **группа**.

## 2. Гомоморфизм групп: определение, основные свойства
Гомоморфизмом групп $G$ и $G'$ называется биекция $\sigma: G \to G'$, обладающая следующими свойствами:
1. $\sigma(x \cdot y) = \sigma(x) \cdot \sigma(y)$;
2. $\sigma(e_G) = e_{G'}$.*

Обозначения:
- $\sigma: G \to G'$ — $\text{Hom}(G, G')$ — **гомоморфизм**;
- $\sigma: G \to G$ — $\text{End}(G)$ — **эндоморфизм**;
- $\sigma: G \to G', \exists \chi: G' \to G$ — $\text{Aut}(G), G'$ такое, что $\chi \circ \sigma = id_G$ и $\sigma \circ \chi = id_H$, тогда $\sigma \in \text{Iso}(G, G')$ — **изоморфизм**;
- $\sigma \in \text{Iso}(G, G)$ — $\text{Aut}(G)$ — **автоморфизм**. Любой автоморфизм изоморфен какой-нибудь симметрической группе — является перестановкой.

### Лемма  
$\sigma \in \text{Hom}(G, G')$, тогда $\sigma(x^{-1}) = \sigma(x)^{-1}$  
Доказательство: $e_H = \sigma(e_G) = \sigma(x \cdot x^{-1}) = \sigma(x) \cdot \sigma(x^{-1}) \rightarrow \sigma(x^{-1}) = \sigma(x)^{-1}$.

\* На лекции сказано, что оба свойства необходимы, но на самом деле достаточно первого свойства, так как второе из него следует:
- $\forall x \in G: \underline{\sigma(x) \cdot \sigma(e_G)} = \sigma(x \cdot e_G) = \underline{\sigma(x)} = \sigma(e_G \cdot x) = \underline{\sigma(e_G) \cdot \sigma(x)}$.  
Следовательно, $\sigma(e_G) = e_H$ по определению нейтрального элемента и его единственности.

## 3. Гомоморфизм групп: образ, ядро
$\sigma \in Hom(G, G')$.

  **Ядро** гомоморфизма: $\text{Ker} \ \sigma = \lbrace x \in G \ \vert \  \sigma(x) = e_{G'} \rbrace$
  
  **Образ** гомоморфизма: $\text{Im} \ \sigma  = \lbrace y \in G' \  \vert \ \exists x \in G: \sigma(x) = y \rbrace$


## 4. Подгруппа: определение, примеры
**Подгруппой** группы $G$ называется её подмножество $H$, обладающее структурой группы, индуцированной законом $G$.<br>
Обозначение: $H < G$.

$H = \lbrace e \rbrace$ — тривиальная подгруппа; $\lbrace e \rbrace < H < G$ - собственная подгруппа; $H = G$ — несобственная подгруппа.

Примеры:

$\sigma \in \text{Hom}(G, G')$, тогда $\text{Ker} \ \sigma \le G$ , $\text{Im} \ \sigma \le G'$ .


## 5. Смежные классы группы по подгруппе. Индекс подгруппы и порядок группы
### Рассмотрим отношение
$H \le G$; $x \thicksim y \Leftrightarrow x \cdot y^{-1} \in H$

Это отношение **эквивалентности**.

Проверим:
  1. $x \thicksim x$, т.к. $x x^{-1} = e \in H$ **рефлексивность**
  2. $x \thicksim y \Rightarrow x y^{-1} \in H \Rightarrow (x y^{-1})^{-1} \in H \Rightarrow y x^{-1} \in H \Rightarrow y \thicksim x$ **симметричность**
  3. $x \thicksim y, y \thicksim z \Rightarrow x y^{-1} \in H, y z^{-1} \in H \Rightarrow x y^{-1} y z^{-1} \in H \Rightarrow x z^{-1} \in H \Rightarrow x \thicksim z$ **транзитивность**
  
Определим **правый смежный класс**

$[y]_R = Hy = \lbrace h \cdot y \vert h \in H \rbrace$

Аналогично **левый смежный класс**

$[y]_L = yH = \lbrace y \cdot h \vert h \in H \rbrace$

Смежные классы содержащие один и тот же элемент совпадают, значит смежные классы являются классами эквивалентности, следовательно они либо совпадают, либо не пересекаются.

$G / H = G / \thicksim$ — фактор-множество левых (правых) смежных классов. Количество левых и правых смежных классов одинаковое.

### Теорема Лагранжа
$G$ — группа, $|G|$ — кол-во элементов, **порядок группы**.

$|G| < \infty$ (конечная группа), тогда:

$|G| = (G : H)|H|$

$(G : H)$ — кол-во смежных классов в $G$ по $H$, **индекс подгруппы $H$ в группе $G$**

\* Сам процесс подсчета кол-ва смежных классов: берем элементы из $G$ и считаем для них левый или правый смежный класс с $H$ (нам все равно левый или правый, потому что их кол-во одинаково), и считаем кол-во уникальных множеств (т.к. смежные классы являются классами эквивалентности)

## 6. Нормальные подгруппы: определение, основные свойства
Подгруппа $H$ группы $G$ называется **нормальной**, если
$$\forall x \in G\ \ xH = Hx.$$

**Nota bene** Если $H$ - нормальная подгруппа $G$, то обычно пишут $H \lhd G$.

**Nota bene** Нормальной является любая подгруппа абелевой группы.

**Nota bene** В случае нормальной подгруппы имеем
$$\forall x\in G [x]_R = [x]_L = \overline{x}.$$

## 7. Теорема о гомоморфизмах, каноническое отображение
**Теорема 2.1.** Пусть $H \lhd G$, тогда существует такой гомоморфизм $\upvarphi$ (называемый **каноническим**), что $ker \upvarphi = H$.

Рассмотрим отображение
$$\upvarphi : G \to G/H,\ \ \upvarphi(x) = xH,$$
и прямой проверкой убеждаемся, что
$$\upvarphi \in hom(G, G/H),\ \ ker \upvarphi - H.$$

## 8. Точные последовательности. Леммы о цепочках гомоморфизмов

## 9. Действие группы на множестве

Пусть $G$ — группа, $S$ — произвольное множество.

$G$ **действует на** $S$, если определено отображение $G \times S \rightarrow S$, т.е. $(x, a) \mapsto b$.<br>
Обозначается $(x, a) = xa = x(a)$.

**$G$-множество** — множество $S$, на которое действует группа $G$. Также обозначается $S_G$.

## 10. Перестановки: сопряжения, трансляции

### Сопряжения

$\sigma: G \rightarrow \text{Aut}(G)$; $x \mapsto \sigma_x$ и $\forall y: \sigma_x(y) = xyx^{-1}$.
<br>
**Свойства сопряжения:**
1. $\sigma_y \circ \sigma_x = \sigma_{yx}$.
2. $\sigma_e$ тождественно, т.е. $\sigma_e(z) = z$.
3. $(\sigma_x)^{-1} = \sigma_{x^{-1}}$.
4. $\forall x: \sigma_x$ — **изоморфизм**.
5. $\sigma_x$ — **гомоморфизм** (но не изоморфизм).

$H, H' \leq G$ — **сопряжённые**, если $\exists x: H' = xHx^{-1}$.

<hr>

### Трансляции

$t: G \rightarrow M(G); x \mapsto t_x$ и $\forall y: t_x(y) = xy$.
<br>
**Свойства трансляции:**
1. $t_y \circ t_x = t_{yx}$.
2. $t_e = e$.
3. Из п.1 и п.2: $t$ — **гомоморфизм**, а также **автоморфизм** (но не эндоморфизм).

## 11. Циклические группы: определения, основные свойства

Группа $G$ — **циклическая**, если $\exists x \in G: \forall y \in G \ \exists m \in \mathbb{Z}: y = x^m$.

То есть элемента $x$ достаточно, чтобы породить $G$.

Обозначение: $G = \langle x \rangle$, где $x$ — единственная образующая $G$.

<hr>

**Лемма:** Пусть $G$ — произвольная группа, $x \in G$.<br>
Тогда $H := \{x^m\}_{m \ \in \ \mathbb{Z}}$ — циклическая подгруппа $G$.

<hr>

**Показатель элемента $x \in G$** — любое число $0 < m \in \mathbb{Z}$, такое что $x^m = e$.<br>
**Показатель группы $G$** — любое число $0 < n \in \mathbb{Z}$, такое что $\forall x \in G:  x^n = e$.<br>
**Период элемента $x \in G$** — наименьший его показатель.

<hr>

Любая группа $H < \mathbb{Z}$ является **циклической** и **бесконечной**.<br>
Кроме того, сама $(\mathbb{Z}, +)$ является циклической группой: $\mathbb{Z} = \langle 1 \rangle$.

<hr>

Рассмотрим $\sigma: \text{Hom}(\mathbb{Z}, G)$, где $\sigma(k) = x^k$ ( $x \in G$ фиксирован).
- Пусть $\sigma$ инъективен, т.е. $\text{Ker} \ \sigma = {0}$.<br>
Тогда $\sigma : \text{Iso}(\mathbb{Z}, \text{Im} \ \sigma)$, а также $\exists H < G$, где $H$ — **циклическая** и **бесконечная**.

- Пусть $H := \text{Ker} \ \sigma = \{k \cdot d\}_{k \\in \\mathbb{Z}} \leq \mathbb{Z}$; $d := \min H, d > 0, d$ — период $x$.<br>
Тогда $\exists K < G$, где $K$ — **циклическая** и $|K| = d$.

<hr>

**Лемма:** Пусть $G$ — произвольная конечная группа; $|G| = n$; $H := \{x^m\}_{m \ \in \ \mathbb{Z}}$. Тогда $G \ \vdots \ H$.
<br>
**Следствие:** Пусть $|G| = p$ — простое число. Тогда $G$ — циклическая группа, любой элемент которой является образующей $G$.

<hr>

**Теорема:** Пусть $G$ — циклическая группа. Тогда:
1. $H \leq G$ — циклическая.
2. $\sigma \in \text{Hom}(G, G') \Rightarrow \text{Im} \ \sigma$ — циклическая подгруппа $G'$.

<hr>


## 12. Силовские p-подгруппы
Пусть $p \in \mathbb{N}$ — простое число, **p-группой** называется конечная группа, порядок которой равен некоторой степени $p$.

**Лемма 4.7.**: *Всякая p-группа имеет нетривиальный центр*. (т.е. $|Z_{G}| > 1$, где $G$ — p-группа (Более точно: $|Z_{G}| \div p$))

Подгруппа $H \subset G$ группы $G$ называется **p-подгруппой** $G$, если $H$ - p-группа.

**Лемма 4.8.**: Пусть $G$ — конечная абелева группа, порядка $m$, с показателем группы равным $n$, а также $p$ —
простое число делящее $m$. Тогда в $G$ существует подгруппа $H$ порядка $p$.

Подгруппа H называется **силовской p-подгруппой** группы $G$, если $H$ - p-подгруппа и $|H| = p^n$ наибольшая степень $p$, делящая порядок $G$.

**Теорема 5.1.** Пусть $G$ — конечная группа и $p$ — простое число, делящее $|G|$. Тогда в
$G$ существует силовская p-подгруппа.

**Теорема 5.2.** Для всякой конечной группы $G$ каждая p-подгруппа содержится в
некоторой силовской p-подгруппе;

**Теорема 5.3.** Все силовские p-подгруппы конечной группы $G$ сопряжены.

**Теорема 5.4.** Число силовских p-подгрупп в конечной группе $G$ равно $1$ при взятии $p$ по модулю: ($≡ 1 \mod p$)

## 13. Произведения групп: прямое, полупрямое
Пусть $I$ — некоторое множество и для любого $i \in I$, $G_i$ — группа. \
(**Прямым**) **Произведением групп** $\lbrace G_i \rbrace_{i∈I}$ называется декартово произведение $G$ семейства множеств $\lbrace G_i \rbrace_{i∈I}$, снабжённое операцией (∗), так что \
$G = \prod_{i \in I} G_i , (x_i) \ast (y_i) = (x_iy_i), \forall (xi),(yi) \in G,$ \
где введено обозначение: \
$(x_i)_{i \in I} = (x_1, x_2, \dots , x_n, \dots), x_i \in G_i.$ \
\
**Лемма 8.1.** Множество G с введённой операцией (∗) является группой.

**Теорема 8.1.** Группа G вместе с гомоморфизмами проектирования $\lbrace pr_i \rbrace$ образует
произведение семейства $\lbrace G_i \rbrace$ в категории групп $Grp$.

**Теорема 8.2.** (*критерий прямого произведения*) Пусть $G$ — группа и $H, K ≤ G$ — подгруппы $G$, такие что \
$H \cap K = e, HK = KH, HK = G.$ \
Перечисленные условия являются необходимыми и достаточными для того, чтобы \
$H \times  K \simeq G.$ \
\
**Полупрямым произведением** групп $H$ и $K$ называется множество $H \leftthreetimes K$ пар
вида $(h, k)$, с законом композиции: \
$(h_1, k_1)(h_2, k_2) = (h_1h_2, \sigma _{h2}(k_1)k_2), \ \ \sigma : H \times K → K,$ \
где $\sigma _h$ — автоморфизм группы $K$ при действии на ней группы $H$ сопряжениями. \
\
**Лемма 8.2.** Полупрямое произведение групп $H \leftthreetimes K$ является группой.

**Теорема 8.3.** (*критерий полупрямого произведения*) Пусть $G$ — группа и $H, K ≤ G$ — её подгруппы причем \
$H \unlhd G, H \cap K = \lbrace e \rbrace , HK = G,$ \
тогда $H \leftthreetimes  K \simeq G.$
