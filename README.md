# 🍽️ Food Recognition & Calorie Estimation

This project uses deep learning (EfficientNet-B0) to recognize food items from images and estimate their calorie content, helping users make informed dietary choices.

---

## 📂 Dataset

We use the **Food-101 dataset**, which contains 101 food categories with 1,000 images each (750 training, 250 testing).

📆 **Dataset Link:**
[https://www.vision.ee.ethz.ch/datasets\_extra/food-101/](https://www.vision.ee.ethz.ch/datasets_extra/food-101/)
(Provided by ETH Zurich)

📁 **Structure:**

```
pec/
├── images/
│   └── <class_name>/image.jpg
├── meta/
│   ├── classes.txt
│   ├── train.txt
│   ├── test.txt
```

---

## 🧠 Model

* **Backbone:** EfficientNet-B0 (pretrained on ImageNet)
* **Input Size:** 224x224 RGB images
* **Framework:** PyTorch + Torchvision

---

## 🔢 Calorie Estimation

Each predicted food item is mapped to an average calorie value (per serving). Example:

| Food Class | Calories |
| ---------- | -------- |
| Pizza      | 285 kcal |
| Ice Cream  | 207 kcal |
| Sushi      | 200 kcal |
| Lasagna    | 375 kcal |

(*Values are approximate and based on common nutrition databases.*)

---

## 📦 Setup Instructions

1. Clone this repo and install dependencies:

```bash
pip install torch torchvision
```

2. Download and extract the dataset into the `pec/` folder.

3. Run the training script:

```bash
python train.py  # or use notebook.ipynb
```

4. Use the `predict_with_calories()` function to test with your own image.

---

## 📊 Output

```python
label, calories = predict_with_calories("example.jpg")
print(f"Predicted: {label}, Estimated Calories: {calories} kcal")
```

---

## ✅ Features

* Recognizes 101 food items
* Fast, GPU-optimized model
* Calorie estimation included
* Easily extendable to food tracking or logging apps

---

## 🙏 Credits

* **Dataset:** [Food-101](https://www.vision.ee.ethz.ch/datasets_extra/food-101/) by Lukas Bossard, Matthieu Guillaumin, and Luc Van Gool, ETH Zurich

  > *Publication: Bossard et al., "Food-101 – Mining Discriminative Components with Random Forests" (ECCV 2014)*

* **Model Architecture:** EfficientNet by Google AI

  > *Paper: Tan and Le, "EfficientNet: Rethinking Model Scaling for Convolutional Neural Networks" (ICML 2019)*

* **Frameworks:** PyTorch, Torchvision

---

## 📌 License

This project is for academic and research use only. Commercial use of the dataset must follow the [Food-101 dataset license](https://data.vision.ee.ethz.ch/cvl/food-101/).

---
