
# 🩺 Pneumonia Detection on Chest X-rays: Intel Tiber Cloud vs Google Colab

This repository presents a comparative study on training a deep learning model for pneumonia detection using chest X-ray images. The same model architecture was trained and evaluated on:

- 🚀 **Intel Tiber Cloud** (Intel® Xeon® Platinum 8468V CPUs)
- 💻 **Google Colab** (Standard GPU runtime)

---

## 📁 Repository Structure

```
pneumonia-detection-tiber-vs-colab/
│
├── README.md
├── requirements.txt
├── colabchest.ipynb             # Notebook run on Google Colab
├── Chestpneumonia.ipynb         # Notebook run on Tiber Cloud
├── results/
│   ├── colab_metrics.txt        # Training time, accuracy, etc.
│   └── tiber_metrics.txt
├── images/
│   └── comparison_chart.png     # Optional: Grad-CAM or performance chart
└── benchmark/
    └── os_level_summary.md      # OS/CPU/GPU differences
```

---

## 📊 Key Comparisons

| Feature               | Tiber Cloud                  | Google Colab            |
|-----------------------|------------------------------|--------------------------|
| CPU/GPU               | Xeon Platinum 8468V (192T)   | K80/TPU (standard)       |
| Installation Setup    | Pre-installed & optimized    | `%pip install` required  |
| I/O & Disk Speed      | High-speed NVMe              | Moderate                 |
| Training Time (Epoch) | Fast (~X sec)                | Slower (~Y sec)          |
| Final Accuracy        | X%                           | Y%                       |

> See `results/` folder for complete metrics.

---

## 🗃️ Dataset

Dataset: [Chest X-ray Pneumonia (Kaggle)](https://www.kaggle.com/datasets/paultimothymooney/chest-xray-pneumonia)

Downloaded using:
```python
import opendatasets as od
od.download('https://www.kaggle.com/datasets/paultimothymooney/chest-xray-pneumonia')
```

---

## 🧪 How to Use

1. Clone this repo:
```bash
git clone https://github.com/your-username/pneumonia-detection-tiber-vs-colab.git
cd pneumonia-detection-tiber-vs-colab
```

2. Install dependencies:
```bash
pip install -r requirements.txt
```

3. Run either notebook depending on your environment:
- `Chestpneumonia.ipynb` for Intel Tiber Cloud
- `colabchest.ipynb` for Google Colab

---

## 📸 Grad-CAM Visualization (Sample Output)

![Grad-CAM Example](images/comparison_chart.png)

---

## ⚙️ Tiber OS-Level Optimizations

- Multithreaded CPU usage (192 threads)
- Faster training due to disk + memory I/O
- Pre-installed packages and optimized kernel
- Benchmarking with Intel® oneAPI & libraries

See: `benchmark/os_level_summary.md`

---

## 📜 License

This project is licensed under the MIT License.

---

## 🙌 Acknowledgments

- Intel Tiber Cloud Platform
- Google Colab
- Kaggle Datasets
- TensorFlow/Keras
