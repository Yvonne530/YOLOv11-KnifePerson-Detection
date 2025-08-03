# 🛡️ Knife Detection with YOLOv11

本项目基于 Ultralytics YOLOv11 框架，完成了“拿刀人”视觉检测模型的训练任务。模型能有效检测图像中的“knife”和“person”类别，适用于安防和监控场景。

---

## 📌 项目简介

- **检测框架**：YOLOv11 (Ultralytics 版本 8.3.172)
- **数据集规模**：400张标注图片，包含两类目标：`knife` 和 `person`
- **类别数量**：2
- **训练设备**：NVIDIA GeForce RTX 4070 Laptop GPU + CUDA 11.8
- **训练轮数**：100 epochs
- **图像尺寸**：640×640

---

## 📂 目录结构


---

## 📝 data.yaml 内容

```yaml
train: train/images
val: valid/images
test: test/images
nc: 2
names: ['knife', 'person']


---

## 🚀 环境配置

推荐使用 Python 3.10，PyTorch 2.0.1 + CUDA 11.8。  
安装依赖：

```bash
pip install -r requirements.txt
