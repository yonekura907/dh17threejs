# ジオメトリ 

&nbsp;

## Mesh メッシュ 

3Dオブジェクト。メッシュは形状と材質で構成されている。

* 形状オブジェクト　Geometry
* 材質オブジェクト　Material

&nbsp;
&nbsp;




### オブジェクトの配置の流れ
&nbsp;

![](img/Mesh.png)

&nbsp;


#### THREE.Mesh

```
var geometry = new THREE.BoxGeometry(50, 50, 50); 
var material = new THREE.MeshNormalMaterial();
var box = new THREE.Mesh(geometry, material);
scene.add(box);
```

1. Geometryを生成して　
2. Materialを生成して　
3. GeometryとMaterialをまとめて、Meshを生成　
4. Sceneに配置　

&nbsp;
&nbsp;


## Geometry　形状



### [THREE.BoxGeometry](https://threejs.org/docs/index.html#api/geometries/BoxGeometry)  

![](img/BoxGeometry.png)

```
var geometry = new THREE.BoxGeometry(50,50,50); // 幅・高さ・奥行き
var material = new THREE.MeshLambertMaterial({color:0xff0000});
var box = new THREE.Mesh(geometry,material);
scene.add(box);
```   

&nbsp;


#### [THREE.Sphere](https://threejs.org/docs/index.html#api/geometries/SphereGeometry)

![](img/SphereGeometry.png)

```
var geometry = new THREE.SphereGeometry(50, 20, 20), // 直径 頂点の数の幅、高さ
var material = new THREE.MeshLambertMaterial({color:0x4caf50});
var sphere = new THREE.Mesh(geometry,material);
scene.add(sphere);
```


&nbsp;

#### [THREE.Plane](https://threejs.org/docs/index.html#api/geometries/PlaneGeometry)
![](img/PlaneGeometry.png)

```
var geometry = new THREE.PlaneGeometry(200, 200); // 幅・高さ
var material = new THREE.MeshLambertMaterial({color:0x0096d6, side: THREE.DoubleSide}) // 両面を表示するように
var plane = new THREE.Mesh(geometry,material);
plane.rotation.x = THREE.Math.degToRad(90); // 回転
scene.add(plane);
```
&nbsp;

### その他

* [ConeGeometry](https://threejs.org/docs/index.html#api/geometries/ConeGeometry)
* [CylinderGeometry](https://threejs.org/docs/index.html#api/geometries/CylinderGeometry)
* [TorusGeometry](https://threejs.org/docs/index.html#api/geometries/TorusGeometry)

3DモデリングしたOBJファイルを読み込むこともできる

