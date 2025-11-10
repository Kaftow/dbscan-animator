<div align="center">
  <h1>DBSCAN Animator</h1>
  <p>
    <em>Interactive DBSCAN visualization and animation in Jupyter Notebook.</em>
  </p>
  <p>
  <a href="./README.md"><strong>English</strong></a> |
  <a href="./README.zh-CN.md"><strong>中文</strong></a>
</p>

  <p>
    <a href="LICENSE"><img src="https://img.shields.io/badge/License-MIT-yellow.svg" alt="License: MIT"></a>
    <a href="https://www.python.org/"><img src="https://img.shields.io/badge/python-3.8%2B-blue?logo=python" alt="Python"></a>
  </p>
  <p>
    <img src="https://img.shields.io/badge/numpy-%23013243.svg?style=for-the-badge&logo=numpy&logoColor=white" alt="NumPy">
    <img src="https://img.shields.io/badge/matplotlib-%23ffffff.svg?style=for-the-badge&logo=matplotlib&logoColor=black" alt="Matplotlib">
    <img src="https://img.shields.io/badge/NetworkX-white?style=for-the-badge&logo=networkx&logoColor=black" alt="NetworkX">
  </p>
</div>

This repository provides a Jupyter Notebook for interactive visualization and animation of the **DBSCAN (Density-Based Spatial Clustering of Applications with Noise)** algorithm. The notebook illustrates the algorithm step by step, including:

- Core point detection
- Connecting core points
- Formation of clusters

With **ipywidgets** interactive controls, users can adjust algorithm parameters in real time—such as the number of sample points, neighborhood radius, and minimum points—and immediately see how these changes affect the clustering results through dynamic animations.

---

## Run Online (No Local Installation Required)

You can run the notebook directly in your browser without installing anything locally. The interactive demo is available via **Binder** or **Hugging Face Spaces**. Click the badges below to launch the demo:

**Binder:**  
[![Binder](https://img.shields.io/badge/Binder-Open%20on%20Binder-blue?style=for-the-badge&logo=mybinder&logoColor=white)](https://mybinder.org/v2/gh/Kaftow/dbscan-animator/main?urlpath=voila%2Frender%2Fdbscan_visual_demo.ipynb)

**Hugging Face Spaces:**  
[![Hugging Face Spaces](https://img.shields.io/badge/Hugging%20Face%20Spaces-Open-orange?style=for-the-badge&logo=huggingface&logoColor=white)](https://huggingface.co/new-space?template=Kaftow/dbscan-animator)

---

## Local Run

### Environment & Dependencies

To run this project locally, make sure your environment has the following Python packages installed (see `requirements.txt` for specific versions):

- `numpy`
- `matplotlib`
- `networkx`
- `shapely`
- `ipywidgets`

### Installation Guide

<details>
<summary>Click to view installation steps</summary>

1.  **Create a virtual environment (optional but recommended):**

    ```bash
    python -m venv .venv
    source .venv/bin/activate   # Windows: .venv\Scripts\activate
    ```

2.  **Install dependencies:**

    ```bash
    pip install -r requirements.txt
    ```

3.  **Enable interactive plots (optional):**
The notebook uses `%matplotlib widget`. To enable this, install `ipympl`:
`bash
    pip install ipympl
    `
</details>

### Run the Notebook

1.  **Launch Jupyter:**
    ```bash
    jupyter lab   # or jupyter notebook
    ```
2.  **Open and run the notebook:**
    Open `dbscan_visual_demo.ipynb` and run the cells. Use the control panel to adjust parameters and click **Run Interact** to start the animation.

---

## Implementation

- **Core DBSCAN Functions:** Implements main DBSCAN logic with `find_core_points`, `build_core_graph`, and `find_reachable_and_noise`.
- **Visualization Tools:** Functions for plotting points, core circles, connections, and cluster polygons.
- **Animations:** `radar_animation` for neighborhood scanning and `core_connection_animation` to visualize cluster connections.
- **Workflow:** `dbscan_workflow` handles the UI and coordinates the step-by-step animation.

---

## Contributing

Feel free to open Issues or Pull Requests! Please follow the repository's license and contribution guidelines.

## License

MIT License — see the `LICENSE` file for details.
