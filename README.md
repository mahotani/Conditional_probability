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

|4個の赤玉と5個の白玉が入った袋から取り出した玉は袋に戻さずに2回取り出す.1回目に取り出した玉が赤玉であったとき2回目に取り出す玉が白玉である確率を求めなさい．|
|:-:|

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

例えば、このような対面を考えてみましょう。

<img width="300" alt="conditional_probability1" src="https://user-images.githubusercontent.com/39772824/76612017-d1d5c380-655e-11ea-88a6-5962b3d5f315.png">

この相手のオニゴーリは先ほどのムラっけオニゴーリを仮定します。

|1ターン目の行動でこちらのギルガルドはオニゴーリを倒した後のことを見越して剣の舞をして攻撃力を高めました。一方、相手のオニゴーリはムラっけの発動のためまもるを選択しました。1ターン目の行動終了時に相手のオニゴーリはムラっけにより回避率を上げてしまいました。この時、2ターン目でギルガルドが命中率90％のせいなるつるぎを当てられる確率はどうなるでしょうか。なお、こちらのギルガルドは耐久に努力値を振り分けており、2ターン目の攻撃で倒されることはないものとする。|
|:-:|

<img width="300" alt="conditional_probability2" src="https://user-images.githubusercontent.com/39772824/76614102-c1274c80-6562-11ea-8d97-72a34a5f962c.png">

よく中学生や高校生は確率の問題を解く時に**樹形図**を書いて考えることが多いと思うので、今回の場合も樹形図に書いていきます。

<img width="300" alt="conditional_probability3" src="https://user-images.githubusercontent.com/39772824/76618167-3bf46580-656b-11ea-967b-6193a7a19ac0.png">

流石にこの図だと長すぎてだるいので、分岐が生じている部分だけ抜き出してみます。

<img width="300" alt="conditional_probability4" src="https://user-images.githubusercontent.com/39772824/76618167-3bf46580-656b-11ea-967b-6193a7a19ac0.png">

オニゴーリがムラっけを発動するまでは分岐が発生せず、必ず起こる事象なので確率は1になります。

