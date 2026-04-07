Here’s a clean, professional **GitHub README.md** based on your paper. You can copy-paste this directly into your repo.

---

# 🌍 Where Do Vision-Language Models Fail?

### World-Scale Analysis for Image Country Geolocalization


## 📌 Overview

This project presents a **systematic benchmark of Vision-Language Models (VLMs)** for **country-level image geolocalization** using **ground-view images only**.

Unlike traditional approaches that rely on:

* image retrieval
* GPS metadata
* or task-specific training

we evaluate **zero-shot geographic reasoning** using **prompt-based inference**.

---

## 🎯 Key Contributions

* ✅ **Unified Benchmark** for evaluating VLMs on geolocalization
* 🌍 **World-scale evaluation** across 3 diverse datasets
* 📊 Introduction of **Geographic Error Reasonableness (GER)**
* 🔍 Deep analysis of:

  * urban vs rural performance
  * biome-based difficulty
  * geographic error patterns

---

## 🧠 Problem Setting

Given an input image, the model predicts:

```json
{
  "predictions": ["Country1", "Country2", "Country3", "Country4", "Country5"]
}
```

### Two evaluation modes:

* **Unconstrained** → free-form prediction
* **Label-constrained** → choose from predefined country list

---

## 🏗️ Models Evaluated

We benchmark **9 state-of-the-art VLMs**:

### 🔹 InternVL Family

* InternVL2.5-1B
* InternVL2.5-4B
* InternVL2.5-8B

### 🔹 LLaVA Family

* LLaVA-Mistral-7B
* LLaVA-Vicuna-7B
* LLaMA3-LLaVA-NeXT-8B

### 🔹 Qwen3-VL Family

* Qwen3-VL-2B
* Qwen3-VL-4B ⭐ (best overall)
* Qwen3-VL-8B

---

## 📊 Datasets

| Dataset        | Images | Countries | Source             |
| -------------- | ------ | --------- | ------------------ |
| GeoGuessr-50k  | ~50K   | 124       | Google Street View |
| CityGuessr     | ~68K   | 91        | YouTube            |
| OSV5M (subset) | 50K    | 219       | Mapillary          |

---

## 📈 Evaluation Metrics

### Accuracy

* **Top-1 Accuracy**
* **Top-5 Accuracy**

### Geographic Error Metrics

* 🌍 **Hop Distance** (geographic proximity of errors)
* 🧠 **Geographic Error Reasonableness (GER)**

---

## 🧪 Geographic Error Reasonableness (GER)

![Image](https://i.insider.com/6245242f4829f10018e47aee?format=jpeg\&width=1200)

![Image](https://upload.wikimedia.org/wikipedia/commons/thumb/7/7f/Fuller_projection_with_largest_countries.svg/1280px-Fuller_projection_with_largest_countries.svg.png)

![Image](https://www.researchgate.net/publication/348794634/figure/fig3/AS%3A1023140528398343%401620947119840/Examples-of-Wrong-Classifications-presented-in-Expt-1-Explanation-Present-condition.png)

![Image](https://www.researchgate.net/publication/374938375/figure/fig3/AS%3A11431281203362284%401699287626086/Visual-map-of-countries-region-A-Geographic-distribution-map-based-on-the-total.tif)

GER evaluates whether **wrong predictions are visually reasonable**.

* **GER-Weak** → predicted country appears in ≥1 nearest neighbors
* **GER-Strong** → appears in ≥2 neighbors

👉 Insight:

> Not all errors are equal — some are *visually justified*.

---

## 🔥 Key Findings

### 🥇 Best Model

* **Qwen3-VL-4B** achieves highest performance across datasets

---

### ⚠️ Inverted Scaling

* Larger models (e.g., Qwen3-VL-8B) **do NOT always perform better**

---

### 🏙️ Urban vs Rural Gap

* Models perform significantly better on **urban scenes**
* Up to **34% accuracy gap**

---

### 🌿 Biome Sensitivity

* Performance varies across:

  * Tropical 🌴
  * Arid 🏜️
  * Boreal 🌲
* Dataset distribution heavily affects results

---

### 🌍 Error Behavior

* Strong models:

  * Make **geographically close mistakes**
  * Show **higher GER (reasonable errors)**

* Weak models:

  * Produce **random, visually unjustified errors**

---

## 📉 Example Results (Top-1 Accuracy)

| Model            | GeoGuessr  | CityGuessr | OSV5M  |
| ---------------- | ---------- | ---------- | ------ |
| Qwen3-VL-4B      | **74.79%** | **65.78%** | 45.45% |
| InternVL2.5-8B   | 65.00%     | 57.21%     | 36.30% |
| LLaVA-Mistral-7B | 39.42%     | 30.51%     | 17.67% |

---

## ⚙️ Setup & Usage (Example)

```bash
git clone https://github.com/yourusername/your-repo.git
cd your-repo
pip install -r requirements.txt
```

### Run Inference

```bash
python run_inference.py \
  --model qwen3-vl-4b \
  --image path/to/image.jpg
```

---

## 🔬 Future Work

* 🔧 Fine-tuning VLMs for geolocation
* 🔗 Hybrid models (retrieval + reasoning)
* 🌐 Better geographic grounding
* 📉 Reducing dataset bias

---

## 📚 Citation

```bibtex
@article{anonymous2026vlmgeo,
  title={Where Do Vision-Language Models Fail? World Scale Analysis for Image Country Geolocalization},
  journal={EarthVision 2026},
  year={2026}
}
```

---

## 🙌 Acknowledgements

* GeoGuessr
* Mapillary (OSV5M)
* CityGuessr Dataset
* Open-source VLM community

---

## 📬 Contact

For questions or collaboration:

* Open an issue
* Or reach out via email

---

If you want, I can also:

* tailor this README specifically for your **GitHub repo structure**
* add **badges, demo GIFs, or results plots**
* or generate a **project website (GitHub Pages)** from this README
