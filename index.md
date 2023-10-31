<h1> スーパーアクション3D<h1>
河原電子ビジネス専門学校<br>
ゲームクリエイター科　田村響己<br>

<!-- omit in toc -->
# 目次
  <!-- omit in toc -->
- [1. 作品概要](#1-作品概要)
- [2. 操作説明](#2-操作説明)
- [3. ゲーム内容](#3-ゲーム内容)
- [4. こだわり・工夫した部分](#4-こだわり工夫した部分)
- [5. 技術的部分](#5-技術的部分)



# 1. 作品概要

<iframe width="560" height="315" src="https://www.youtube.com/embed/LGooSktOw0s" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share" allowfullscreen></iframe>


## タイトル
## _スーパーアクション３D_<br>
## ゲームジャンル
アクションゲーム
## 参考ゲーム
スーパーマリオ3Dワールド<br>
## 使用エンジン 
学校内製の簡易エンジンを改造(DirectX12)<br>
## 開発環境
Windows10<br>
DirectX12<br>
## 使用言語
C++<br>
HLSL<br>
## 使用ツール
### ・プログラム
Visual Studio 2019<br>
### ・モデル
3ds Max <br>
blender<br>
### ・画像
Adobe Photoshop<br>
### ・エフェクト
Effekseer<br>
### ・グラフィックデバッグ
RenderDoc<br>
### ・バージョン管理
Github<br>
### ・スケジュール管理
Notion<br>
## 作成したソースコード
### ゲーム部分(cpp,h)<br>

Bard.cpp<br>
Bard.h<br>
Block.cpp<br>
Block.h<br>
Default.cpp<br>
Default.h<br>
Dokan.cpp<br>
Dokan.h<br>
Enemy_Green.cpp<br>
Enemy_Green.h<br>
Enemy_Red.cpp<br>
Enemy_Red.h<br>
Enemy_Yellow.cpp<br>
Enemy_Yellow.h<br>
Fade.cpp<br>
Fade.h<br>
Fence.cpp<br>
Fence.h<br>
FenceHalf.cpp<br>
FenceHalf.h<br>
Flower.cpp<br>
Flower.h<br>
FlowerBed.cpp<br>
FlowerBed.h<br>
Fort.cpp<br>
Fort.h<br>
FortTop.cpp<br>
FortTop.h<br>
Forward.cpp<br>
Forward.h<br>
Game.cpp<br>
Game.h<br>
GameCamera.cpp<br>
GameCamera.h<br>
GoalPoint.cpp<br>
GoalPoint.h<br>
Grass.cpp<br>
Geass.h<br>
Ground.cpp<br>
Ground.h<br>
GroundRoad.cpp<br>
GroundRoad.h<br>
GroundMove.cpp<br>
GroundMove.h<br>
HitBox.cpp<br>
HitBox.h<br>
IActor.cpp<br>
IActor.h<br>
IBgActor.cpp<br>
IBgActor.h<br>
IEnemy.cpp<br>
IEnemy.h<br>
main.cpp<br>
Puddle.cpp<br>
Puddle.h<br>
Pebble.cpp<br>
Pebble.h<br>
Pipe.cpp<br>
Pipe.h<br>
Player.cpp<br>
Player.h<br>
Player_Head.cpp<br>
Player_Head.h<br>
Ring.cpp<br>
Ring.h<br>
Rock_Big.cpp<br>
Rock_Big.h<br>
SignBoard.cpp<br>
SignBoard.h<br>
Stairs.cpp<br>
Stairs.h<br>
Shell.cpp<br>
Shell.h<br>
Shrub.cpp<br>
Shrub.h<br>
Title.cpp<br>
Title.h<br>
Tree.cpp<br>
Tree.h<br>
Windmill.cpp<br>
Windmill.h<br>
Wood_Road.cpp<br>
Wood_Rock.h<br>
WoodenBox.cpp<br>
WoodenBox.h<br>

### エンジン部分(cpp,h)<br>

Bloom.cpp<br>
Bloom.h<br>
CollisionObject.cpp<br>
CollisionObject.h<br>
FontRender.cpp<br>
FontRender.h<br>
Fxaa.cpp<br>
Fxaa.h<br>
IRenderer.cpp<br>
IRenderer.h<br>
LightALL.cpp<br>
LightALL.h<br>
ModelRender.cpp<br>
ModelRender.h<br>
OutLine.cpp<br>
OutLine.h<br>
PostEffect.cpp<br>
PostEffect.h<br>
RenderingEngine.cpp<br>
RenderingEngine.h<br>
ShadowMapRender.cpp<br>
ShadowMapRender.h<br>
SkyCube.cpp<br>
SkyCubr.h<br>
SpriteRender.cpp<br>
SpriteRender.h<br>
Ssr.cpp<br>
Ssr.h<br>

### シェーダー部分(fx)<br>

DrawShadowMap.fx<br>
fxaa.fx<br>
gaussianBlur.fx<br>
light.fx<br>
model.fx<br>
outline.fx<br>
PostEffect.fx<br>
SkyCubeMap.fx<br>
sprite.fx<br>
Ssr.fx<br>
ZPrepass.fx<br>


## 制作人数
1人
## 開発期間
2022年10月～2023年3月<br>
2023年6月 スクリーンスペースリフレクション(SSR)追加<br>
2023年7月 Fast Approximate Anti-Aliasing(FXAA)<br>
　　　　　輪郭線追加<br>


# 2. 操作説明
![Alt text](Slide1.png)
# 3. ゲーム内容
## ゲームの流れ
少年を操作し、ゴールにある宝石を手に入れよう。<br>

<img src="stage1.png" width="700" height=456px ><img src="stage2.png" width="700" height=456px >

__ゲームクリア__<br>
ゴールにある宝石を手に入れるとゲームクリアです。<br>
<img src="goal.png" width="700" height=456px >

__ゲームオーバー__<br>
左上に表示されている残機が０になるか、右上に表示されている制限時間が０になるとゲームオーバーです。<br>
残機は、敵に倒されるかステージ外に落ちると１ずつ減っていきます。<br>
残機が減った場合、規定の位置に戻ります。<br>
<img src="stage_video.png" width="700" height=456px >


# 4. こだわり・工夫した部分

## 操作
### 待機
様々な既存のゲームで操作をせずにしていると、キャラクター独自のモーションに変化することを参考にしました。<br>
一定時間操作していないと待機モーションが変化するようにしました。<br>

<video controls preload width="780" autoplay loop muted="true" poster="![Alt text](Idle_video.png)">
<source src="Idle.mp4"type="video/mp4">
</video>

### 移動

Lスティック＋ダッシュボタンでプレイヤーがダッシュします。<br>
一定時間ダッシュし続けるとスーパーダッシュに変化します。<br>
通常ダッシュとスーパーダッシュでは、速度が異なります。<br>
通常ダッシュでは超えられない場所も、スーパーダッシュで超えることが出来ます。<br>

歩き、ダッシュ、スーパーダッシュの差別化<br>

<video controls preload width="780" autoplay loop muted="true" poster="![Alt text](walk_dash_video">
<source src="walk_dash.mp4"type="video/mp4">
</video>

### __共通の仕様__
移動をやめた時、現在の速度を徐々に落とす事で慣性が付くようにしました。<br>

__カメラ切り替え時の移動処理__<br>
カメラを途中で切り替えた時、プレイヤーの移動方向が急に変わり操作のしづらさを感じたため、既存の3Dゲームを参考に実装しました。<br>

カメラの前、右方向とスティックの方向を使いプレイヤーの移動を実装しました。__[1]__<br>
カメラ切り替え時、１フレーム前のカメラ方向を使い移動方向維持するようにしました。__[2]__<br>
スティックの入力方向が変わるか、スティックを離すことで、現在のカメラ方向に移動方向が変わるようにしました。__[3]__<br>

<img src="camera_move1.png" width="400" height=456px ><img src="camera_move2.png" width="400" height=456px ><img src="camera_move3.png" width="400" height=456px >

実際のゲーム画面<br>

<video controls preload width="780" autoplay loop muted="true" poster="![Alt text](move_camera_video">
<source src="move_camera.mp4"type="video/mp4">
</video>

-------------------------------------------------

__ジャンプ__<br>
敵を踏んで倒す、ブロックを破壊する時に使います。<br>
ジャンプをすると再び着地するまでジャンプ出来ませんが、ジャンプで敵を倒すと再びジャンプすることが出来ます。<br>

ジャンプボタンを押した時間によって、ジャンプ力が変化します。<br>

<video controls preload width="780" autoplay loop muted="true" poster="![Alt text](jump_video)">
<source src="jump.mp4"type="video/mp4">
</video>

マリオはジャンプした時の軌道が放物線にならないのが特徴的です。これは、上昇速度と下降速度が異なるからです。<br>
そこで、上昇中の重力を弱くし、下降中の重力を強くすることで、再現しました。<br>
これにより、狙った地点へ速く着地することができます。<br>

<img src="jump.png" width="780" height=456px >

-------------------------------------------------

__ヒップドロップ__<br>
空中でヒップドロップボタンを入力でプレイヤーがヒップドロップします。<br>
敵を倒す、ブロックを破壊する用途の他に、素早く真下に着地することが出来ます。<br>
ヒップドロップ中はLスティックの操作は効かないようにしています。<br>
アニメーションイベントを利用して、回転中は重力を０に、回転後は強い重力を与えています。<br>

*問題点と解決*<br>
しかし、ヒップドロップで敵を倒そうとすると、プレイヤーの落下速度が速すぎて敵を倒せていても敵の攻撃判定に衝突し相打ちしてしまう（敵が倒れる時に敵の攻撃判定も消える為）ので、ヒップドロップ落下中は無敵にする事にしました。<br>

ですが、無敵にしてしまうと全ての敵を安全に倒せるようになってしまうと考え、着地してから再度動けるようになる時間を長めに設定しました。<br>
これにより、目の前の敵に対してヒップドロップを外す、または別の敵に攻撃されるリスクを付けバランスを調整しました。<br>

<video controls preload width="780" autoplay loop muted="true" poster="![Alt text](hipdrop_video)">
<source src="hipdrop.mp4"type="video/mp4">
</video>

## ステージ
### 背景
プレイヤーのモデルに合わせて、ローポリゴンで作成しました。<br>
画面に動きが欲しかったので、所々の背景モデルにアニメーションを追加しました。<br>

<img src="stage3.png" width="780" height=456px ><br>

<video controls preload width="780" autoplay loop muted="true" poster="![Alt text](stage_video)">
<source src="stage.mp4"type="video/mp4">
</video>

## 敵
### <span style="color: red; ">スライム</span>（追いかけてくる敵）
<img src="enemy_red.png" width="700" height=456px ><br>
プレイヤーを見つけると地面を素早く跳ねて追いかけてきます。（XZ軸移動）<br>
段差を降りることは出来ますが登るのことは出来ません。<br>

### <span style="color: orange; ">ハチ</span>（飛んで追いかけてくる敵)
<img src="enemy_yellow.png" width="700" height=456px ><br>
プレイヤーが近づくと追いかけてくるように移動します。（XYZ軸移動）<br>
<span style="color: red; ">スライム</span>とは違い、飛んで追いかけてくるためY軸も移動させるようにしました。<br>
<span style="color: red; ">スライム</span>と違い段差を無視出来ますが、ダッシュで逃げ切れるほど移動速度が遅くなっています。<br>
プレイヤーと全く同じ高さで追いかけてくると踏んで倒しにくいため、プレイヤーの少し下を追いかけてくるようにしています。<br>


### <span style="color: gray; ">ロボット</span>（遠距離攻撃を行う敵）
<img src="enemy_green.png" width="700" height=456px ><br>
砲弾を発射し攻撃してくる遠距離エネミーです。<br> 
本体に攻撃判定はありませんが、ジャンプでは倒せずヒップドロップを使う必要があります。<br>
また、砲弾を踏むことで、距離を詰めやすくなります。<br>
遠距離攻撃を行う敵とヒップドロップでしか倒せない敵が欲しかった為、制作しました。<br>

__基本的な当たり判定__<br>
敵の側面からぶつかるとプレイヤーが死亡し、真上から踏むと敵が死亡します。<br>

<img src="enemy_red2.png" width="780" height=456px ><br>

<video controls preload width="780" autoplay loop muted="true" poster="![Alt text](block_video">
<source src="enemy_down.mp4"type="video/mp4">
</video>

## ギミック
__壊せるブロック__<br>

<video controls preload width="780" autoplay loop muted="true" poster="![Alt text](block_video">
<source src="block.mp4"type="video/mp4">
</video>

_当たり判定_<br>

プレイヤーの足元の判定とブロックの当たり判定が衝突すると、プレイヤーの重力が０になります。__[１]__<br>
プレイヤーの頭上の判定・ヒップドロップの判定とブロックの当たり判定が衝突すると、ブロックが破壊されます。__[2]__<br>
これだけでは、プレイヤーがブロックの真横から衝突しようとするとブロックを貫通してしまう為、プレイヤーの身体に当たり判定を追加してブロックの当たり判定と衝突すると、プレイヤーのXZの移動速度を０にすることでブロックに当たって止まっているように見せました。__[1]__<br>

<img src="block1.png" width="400" height=456px ><img src="block2.png" width="400" height=456px ><br>

__大砲__<br>

<video controls preload width="780" autoplay loop muted="true" poster="![Alt text](fort_video">
<source src="fort.mp4"type="video/mp4">
</video>

プレイヤーが大砲に近づくと大砲のアニメーション再生され発射、 __空中にある当たり判定__ まで移動します。この時、__重力を０__ にします。<br>
そして、空中の当たり判定にプレイヤーが衝突すると、速度を徐々に落とします。また、この時に __重力を元に戻す__ ことで着地します。<br>
<img src="fort.png" width="780" height=456px ><br>


## 演出
__カメラ__<br>
所々でカメラの切り替えを行いました。<br>
__奥行きを分かりやすくするカメラ__<br>

<video controls preload width="780" autoplay loop muted="true" poster="![Alt text](move_camera_video">
<source src="move_camera.mp4"type="video/mp4">
</video>

__大砲用のカメラ__<br>

<video controls preload width="780" autoplay loop muted="true" poster="![Alt text](fort_video">
<source src="fort.mp4"type="video/mp4">
</video>

__ゴール用のカメラ__<br>
プレイヤーをターゲットとして、宝石と一直線の角度になるように視点を計算しています。<br>
このため、どの方向から宝石に近づいても、プレイヤーを正面から見ることができます。<br>

<video controls preload width="780" autoplay loop muted="true" poster="![Alt text](goal_video">
<source src="goal.mp4"type="video/mp4">
</video>

<img src="goal_camera.png" width="780" height=456px >

-------------------------------------------------
__影__<br>
ジャンプなどの着地先を分かりやすくする為、ライトカメラの方向を __真下__ に設定しました。<br>

<img src="stage1.png" width="780" height=456px >

プレイヤーの座標を中心に __影の濃さ__ を変更しています。（プレイヤーから離れるほど薄くなる）<br>
これにより少しでも、処理負荷を掛けないようにしています。<br>

<video controls preload width="780" autoplay loop muted="true" poster="![Alt text](shadow_video.png">
<source src="shadow.mp4"type="video/mp4">
</video>

<img src="shadow_camera.png" width="780" height=456px >

# 5. 技術的部分
## スクリーンスペース・リフレクション(SSR)
<img src="ssr.png" width="780" height=456px >

### 基本的なアルゴリズム
まず，一度シーンを描画します。そのとき、カメラ空間における位置情報、深度情報と法線情報を出力します。<br>
__出力した深度テクスチャ__<br>
<img src="ssr_depht.png" width="780" height=456px >

__出力した法線テクスチャ__<br>
<img src="ssr_normal.png" width="780" height=456px >

また、今回は部分的に反射させたいため、 スムースネステクスチャからスムースの値（α）にアクセスし1.0の  箇所だけ反射するようにする。<br>
__出力したスムースネステクスチャ__<br>

<img src="ssr_specular.png" width="780" height=456px >

次にカメラ位置からスクリーン上の各ピクセルにおける位置に向かうベクトルと法線ベクトルから反射ベクトルを求めます。位置から反射ベクトル方向に深度バッファを使い、物体と交差したときに、その位置を投影したピクセルをサンプリングして周囲からの反射光として計算します。反射を計算したシーンはアーティファクトが目立ってしまうので、ぼかしをかけます。そして、元のシーンを合成します。<br>

__反射ベクトルを使ってシーンとの衝突判定を行う。__<br>
<img src="ssr_ar.png" width="780" height=456px >

__出力した反射テクスチャ・ぼかし無し__<br>
<img src="ssr_ssr.png" width="780" height=456px >

__出力した反射テクスチャ・ぼかし有りの一部__<br>
<img src="ssr_blur.png" width="780" height=456px >

__合成されたシーン・ぼかし有り__<br>
<img src="ssr.png" width="780" height=456px >

__全反射・ぼかし無しの場合__<br>
<img src="ssr_all.png" width="780" height=456px >

-------------------------------------------------
## Fast Approximate Anti-Aliasing(FXAA)
### Fast Approximate Anti-Aliasing(FXAA)とは？<br>
Fast Approximate Anti-Aliasing(以下、FXAA)とは、すばやく近似するアンチエイリアシングと言うことで、他のアンチエイリアシング技法と比べて軽く、簡単にジャギーを軽減することができる技法。<br>

FXAAの手法は極めてシンプルなもので、「ピクセル色を周囲と比較して輝度差を調べ，輝度差があるピクセルの色は周囲と混ぜ合わせる」というものになっている。<br>
たとえば、背景とオブジェクトには大きな輝度差があるとしよう。このとき、あるピクセルで周囲との輝度の差を調べ、輝度の差があれば、オブジェクトの縁の部分がピクセルに乗っている可能性があると判断できる。ピクセルの輝度の差（＝輝度差の大きいピクセルのエッジ）をとっていくことで、オブジェクトの縁（へり）を推定できるわけだ。<br>
そしてこの「推定できた縁」に沿って、「縁が横切る比率」に基づいてピクセルの色を混ぜ、それによって輪郭をぼかそうというのがFXAAの基本的な考え方になる。<br>

<img src="fxaa_pikuseru.jpg" width="780" height=456px >

FXAAではサブピクセルを使わずに済むのが利点だ。要は、2Dレベルの画像処理で、ギザギザ感を低減できる。また、輝度の差があればブレンドが行われるので、テクスチャに描かれた線のようなものに対しても有効に機能する。<br>
<br>
<br>
実際のゲームではポストエフェクトとしてFXAA処理が行われるのだが「FXAAのシェーダコードはかなり長い」ものの「レイテンシは0.1msやその程度で済む」と竹重氏は述べていた。輪郭を検出して色のブレンドを行う処理は相応に複雑だが、「深度が格納されているバッファ（＝Zバッファ）を参照する」作業が不要で、かつ、現在のGPUはシェーダコード――より具体的に言えばピクセルシェーダのコード――を高速に実行できるため、FXAAのレイテンシは極めて低いのだろう。つまり、GPUで長いシェーダコードを高速に実行できるようになったからこそ可能になったAA技法と述べていいかもしれない。

引用元 [https://www.4gamer.net/games/120/G012093/20121125002/](https://www.4gamer.net/games/120/G012093/20121125002/)<br>

### シーンに描画する
1,まず、FXAAをかけた絵を描画するためのFXAA用のレンダリングターゲットを切り替えます。<br>
2.元シーンをテクスチャとしてスプライトを描画し、アンチをかけます。<br>
3.レンダリングターゲットを元シーンに切り替え、2のスプライトを描画します。<br>

<img src="fxaa_kaisetu.png" width="780" height=456px >

__FXAA無し(元シーン)の場合__<br>
<img src="fxaa_off.png" width="780" height=456px >

__FXAAありの場合__<br>
<img src="fxaa_on.png" width="780" height=456px >

-------------------------------------------------
## 輪郭線
考え方は、Fast Approximate Anti-Aliasing(FXAA)と似ており、ピクセル色を周囲と比較して深度値の差を調べ、深度値の差があるピクセルの色を輪郭線（今回は黒色）として描画します。

__輪郭線無しの場合__<br>
<img src="notoutline.png" width="780" height=456px >

__輪郭線ありの場合__<br>
<img src="outline.png" width="780" height=456px >