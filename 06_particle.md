# Particle　粒子
&nbsp;
&nbsp;

## THREE.Vector3

```
var particle = new THREE.Vector3(0,0,0);
```
* XYZ座標を一つの変数に保持できる
* 座標間距離を測るなどベクトルとして使用

&nbsp;
&nbsp;

## THREE.Points

```
var geometry = new THREE.Geometry(); // ジオメトリ
for ( var i = 0; i < 10000; i ++ ) {
  var star = new THREE.Vector3(
    THREE.Math.randFloatSpread(500); X座標を-500〜500間でランダム
    THREE.Math.randFloatSpread(500); Y座標を-500〜500間でランダム
    THREE.Math.randFloatSpread(500); Z座標を-500〜500間でランダム
  );
  geometry.vertices.push(star); // ジオメトリの頂点データを追加
}
var material = new THREE.PointsMaterial( { color: 0x00ff00 } );
var mesh = new THREE.Points(geometry,material);
scene.add(mesh);
```

&nbsp;
&nbsp;

## THREE.PointsMaterial
```
var material = new THREE.PointsMaterial({
  size: 2, // サイズ
  transparent: true, // 透過
  opacity: 0.8, //　透明度
  //map: texture,
  sizeAttenuation: true, //パーティクルの大きさ
  color: 0x00ff00 // 色
});
```

---

