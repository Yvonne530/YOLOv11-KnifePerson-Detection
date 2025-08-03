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

```
yaml
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


---
##🔧 模型训练
###训练命令
yolo detect train model=yolo11m.pt data=D:/ultralytics-main/ultralytics-main/knife_dataset/data.yaml epochs=100 imgsz=640


---
## 📊 模型评估指标

验证集结果如下：

| 类别   | Precision | Recall | mAP@0.5 | mAP@0.5:0.95 |
|--------|-----------|--------|---------|--------------|
| all    | 0.822     | 0.729  | 0.787   | 0.569        |
| knife  | 0.760     | 0.512  | 0.602   | 0.303        |
| person | 0.885     | 0.947  | 0.972   | 0.834        |

- 模型整体检测效果良好，`person` 类表现尤为突出；
- `knife` 类召回率相对较低，建议结合实际场景进一步优化。

---

## 🔍 模型推理示例

### ✅ 单张图像预测

```bash
yolo detect predict model=runs/detect/train5/weights/best.pt source=sample_images/test1.jpg


pip install -r requirements.txt
