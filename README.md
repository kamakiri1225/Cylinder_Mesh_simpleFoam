# Cylinder_Mesh_simpleFoam

OpenFOAMで使えるメッシュ生成法を色々試しました。

## 軸対称モデル
- Cylinder_axialSymmetry_laminar
- Cylinder_axialSymmetry_turbulence
![image](https://user-images.githubusercontent.com/36812492/227681981-403d2781-7af2-46cd-9090-15451c3c8c85.png)

```bash
blockMesh
extrudeMesh
createPatch -overwrite
simpleFoam
postProcess -func sampleDict -latestTime
```
![image](https://user-images.githubusercontent.com/36812492/227678413-b3b1bdfe-1e18-4cdc-b1b0-bcc1e0aef953.png)

## blockMesh
- Cylinder_blockMesh_laminar
- Cylinder_blockMesh_turbulence
![image](https://user-images.githubusercontent.com/36812492/227681948-daa52d3b-952a-4afe-afbc-3918745fa17e.png)

```bash
blockMesh
simpleFoam
postProcess -func sampleDict -latestTime
```
![image](https://user-images.githubusercontent.com/36812492/227678420-5ad8234e-f146-4d2e-b46c-9cd71d791b79.png)

## cfMesh
- Cylinder_cfMesh_laminar
- Cylinder_cfMesh_turbulence
![image](https://user-images.githubusercontent.com/36812492/227681968-fa560092-a465-4dd7-ac7d-2329e76400f3.png)

cfMeshはcartesianMeshで別フォルダで作成しています。

作り方はブログ記事をご参考ください。

```bash
simpleFoam
postProcess -func sampleDict -latestTime
```
![image](https://user-images.githubusercontent.com/36812492/227678427-4db3c254-6a72-43f0-99e5-3b6e43c7ed83.png)

## snappyHexMesh
- Cylinder_snappyHexMesh_laminar
- Cylinder_snappyHexMesh_turbulence
![image](https://user-images.githubusercontent.com/36812492/227681954-850b9293-b552-4a97-aafd-d225bd76baf8.png)

```bash
surfaceFeatureExtract
blockMesh
snappyHexMesh -overwrite
simpleFoam
postProcess -func sampleDict -latestTime
```
![image](https://user-images.githubusercontent.com/36812492/227678430-206499c4-710d-4478-aca8-89225cb30044.png)

## ブログ記事
1. [【OpenFOAM(円筒内の流れ)】blockMeshでメッシュ作成(1)](https://takun-physics.net/15282/)
2. [【OpenFOAM(円筒内の流れ)】snappyHexMeshでメッシュ作成(2)](https://takun-physics.net/15416/)
3. [【OpenFOAM(円筒内の流れ)】cfMeshでメッシュ作成(3)](https://takun-physics.net/15439/)
4. [【OpenFOAM(円筒内の流れ)】軸対称モデルでメッシュ作成(4)](https://takun-physics.net/15449/)
5. [【OpenFOAM(円筒内の流れ)】simpleFoamで定常解析(5)](https://takun-physics.net/15423/)
![image](https://user-images.githubusercontent.com/36812492/227678408-41a7e893-6690-4da4-9ced-0f9d1215fd8b.png)

