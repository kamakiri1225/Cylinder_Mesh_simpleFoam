# Cylinder_Mesh_simpleFoam

## 実行方法

## 軸対称モデル
- Cylinder_axialSymmetry_laminar
- Cylinder_axialSymmetry_turbulence

```sh
blockMesh
extrudeMesh
createPatch -overwrite
simpleFoam
postProcess -func sampleDict -latestTime
```

## blockMesh
- Cylinder_blockMesh_laminar
- Cylinder_blockMesh_turbulence

```sh
blockMesh
simpleFoam
postProcess -func sampleDict -latestTime
```

## cfMesh
- Cylinder_cfMesh_laminar
- Cylinder_cfMesh_turbulence

cfMeshはcartesianMeshで別フォルダで作成しています。

作り方はブログ記事をご参考ください。

```sh
simpleFoam
postProcess -func sampleDict -latestTime
```

## snappyHexMesh
- Cylinder_snappyHexMesh_laminar
- Cylinder_snappyHexMesh_turbulence

```sh
surfaceFeatureExtract
blockMesh
snappyHexMesh -overwrite
simpleFoam
postProcess -func sampleDict -latestTime
```

## ブログ記事
1. [【OpenFOAM(円筒内の流れ)】blockMeshでメッシュ作成(1)](https://takun-physics.net/15282/)
2. [【OpenFOAM(円筒内の流れ)】snappyHexMeshでメッシュ作成(2)](https://takun-physics.net/15416/)
3. [【OpenFOAM(円筒内の流れ)】cfMeshでメッシュ作成(3)](https://takun-physics.net/15439/)
4. [【OpenFOAM(円筒内の流れ)】軸対称モデルでメッシュ作成(4)](https://takun-physics.net/15449/)
5. [【OpenFOAM(円筒内の流れ)】simpleFoamで定常解析(5)](https://takun-physics.net/15423/)
