# Clustering Research Lab

Bienvenido a la documentación del proyecto.

Este laboratorio combina una investigación teórica sobre algoritmos de clustering con pequeños experimentos prácticos y funcionalidades de documentación de GitHub.

## Contenido

- Fundamentos del aprendizaje no supervisado
- Tipos de clustering
- Evaluación de agrupamientos
- Comparación de algoritmos
- Experimentos visuales

```mermaid
flowchart LR
    A[Dataset] --> B[Preprocesamiento]
    B --> C[K-Means]
    B --> D[Jerárquico]
    B --> E[DBSCAN]
    B --> F[GMM]
q

## Configurar MkDocs

```bash
cat > mkdocs.yml <<'EOF'
site_name: Clustering Research Lab
site_description: Investigación y experimentación sobre algoritmos de clustering
repo_name: clustering-research-lab

theme:
  name: material
  language: es

nav:
  - Inicio: index.md
  - Fundamentos: fundamentals.md
  - Algoritmos: algorithms.md
  - Evaluación: evaluation.md
  - Conclusiones: conclusions.md

markdown_extensions:
  - admonition
  - tables
  - toc:
      permalink: true
  - pymdownx.details
  - pymdownx.superfences:
      custom_fences:
        - name: mermaid
          class: mermaid
          format: !!python/name:pymdownx.superfences.fence_code_format
