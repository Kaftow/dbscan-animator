<div align="center">
  <h1>DBSCAN 动画演示器</h1>
  <p>
    <em>在 Jupyter Notebook 中进行 DBSCAN （基于密度的聚类算法）的交互式可视化与动画演示</em>
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

本项目包含一个 Jupyter Notebook，用于生成并动态演示 **DBSCAN（Density-Based Spatial Clustering of Applications with Noise，基于密度的聚类算法）** 算法的执行流程。Notebook 提供分步动画，直观展示算法核心步骤：

- 核心点检测
- 核心点间连边
- 簇的逐步形成

通过基于 **ipywidgets** 的交互控件，用户可以实时调整样本点个数、邻域半径和最小点数目在内的算法参数，并能看到基于调整后参数的新聚类动画。

---

## 免安装运行

本项目可直接在浏览器中运行，无需本地安装环境。目前，本项目以支持 **Binder** 和 。点击下方对应按钮，即可在线打开动画演示：

**Binder**:

[![Binder](https://img.shields.io/badge/Binder-Open%20on%20Binder-blue?style=for-the-badge&logo=mybinder&logoColor=white)](https://mybinder.org/v2/gh/Kaftow/dbscan-animator/main?urlpath=voila%2Frender%2Fbuild%2Fdbscan_animator_for_display.ipynb)

**Hugging Face Spaces**:

[![Hugging Face Spaces](https://img.shields.io/badge/Hugging%20Face%20Spaces-Open-orange?style=for-the-badge&logo=huggingface&logoColor=white)](https://huggingface.co/new-space?template=Kaftow/dbscan-animator)

---

## 本地运行

### 环境依赖

如果要运行本项目，请保证你的环境拥有以下库：

- `numpy`
- `matplotlib`
- `networkx`
- `shapely`
- `ipywidgets`

具体版本请参考 requirements.txt。

### 安装指南

<details>
<summary>点击查看安装步骤</summary>

1.  **创建虚拟环境（可选，但强烈推荐）：**

    ```bash
    python -m venv .venv
    source .venv/bin/activate   # Windows: .venv\Scripts\activate
    ```

2.  **安装依赖：**

    ```bash
    pip install -r requirements.txt
    ```

</details>

### 运行和调试笔记本

1.  **编辑笔记本：**
    在 `src` 目录中打开 `dbscan_animator.ipynb` 并按顺序运行单元。通过控制面板调整参数后，点击 **Run Interact** 启动动画并观察结果。

2.  **在本地使用 Voila 展示：**
    默认的笔记本包含大量 Markdown 单元和输出，在直接用 Voila 展示时可能影响观感。建议先生成一个去除了 Markdown 单元与输出的副本，再用 Voila 启动：

    ```bash
    jq '(.cells |= map(select(.cell_type != "markdown") | .outputs = [] | .execution_count = null))' \
      src/dbscan_animator.ipynb > build/dbscan_animator_for_display.ipynb
    ```

    然后运行：

    ```bash
    voila build/dbscan_animator_for_display.ipynb
    ```

    打开 http://localhost:8866 即可查看展示页面。

---

## 实现思路

- **核心算法函数**：实现 DBSCAN 聚类的关键逻辑，包括 `find_core_points`（核心点检测）、`build_core_graph`（核心点连边）、`find_reachable_and_noise`（可达点与噪声识别）。
- **可视化组件函数**：用于绘制数据点、核心圈、连边和簇的多边形轮廓。
- **动画效果**：包括 `radar_animation`（邻域扫描动画）和 `core_connection_animation`（簇连边动画）。
- **流程控制**：`dbscan_workflow` 负责整体流程控制，初始化 UI 并协调各个步骤。

---

## 如何贡献

欢迎提交 Issue 和 Pull Request，贡献时请遵循本仓库的许可协议及贡献指南。

## 许可证

本项目遵循 MIT 许可证，详细信息请参阅 `LICENSE` 文件。
