
# 🩺 Pneumonia Detection on Chest X-rays: Intel Tiber Cloud vs Google Colab

This repository presents a comparative study on training a deep learning model for pneumonia detection using chest X-ray images. The model is trained and evaluated on:

- 🚀 **Intel Tiber Cloud** (Intel® Xeon® Platinum 8468V CPUs)
- 💻 **Google Colab** (Standard GPU runtime)

---

## 📁 Repository Structure

```
pneumonia-detection-tiber-vs-colab/
│
├── README.me
├── colabchest.ipynb             # Notebook run on Google Colab
├── Chestpneumonia.ipynb         # Notebook run on Tiber Cloud
├── colab_metrics.txt        # Training time, accuracy, etc.
│── tiber_metrics.txt
```

---

## 📊 Summary Comparison

| Feature                  | Tiber Cloud                          | Google Colab                     |
|--------------------------|---------------------------------------|----------------------------------|
| CPU/GPU                 | Xeon 8468V (192 Threads)              | 2 vCPU + GPU (likely K80/TPU)    |
| RAM                     | 1.0 TiB (90 GiB free)                 | 12 GiB                           |
| Total Training Time     | ⏱️ 479.97 sec                         | ⏱️ 2533.92 sec                   |
| Avg Time per Epoch      | 95.99 sec                             | 506.78 sec                       |
| Final Train Accuracy    | 98.69%                                | 98.10%                           |
| Final Val Accuracy      | 81.25%                                | 81.25%                           |
| Test Accuracy           | 73.89%                                | 79.11%                           |
| Test Loss               | 1.5470                                | 0.9537                           |

> 📂 Detailed evaluation results are available in the `results/` folder.

---

## 🗃️ Dataset

Dataset: [Chest X-ray Pneumonia (Kaggle)](https://www.kaggle.com/datasets/paultimothymooney/chest-xray-pneumonia)

Used `opendatasets` to download:
```python
import opendatasets as od
od.download('https://www.kaggle.com/datasets/paultimothymooney/chest-xray-pneumonia')
```

---

## 🧪 How to Use

1. Clone the repository:
```bash
git clone https://github.com/your-username/pneumonia-detection-tiber-vs-colab.git
cd pneumonia-detection-tiber-vs-colab
```

2. Install required packages:
```bash
pip install -r requirements.txt
```

3. Run the appropriate notebook:
- `Chestpneumonia.ipynb` for Intel Tiber Cloud
- `colabchest.ipynb` for Google Colab

---

## ⚙️ System Insights

### 🖥️ Tiber Cloud Specs:
- Model: Intel Xeon Platinum 8468V
- Cores: 96 physical / 192 threads
- RAM: 1 TiB
- OS: Ubuntu 22.04
- Optimizations: AVX-512, oneAPI libraries, faster disk I/O

### 💻 Google Colab Specs:
- CPU: 2 vCPUs
- RAM: 12 GiB
- GPU: K80 or TPU (dynamic allocation)
- OS: Debian-based (kernel 6.1.x)

---

## 📜 License

MIT License

---

## 🙌 Acknowledgments

- Intel Tiber Cloud Platform
- Google Colab
- Kaggle Datasets
- TensorFlow/Keras
