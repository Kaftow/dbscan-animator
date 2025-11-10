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

Click the button below to view the animation:

[![Animation Showcase](https://img.shields.io/badge/Animation%20Showcase-Click%20to%20View-blue?style=for-the-badge&logo=mybinder&logoColor=white)](https://mybinder.org/v2/gh/Kaftow/dbscan-animator/main?urlpath=voila%2Frender%2Fdbscan_visual_demo.ipynb)


---

## Run Online (No Local Installation Required)

This project can be run entirely in your browser — **no local installation required** — and offers two options for online execution: **Binder** for interactive, code-free visualization, and **Google Colab** for full notebook editing and experimentation.

### **Binder - Voila Rendered**

For viewers who just want to see and interact with the animations without seeing code or Markdown:

[![Binder Voila](https://img.shields.io/badge/Binder-Voila-blue?style=for-the-badge&logo=mybinder&logoColor=white)](https://mybinder.org/v2/gh/Kaftow/dbscan-animator/main?urlpath=voila%2Frender%2Fdbscan_visual_demo.ipynb)

### **Binder - Original Notebook**

Beyond the Voila-rendered version,there is a fully interactive notebook environment available.

Click here to view, run, and edit all code and Markdown cells within a temporary, interactive environment:

[![Binder Notebook](https://img.shields.io/badge/Binder-Notebook-blue?style=for-the-badge&logo=mybinder&logoColor=white)](https://mybinder.org/v2/gh/Kaftow/dbscan-animator/main?filepath=dbscan_visual_demo.ipynb)

### **Google Colab**

The **Google Colab** version provides a full-featured online Notebook environment.

You can run and modify code directly in your browser, and **save any changes** to your Google Drive:

[![Colab](https://img.shields.io/badge/Colab-Open%20in%20Colab-orange?style=for-the-badge&logo=google-colab&logoColor=white)](https://colab.research.google.com/drive/1PXiiNMHB2bXA8f1UDtxGTtVo6dDa519L?usp=sharing)


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
</details>

### Run the Notebook

1.  **Edit the notebook:**
   Open `dbscan_animator.ipynb` in the `src` directory and run the cells in order. Adjust parameters via the control panel, then click `Run Interact` to start the animation.

2.  **Display with Voila locally:**
  The source notebook contains Markdown cells and outputs that may affect its appearance when served with Voila. It is recommended to create a cleaned copy with Markdown cells removed and outputs cleared beforing serving it with Voila:

  ```bash
  jq '(.cells |= map(select(.cell_type != "markdown") | .outputs = [] | .execution_count = null))' \
    src/dbscan_animator.ipynb > build/dbscan_animator_for_display.ipynb
  ```

  Then run:

  ```bash
  voila build/dbscan_animator_for_display.ipynb
  ```

  Open http://localhost:8866 to view the demo.

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
