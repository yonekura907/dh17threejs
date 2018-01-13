# マテリアルと光源

&nbsp;
&nbsp;


## Material　材質

Materialの種類

* [MeshBasicMaterial](https://threejs.org/docs/index.html#api/materials/MeshBasicMaterial)
	* ライティングを考慮しない陰がつかないマテリアル 
* [MeshNormalMaterial](https://threejs.org/docs/index.html#api/materials/MeshNormalMaterial)
	* ノーマルのカラーをRGBで可視化するマテリアル	
* [MeshLambertMaterial](https://threejs.org/docs/index.html#api/materials/MeshLambertMaterial)
	* 光沢感のないマットな質感。陰影を必要とするのでライトが必要	
* [MeshPhongMaterial](https://threejs.org/docs/index.html#api/materials/MeshPhongMaterial)
	* 光沢感のある質感

&nbsp;

### Materialの設定

![](img/MeshLambertMaterial.png)

```
var sphere = new THREE.Mesh(
    new THREE.SphereGeometry(50, 20, 20),
    new THREE.MeshPhongMaterial({color:0x4caf50})
);
scene.add(sphere);
```

&nbsp;


### ワイヤーフレーム表示
![](img/Wireframe.png)

```
new THREE.MeshPhongMaterial({color:0x4caf50, wireframe:true})
```


&nbsp;



### テクスチャ
![](img/Texture.png)

```
var loader = new THREE.TextureLoader();
var texture = loader.load('img/earthmap1k.jpg');
var sphere = new THREE.Mesh(
  new THREE.SphereGeometry(80, 40, 40),
  new THREE.MeshLambertMaterial({map:texture})
);
```

&nbsp;
&nbsp;



## 光源 light



light の種類

* AmbientLight 環境光源
* DirectionalLight 平行光源
* PointLight 点光源
* SpotLight スポットライト光源

&nbsp;

### [THREE.AmbientLight](https://threejs.org/docs/index.html#api/lights/AmbientLight)


```
// 環境光源
var ambientLight = new THREE.AmbientLight(0x404040); //光の色 ソフトライト
scene.add(ambientLight);
```
&nbsp;



### [THREE.DirectionalLight](https://threejs.org/docs/index.html#api/lights/DirectionalLight)

```
// 平行光源
var directionalLight = new THREE.DirectionalLight(0xffffff, 1); //光の色、光の強さ
directionalLight.position.set(0,100,30);
scene.add(directionalLight);

```

&nbsp;
&nbsp;


## 影

![](img/Shadow.png)

```
renderer.shadowMap.enabled = true;　// レンダラーに影を描画する設定
light.castShadow = true; // ライトに影を出す指定
// 影のサイズを広げる
light.shadow.camera.left = -200;
light.shadow.camera.right = 200;
light.shadow.camera.top = 200;
light.shadow.camera.bottom = -200;
sphere.castShadow = true; // 影を作る対象
plane.receiveShadow = true; // 影を落とす対象
```
---


