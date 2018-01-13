# グループ

&nbsp;


## THREE.Group　グループ
```
var boxes = new THREE.Group();
  for (var i = 0; i < 20; i++) {
    box = new THREE.Mesh(
      new THREE.BoxGeometry(10,10,10),
      new THREE.MeshLambertMaterial({color: Math.random() * 0xffffff})
    );

    box.position.set(
      Math.random() * 100 - 50,
      Math.random() * 100 - 50,
      Math.random() * 100 - 50
    );
    boxes.add(box);
  }
scene.add(boxes);
```



