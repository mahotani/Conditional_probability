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

<img width="600" alt="conditional_probability1" src="https://user-images.githubusercontent.com/39772824/76612017-d1d5c380-655e-11ea-88a6-5962b3d5f315.png">

この相手のオニゴーリは先ほどのムラっけオニゴーリを仮定します。

|1ターン目の行動でこちらのギルガルドはオニゴーリを倒した後のことを見越して剣の舞をして攻撃力を高めました。一方、相手のオニゴーリはムラっけの発動のためまもるを選択しました。1ターン目の行動終了時に相手のオニゴーリはムラっけにより回避率を上げてしまいました。この時、2ターン目でギルガルドが命中率90％のせいなるつるぎを当てられる確率はどうなるでしょうか。なお、こちらのギルガルドは、2ターン目の攻撃で倒されることはないものとする。|
|:-:|

<img width="600" alt="conditional_probability2" src="https://user-images.githubusercontent.com/39772824/76614102-c1274c80-6562-11ea-8d97-72a34a5f962c.png">

よく中学生や高校生は確率の問題を解く時に**樹形図**を書いて考えることが多いと思うので、今回の場合も樹形図に書いていきます。

<img width="600" alt="conditional_probability3" src="https://user-images.githubusercontent.com/39772824/76618167-3bf46580-656b-11ea-967b-6193a7a19ac0.png">

流石にこの図だと長すぎてだるいので、分岐が生じている部分だけ抜き出してみます。

<img width="600" alt="conditional_probability4" src="https://user-images.githubusercontent.com/39772824/76623020-fa1cec80-6575-11ea-9be2-47d5057255b3.png">

各確率を書き込んでいきましょう。  
この時、ムラっけが発動するまでは必ず起こる事象なので確率は1になります。

<img width="600" alt="conditional_probability5" src="https://user-images.githubusercontent.com/39772824/76623200-61d33780-6576-11ea-9154-dbf863043570.png">

ムラっけによりかいひりつが上がる確率は、他の各ステータスが上がる確率と同様に確からしいはずなので、
<a href="https://www.codecogs.com/eqnedit.php?latex=\frac{1}{7}" target="_blank"><img src="https://latex.codecogs.com/gif.latex?\frac{1}{7}" title="\frac{1}{7}" /></a>
それ以外が上がる確率は
<a href="https://www.codecogs.com/eqnedit.php?latex=\frac{6}{7}" target="_blank"><img src="https://latex.codecogs.com/gif.latex?\frac{6}{7}" title="\frac{6}{7}" /></a>
になります。

<img width="600" alt="conditional_probability6" src="https://user-images.githubusercontent.com/39772824/76623556-0fdee180-6577-11ea-9908-932f43915733.png">

次は以下の4パターンの確率を求めます。

- かいひりつ上昇 -> せいなるつるぎ成功
    かいひりつが上がった上でせいなるつるぎを当てられる確率は、

    <a href="https://www.codecogs.com/eqnedit.php?latex=\frac{9}{10}&space;\times&space;\frac{3}{5}&space;=&space;\frac{27}{50}" target="_blank"><img src="https://latex.codecogs.com/gif.latex?\frac{9}{10}&space;\times&space;\frac{3}{5}&space;=&space;\frac{27}{50}" title="\frac{9}{10} \times \frac{3}{5} = \frac{27}{50}" /></a>

    さらに、ムラっけでかいひりつが上がる確率は、
    <a href="https://www.codecogs.com/eqnedit.php?latex=\frac{1}{7}" target="_blank"><img src="https://latex.codecogs.com/gif.latex?\frac{1}{7}" title="\frac{1}{7}" /></a>
    なので、これをかけてあげて結果をえる。

    <a href="https://www.codecogs.com/eqnedit.php?latex=\frac{27}{50}&space;\times&space;\frac{1}{7}&space;=&space;\frac{27}{350}" target="_blank"><img src="https://latex.codecogs.com/gif.latex?\frac{27}{50}&space;\times&space;\frac{1}{7}&space;=&space;\frac{27}{350}" title="\frac{27}{50} \times \frac{1}{7} = \frac{27}{350}" /></a>
- かいひりつ上昇 -> せいなるつるぎ失敗
    こちらも上記と同様に求めます。

    <a href="https://www.codecogs.com/eqnedit.php?latex=\frac{23}{50}&space;\times&space;\frac{1}{7}&space;=&space;\frac{23}{350}" target="_blank"><img src="https://latex.codecogs.com/gif.latex?\frac{23}{50}&space;\times&space;\frac{1}{7}&space;=&space;\frac{23}{350}" title="\frac{23}{50} \times \frac{1}{7} = \frac{23}{350}" /></a>
- かいひりつ以外のステータスが上昇 -> せいなるつるぎ成功

    <a href="https://www.codecogs.com/eqnedit.php?latex=\frac{9}{10}&space;\times&space;\frac{6}{7}&space;=&space;\frac{54}{70}" target="_blank"><img src="https://latex.codecogs.com/gif.latex?\frac{9}{10}&space;\times&space;\frac{6}{7}&space;=&space;\frac{54}{70}" title="\frac{9}{10} \times \frac{6}{7} = \frac{54}{70}" /></a>
- かいひりつ以外のステータスが上昇 -> せいなるつるぎ失敗

    <a href="https://www.codecogs.com/eqnedit.php?latex=\frac{1}{10}&space;\times&space;\frac{6}{7}&space;=&space;\frac{6}{70}" target="_blank"><img src="https://latex.codecogs.com/gif.latex?\frac{1}{10}&space;\times&space;\frac{6}{7}&space;=&space;\frac{6}{70}" title="\frac{1}{10} \times \frac{6}{7} = \frac{6}{70}" /></a>

これらを先ほどの樹形図に更新します。

<img width="600" alt="conditional_probability7" src="https://user-images.githubusercontent.com/39772824/76624514-cbecdc00-6578-11ea-9c81-f4d6e68ea0c7.png">
