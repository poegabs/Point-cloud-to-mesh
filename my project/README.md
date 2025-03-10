# Point Cloud Processing and Mesh Reconstruction


## Overview (English)
This repository contains a Python script that processes a point cloud using Open3D. The goal is to apply filtering, normal estimation, and mesh reconstruction to obtain a clean, high-quality 3D model.

## Features
- Loads a `.ply` point cloud file.
- Removes statistical outliers.
- Downsamples the cloud using a voxel grid.
- Estimates normals and applies Poisson surface reconstruction.
- Removes low-density vertices and disconnected components.
- Crops the mesh within a bounding box.
- Optionally maps colors from the original point cloud.
- Saves the final mesh as `mesh_final.ply`.

## Dependencies
To run this project, install the required packages:
```bash
pip install -r requirements.txt
```
## Run
Execute the main script: 
```BASH
python src/main.py
```
## Visualize 
To view the generated mesh, run:
```bash
import open3d as o3d
mesh = o3d.io.read_triangle_mesh("data/mesh_final.ply")
o3d.visualization.draw_geometries([mesh])
```

# Processamento de Nuvem de Pontos e Reconstrução de Malha

## Visão Geral (Português)
Este projeto implementa um pipeline para processamento de nuvem de pontos e reconstrução de malha 3D utilizando Open3D. Ele realiza filtragem, downsampling, estima normais e reconstrói a superfície usando o método Poisson. O resultado final é uma malha limpa e de alta qualidade, salva em um arquivo .ply.

## Funcionalidades
- Carregamento: Lê um arquivo .ply contendo a nuvem de pontos.
- Filtragem: Remove pontos ruidosos (outliers) com um filtro estatístico.
- Downsampling: Reduz a quantidade de pontos usando uma técnica de voxel.
- Estimativa de Normais: Calcula as normais dos pontos para auxiliar na reconstrução.
- Reconstrução Poisson: Gera uma malha 3D a partir da nuvem de pontos.
- Pós-processamento: Remove vértices e triângulos indesejados, e realiza um recorte com base em uma bounding box.
- Mapeamento de Cores: Se a nuvem original possuir cores, elas serão mapeadas para a malha.
- Visualização: Exibe a malha processada utilizando a ferramenta de visualização do Open3D.
- Exportação: Salva a malha final no arquivo mesh_final.ply.

## Preparação
Instale as dependências:
```bash
pip install -r requirements.txt
```
## Execução 
Execute o script principal:
```BASH
python src/main.py
```
## Visualização
Para visualizar a malha gerada, execute:
```bash
import open3d as o3d
mesh = o3d.io.read_triangle_mesh("data/mesh_final.ply")
o3d.visualization.draw_geometries([mesh])
```



