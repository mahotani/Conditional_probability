# 条件付き確率

条件付き確率（じょうけんつきかくりつ、英:conditional probability）は、ある事象Bが起こると言う条件下での別の事象Aの確率のことをいう。条件付き確率は
<a href="https://www.codecogs.com/eqnedit.php?latex=P(A|B)" target="_blank"><img src="https://latex.codecogs.com/gif.latex?P(A|B)" title="P(A|B)" /></a>
または
<a href="https://www.codecogs.com/eqnedit.php?latex=P_B(A)" target="_blank"><img src="https://latex.codecogs.com/gif.latex?P_B(A)" title="P_B(A)" /></a>
のように表される。  
(Wikipediaより)  

と説明が書いてありますが、**正直、よくわかりません ｼｮﾎﾞ━(´·ω·`)━ﾝ**

公式を見てみても、

<a href="https://www.codecogs.com/eqnedit.php?latex=P_B(A)&space;=&space;\frac{P(A&space;\bigcap&space;B)}{P(A)}" target="_blank"><img src="https://latex.codecogs.com/gif.latex?P_B(A)&space;=&space;\frac{P(A&space;\bigcap&space;B)}{P(A)}" title="P_B(A) = \frac{P(A \bigcap B)}{P(A)}" /></a>

これでは、初見さんである大体の高校生たちはいまいちピンときません。

例題で考えてみましょう。

<p class="info">4個の赤玉と5個の白玉が入った袋から取り出した玉は袋に戻さずに2回取り出す．1回目に取り出した玉が赤玉であったとき2回目に取り出す玉が白玉である確率を求めなさい．</p>

この問題をみてピンとこない高校生は、この問題を先ほどの公式に当てはめようと頑張るのですが、何が
<a href="https://www.codecogs.com/eqnedit.php?latex=P(A&space;\bigcap&space;B)" target="_blank"><img src="https://latex.codecogs.com/gif.latex?P(A&space;\bigcap&space;B)" title="P(A \bigcap B)" /></a>
なのか、またどれが
<a href="https://www.codecogs.com/eqnedit.php?latex=P(A)" target="_blank"><img src="https://latex.codecogs.com/gif.latex?P(A)" title="P(A)" /></a>
に当たるのかがよく分かっていない子が多いです。

なので、試しにポケモンを例に当てはめていきましょう。

## 害悪特性”ムラっけ”

オニゴーリとオクタンの夢特性であるムラっけですが、相手にするととても厄介な特性です。

**毎ターン終了時、「こうげき」「ぼうぎょ」「とくこう」「とくぼう」「すばやさ」いずれかのランクが２段階上がり、別のランクが1段階下がる。**

生き残ったターンが多いほど強化されてしまいます。

この特性が第7世代までは、**かいひりつ**と**めいちゅうりつ**も含まれていて、これがまたさらに厄介さを増します。

回避が上がるかもしれない対象に入っていたのです。これがとても厄介なのです。

ポケモンの回避は1段階上昇するとこちらの技が当たる確率が
<a href="https://www.codecogs.com/eqnedit.php?latex=\times&space;\frac{3}{4}" target="_blank"><img src="https://latex.codecogs.com/gif.latex?\times&space;\frac{3}{4}" title="\times \frac{3}{4}" /></a>
、2段階上昇すると
<a href="https://www.codecogs.com/eqnedit.php?latex=\times&space;\frac{3}{5}" target="_blank"><img src="https://latex.codecogs.com/gif.latex?\times&space;\frac{3}{5}" title="\times \frac{3}{5}" /></a>
となります。(こちらの命中に補正がかかっていない場合です。)

1段階上昇でも命中率100のじしんが命中率70のきあいだまよりも「ちょっとは当たるかなぁ」ぐらいのレベルに落ちるのに、2段階上昇ではきあいだまよりも「当たらねぇ」レベルまで落ちてしまいます。  
とびひざげりなんて放っていたら膝が割り放題になってしまいますね。

ちなみに、最大の6段階上昇で
<a href="https://www.codecogs.com/eqnedit.php?latex=\times&space;\frac{1}{3}" target="_blank"><img src="https://latex.codecogs.com/gif.latex?\times&space;\frac{1}{3}" title="\times \frac{1}{3}" /></a>
になってしまいます。辛い・・・

## 実際の問題に当てはめてみる

先ほどの問題をポケモンを使った問題に変えてみます。