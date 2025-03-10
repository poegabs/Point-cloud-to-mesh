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

###Run
python src/main.py

### Visualize 
import open3d as o3d
mesh = o3d.io.read_triangle_mesh("data/mesh_final.ply")
o3d.visualization.draw_geometries([mesh])




# Processamento de Nuvem de Pontos e Reconstrução de Malha

Este projeto implementa um pipeline para processamento de nuvem de pontos e reconstrução de malha 3D utilizando Open3D. Ele realiza filtragem, downsampling, estima normais e reconstrói a superfície usando o método Poisson. O resultado final é uma malha limpa e de alta qualidade, salva em um arquivo `.ply`.

---

## Visão Geral (Português)

### Funcionalidades
- **Carregamento:** Lê um arquivo `.ply` contendo a nuvem de pontos.
- **Filtragem:** Remove pontos ruidosos (outliers) com um filtro estatístico.
- **Downsampling:** Reduz a quantidade de pontos usando uma técnica de voxel.
- **Estimativa de Normais:** Calcula as normais dos pontos para auxiliar na reconstrução.
- **Reconstrução Poisson:** Gera uma malha 3D a partir da nuvem de pontos.
- **Pós-processamento:** Remove vértices e triângulos indesejados, e realiza um recorte com base em uma bounding box.
- **Mapeamento de Cores:** Se a nuvem original possuir cores, elas serão mapeadas para a malha.
- **Visualização:** Exibe a malha processada utilizando a ferramenta de visualização do Open3D.
- **Exportação:** Salva a malha final no arquivo `mesh_final.ply`.

### Como Utilizar
1. **Preparação:**  
   - Instale as dependências:
     ```bash
     pip install -r requirements.txt
     ```
   - Coloque o arquivo `ihrmodificado.ply` na pasta `data/`.

2. **Execução:**  
   Execute o script principal:
   ```bash
   python src/main.py

### Visualização
   import open3d as o3d
mesh = o3d.io.read_triangle_mesh("data/mesh_final.ply")
o3d.visualization.draw_geometries([mesh])


