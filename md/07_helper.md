# Helper / OrbitControls

&nbsp;
&nbsp;

## Helper 



### THREE.GridHelper

```
var gridHelper = new THREE.GridHelper(200,50);
scene.add(gridHelper);
```
&nbsp;

### THREE.AxisHelper

```
var axisHelper = new THREE.AxisHelper(1000);
scene.add(axisHelper);
```

&nbsp;

###  [DirectionalLightHelper](https://threejs.org/docs/index.html#api/helpers/DirectionalLightHelper)

![](img/lightHelper.png)

```
var lightHelper = new THREE.DirectionalLightHelper(light,20);
scene.add(lightHelper);
```

&nbsp;
&nbsp;

## OrbitControls

Scriptファイルの追加読み込み

`<script src="js/OrbitControls.js"></script>`

```
var controls = new THREE.OrbitControls(camera);
controls = new THREE.OrbitControls(camera);
controls.autoRotate = true; // カメラの自動回転

function tick(){
    requestAnimationFrame(tick);
    controls.update(); // controlsをアップデートさせる
    renderer.render(scene, camera);
}
tick();
```
