# 概要

A-Frameの学習用レポジトリ

2018/08/11 : 学習開始

# 学習記録メモ

## 重力の実装

Don McCurdy’s aframe-physics-system をアタッチすれば実装可。 [リンク](https://aframe.io/docs/0.8.0/introduction/html-and-primitives.html#attaching-components-to-primitives)

```
<script src="https://unpkg.com/aframe-physics-system@1.4.0/dist/aframe-physics-system.min.js"></script>
<a-scene physics>
</a-scene>
```

## environmentの変更

```
<a-scene>
  <a-assets>
    <img id="boxTexture" src="https://i.imgur.com/mYmmbrp.jpg">
    <img id="skyTexture"
      src="https://cdn.aframe.io/360-image-gallery-boilerplate/img/sechelt.jpg">
  </a-assets>

  <a-box src="#boxTexture" position="0 2 -5" rotation="0 45 45" scale="2 2 2"></a-box>

  <a-sky src="#skyTexture"></a-sky>
</a-scene>
```

360度画像をskyに指定すると出来る

<a-assets>を使うと上手く出来ないので、普通にsrcで指定するべき

## カメラ

```
<a-camera>
  <a-cursor></a-cursor>
</a-camera>
```

カーソルをカメラの子にすることで固定できる。

###　VRインタラクティブ

```
<a-box color="red" position="-10 2 -5" rotation="0 0 45" scale="2 2 2">
  <a-animation attribute="position" to="0 2.2 -5" direction="alternate" dur="2000"
    repeat="indefinite"></a-animation>
  <!-- These animations will start when the box is looked at. -->
  <a-animation attribute="scale" begin="mouseenter" dur="300" to="3 3 3"></a-animation>
  <a-animation attribute="scale" begin="mouseleave" dur="300" to="2 2 2"></a-animation>
  <a-animation attribute="rotation" begin="click" dur="2000" to="360 405 45"></a-animation>
</a-box>
```

**mouseenter** : カーソルがオブジェクトに当たった時

**mouseleave** : カーソルがオブジェクトから外れた時

**click** : カーソルがオブジェクト上にある かつ クリックされた時

これでインタラクティブなオブジェクトを作ることが出来る
