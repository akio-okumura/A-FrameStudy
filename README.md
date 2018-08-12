# 概要

A-Frameの学習用レポジトリ

2018/08/11 : 学習開始

# 学習記録メモ

### 重力の実装

Don McCurdy’s aframe-physics-system をアタッチすれば実装可。 [リンク](https://aframe.io/docs/0.8.0/introduction/html-and-primitives.html#attaching-components-to-primitives)

```
<script src="https://unpkg.com/aframe-physics-system@1.4.0/dist/aframe-physics-system.min.js"></script>
<a-scene physics>
</a-scene>
```

### environmentの変更

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

### カメラ

```
<a-camera>
  <a-cursor></a-cursor>
</a-camera>
```

カーソルをカメラの子にすることで固定できる。
