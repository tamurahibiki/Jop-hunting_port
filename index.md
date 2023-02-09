<h1> スーパーアクション3D<h1>
河原電子ビジネス専門学校<br>
ゲームクリエイター科　2年　田村響己<br>

<!-- omit in toc -->
# 目次
  <!-- omit in toc -->
- [1. 作品概要](#1-作品概要)
- [2. 操作説明](#2-操作説明)
- [3. ゲームの流れ](#3-ゲームの流れ)
- [4. こだわり・工夫した部分](#4-こだわり工夫した部分)

# 1. 作品概要
## 参考ゲーム
このゲームは、スーパーマリオ3Dワールドを参考にした3Dアクションゲームです。<br>
## 使用エンジン 
学校内製のエンジンを元に作成<br>
## 
<details><summary>作成したコード・シェーダー</summary>

Bloom.h<br>
Bloom.cpp<br>
CollisionObject.h<br>
CollisionObject.cpp<br>
FontRender.h<br>
FontRender.cpp<br>
IRenderer.h<br>
IRenderer.cpp<br>
LightALL.h<br>
LightALL.cpp<br>
ModelRender.h<br>
ModelRender.cpp<br>
PostEffect.h<br>
PostEffect.cpp<br>
RenderingEngine.h<br>
RenderingEngine.cpp<br>
ShadowMapRender.h<br>
ShadowMapRender.cpp<br>
SkyCube.h<br>
SkyCubr.cpp<br>
SpriteRender.h<br>
SpriteRender.cpp<br>
DrawShadowMap.fx<br>
gaussianBlur.fx<br>
light.fx<br>
model.fx<br>
PostEffect.fx<br>
SkyCubeMap.fx<br>
sprite.fx<br>
ZPrepass.fx<br>
</details>

## 使用ツール
Visual Studio 2019<br>
3ds Max 2021<br>
blender<br>
Adobe Photoshop<br>
Effekseer<br>
RenderDoc<br>
## 使用言語
C++<br>
## 開発環境
Windows10  
DirectX12
## 制作人数
1人
## 開発期間
2022年9月～2023年2月

# 2. 操作説明
![Alt text](Slide1.png)
# 3. ゲームの流れ
## ステージ
少年を操作し、ゴールにある宝石を手に入れよう。

<img src="stage1.png" width="700" height=456px ><img src="stage2.png" width="700" height=456px >

## ゲームクリア

## ゲームオーバー

# 4. こだわり・工夫した部分
## 操作
### 待機
一定時間操作していないと待機モーションが変化するようにしました。

<video controls preload width="780" autoplay loop muted="true" poster="![Alt text](Idle_video.png)">
<source src="Idle.mp4"type="video/mp4">
</video>

### 移動

移動をやめた時、現在の速度を徐々に落とす事で慣性が付くようにしました。

カメラの前、右方向とスティックの方向を使いプレイヤーの移動を実装しました。__[1]__<br>
カメラ切り替え時、１フレーム前のカメラ方向を使い移動方向維持するようにしました。__[2]__<br>
スティックの入力方向が変わるか、スティックを離すことで、現在のカメラ方向に移動方向が変わるようにしました。__[3]__<br>

<img src="camera_move1.png" width="400" height=456px ><img src="camera_move2.png" width="400" height=456px ><img src="camera_move3.png" width="400" height=456px >

実際のゲーム画面

<video controls preload width="780" autoplay loop muted="true" poster="![Alt text](move_camera_video">
<source src="move_camera.mp4"type="video/mp4">
</video>

### ジャンプ

ジャンプボタンを押した時間によって、ジャンプ力を変化しました。<br>

<video controls preload width="780" autoplay loop muted="true" poster="![Alt text](jump_video)">
<source src="jump.mp4"type="video/mp4">
</video>

マリオはジャンプした時の軌道が放物線にならないのが特徴的です。これは、上昇速度と下降速度が異なるからです。<br>
そこで、上昇中の重力を弱くし、下降中の重力を強くすることで、再現しました。<br>
![Alt text](jump.png)<br>


### ヒップドロップ
着地してから再度動けるようになる時間を設けました。<br>
## ステージ
### 背景
プレイヤーのモデルに合わせて、ローポリで作成しました。<br>
画面に動きが欲しかったので、所々の背景モデルにアニメーションを追加しました。<br>

<video controls preload width="780" autoplay loop muted="true" poster="![Alt text](stage_video)">
<source src="stage.mp4"type="video/mp4">
</video>

### 鳥
プレイヤーが近づくと各鳥は規定の方向（今回は左斜め前）に飛び立つ。<br>
### 小石
プレイヤーと衝突（近づく）とプレイヤーの回転方向を __一度__ だけ呼び出し、その方向に動かす。<br>
（途中でプレイヤーの方向が変わると小石の方向も変わってしまう為、一度だけ）<br>

## 敵
### 赤い敵（追いかけてくる敵）
<img src="enemy_red.png" width="700" height=456px ><br>
プレイヤーが近づくと追いかけてくるように移動します。（XZ軸移動）

### 黄色い敵（飛んで追いかけてくる敵)
<img src="enemy_yellow.png" width="700" height=456px ><br>
プレイヤーが近づくと追いかけてくるように移動します。（XYZ軸移動）<br>
赤い敵とは違い、飛んで追いかけてくるためY軸も移動させるようにしました。<br>
まったく同じ高さ（Y軸）になると敵を踏んで倒しにくいため、プレイヤーの少し下に追いかけてくるようにしています。<br>

### 硬い敵（遠距離攻撃を行う敵）
<img src="enemy_green.png" width="700" height=456px ><br>
遠距離攻撃を行う敵とヒップドロップでしか倒せない敵が欲しかった為、制作しました。

## ギミック
### 壊せるブロック

### 大砲

<video controls preload width="780" autoplay loop muted="true" poster="![Alt text](fort_video">
<source src="fort.mp4"type="video/mp4">
</video>

プレイヤーが大砲に近づくと大砲のアニメーション再生され発射、 __空中にある当たり判定__ まで移動します。この時、__重力を０__ にします。<br>
そして、空中の当たり判定にプレイヤーが衝突すると、速度を徐々に落とします。また、この時に __重力を元に戻す__ ことで着地します。
<img src="fort.png" width="800" height=456px ><br>

## 演出
### カメラ
所々でカメラの切り替えを行いました。<br>
#### 奥行きを分かりやすくするカメラ<br>

<video controls preload width="780" autoplay loop muted="true" poster="![Alt text](move_camera_video">
<source src="move_camera.mp4"type="video/mp4">
</video>

#### 大砲用のカメラ<br>

<video controls preload width="780" autoplay loop muted="true" poster="![Alt text](fort_video">
<source src="fort.mp4"type="video/mp4">
</video>

#### ゴール用のカメラ<br>


### 影
ジャンプなどの着地先を分かりやすくする為、ライトカメラの方向を真下に設定しました。<br>
プレイヤーの座標を中心に影の濃さを変更しています。(プレイヤーから離れるほど薄くなる）<br>
