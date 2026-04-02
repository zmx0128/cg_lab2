# 3D 图形变换项目

## 📋 项目简介

这是一个使用 Taichi 库实现的 3D 图形变换项目，展示了如何通过矩阵变换实现 3D 物体的旋转和透视投影效果。

## ✨ 功能特性

- **3D 三角形旋转**：实现了三角形的 3D 旋转效果
- **3D 立方体旋转**：实现了立方体的 3D 旋转效果，支持绕 X、Y、Z 轴旋转
- **彩色边效果**：立方体的边使用不同颜色区分，增强视觉效果
- **透视投影**：实现了真实的 3D 透视效果
- **交互式控制**：通过键盘按键控制旋转角度

## 🛠️ 技术实现

- **矩阵变换**：使用模型视图投影 (MVP) 矩阵实现 3D 变换
- **并行计算**：利用 Taichi 的并行计算能力加速顶点变换
- **GUI 渲染**：使用 Taichi 的 GUI 模块实现实时渲染
- **透视投影**：实现了完整的透视投影矩阵计算

## 📁 项目结构

```
cg_lab2/
├── src/
│   ├── main.py          # 3D 三角形旋转
│   └── cube.py          # 3D 立方体旋转
├── .gitignore          
├── .python-version     # Python 版本指定
├── pyproject.toml      
├── uv.lock             
└── README.md           # 项目说明文档
```

## 🚀 环境配置

### 1. 创建并激活Conda虚拟环境

```bash
conda create -n cg_env python=3.12 -y
conda activate cg_env 
```

### 2. 安装依赖

在激活的环境中安装`Taichi`：

```bash
# 安装依赖
pip install taichi
```
### 3.IDE配置

## 🎮 使用方法

### 运行 3D 三角形旋转

```bash
uv run python src/main.py
```

### 运行 3D 立方体旋转

```bash
uv run python src/cube.py
```

## ⌨️ 按键控制

### 3D 三角形控制
- **A**：逆时针旋转
- **D**：顺时针旋转
- **ESC**：退出程序

### 3D 立方体控制
- **W**：绕 X 轴逆时针旋转
- **S**：绕 X 轴顺时针旋转
- **A**：绕 Y 轴逆时针旋转
- **D**：绕 Y 轴顺时针旋转
- **Q**：绕 Z 轴逆时针旋转
- **E**：绕 Z 轴顺时针旋转
- **ESC**：退出程序

## 📄 技术文档

### 矩阵变换原理

项目使用了以下矩阵变换步骤：

1. **模型变换 (Model)**：将物体从局部坐标系变换到世界坐标系
2. **视图变换 (View)**：将相机移动到原点，方便后续计算
3. **投影变换 (Projection)**：将 3D 坐标投影到 2D 屏幕

### 关键函数

- `get_model_matrix()`：生成模型旋转矩阵
- `get_view_matrix()`：生成视图变换矩阵
- `get_projection_matrix()`：生成透视投影矩阵
- `compute_transform()`：在并行架构上计算顶点变换

## 🎨 视觉效果

### 3D 三角形
- 三条边分别使用红、绿、蓝三种颜色
- 可通过 A/D 键控制旋转角度
- 三角形三边加粗效果
  
![cg_lab2](https://github.com/user-attachments/assets/52e87cdc-ad19-472a-bafb-fd46dbfd043d)

- 三角形颜色改变，同时旋转角度改为30°
  
![1](https://github.com/user-attachments/assets/603bade0-936c-460f-a22b-dc7169b61bfa)

- 三角形初始顶点位置改变

![2](https://github.com/user-attachments/assets/78cfddaa-e3f7-42ce-a040-2ff096379326)

  
### 3D 立方体
- 前面的边：粉红色 (0xF040AE)
- 后面的边：紫色 (0xB440F0)
- 连接前后的边：深红色 (0xB50053)
- 可通过 W/S/A/D/Q/E 键控制绕不同轴的旋转

  ![develop](https://github.com/user-attachments/assets/90425f8e-69dc-48ef-ae5d-cb0f3bbe7587)


## 🔧 依赖项

- **Python 3.8+**
- **Taichi 1.7.4+**：用于并行计算和 GUI 渲染

**Happy Coding! 🎉**
