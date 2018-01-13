# アニメーション

&nbsp;
&nbsp;

## position　座標
#### XYZ同時に指定

```
box.position.set(100,0,0);
```

#### XYZ個別に指定

```
box.position.x = 100;
box.position.y = 50;
box.position.y = 20;
```

&nbsp;


## scale　拡大縮小
#### XYZ同時に指定
```
box.scale.set(2,1,0.5);
```
#### XYZ個別に指定

```
box.scale.x = 2;
box.scale.y = 2;
box.scale.z = 0.5;
```

&nbsp;

## rotation　回転
#### XYZ同時に指定

```
box.rotation.set(THREE.Math.degToRad(70),0,0);
```

#### XYZ個別に指定

```
box.rotation.x = THREE.Math.degToRad(45);
```
&nbsp;

参照: [THREE.Math](https://threejs.org/docs/index.html#api/math/Math)

&nbsp;
&nbsp;

## requestAnimationFrame

```
function tick(){

  // tick関数をrequestAnimationFrameで連続実行
  requestAnimationFrame(tick);

  // ここにアニメーションの指定を記述する


  // レンダリング
  renderer.render(scene, camera);
}

tick(); // tick関数を実行
```

&nbsp;

### アニメーション: オブジェクトを回転


```
function tick(){

  // tick関数をrequestAnimationFrameで連続実行
  requestAnimationFrame(tick);

  // boxのY軸回転をインクリメント
  // boxをグローバル変数に変更する
  box.rotation.y += 0.01;

  renderer.render(scene, camera); // レンダリング
}

tick(); // tick関数を実行
```

&nbsp;



### アニメーション: カメラを回転


```
var angle = 0; // 角度の値を保持する変数

function tick(){
  // tick関数をrequestAnimationFrameで連続実行
  requestAnimationFrame(tick);

  // 角度をインクリメント
  angle += 0.1;
  
  // カメラの軌道
  camera.position.x = Math.cos(THREE.Math.degToRad(angle)) * 300;
  camera.position.z = Math.sin(THREE.Math.degToRad(angle)) * 300;
  camera.lookAt(scene.position); // 原点方向を向く
  
  renderer.render(scene, camera); // レンダリング
}
tick(); // tick関数を実行
```

---

