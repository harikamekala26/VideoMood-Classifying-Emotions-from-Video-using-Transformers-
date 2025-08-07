# 🎥 VideoMood-Classifying-Emotions-from-Video-using-Transformers-

This repository implements **emotion classification from video** using a fine-tuned [TimeSformer](https://huggingface.co/facebook/timesformer-base-finetuned-k400) model on the [RAVDESS](https://zenodo.org/record/1188976) dataset. It extracts frames from each video, processes them through a transformer-based architecture, and classifies into one of 8 emotional categories.

---

## 🔍 Overview

- 🎯 **Task:** Video-based emotion recognition  
- 🧠 **Model:** `facebook/timesformer-base-finetuned-k400`  
- 📁 **Dataset:** RAVDESS (Ryerson Audio-Visual Database of Emotional Speech and Song)  
- ⚙️ **Frameworks:** PyTorch, Hugging Face Transformers, Datasets, Decord  
- 📊 **Performance:** Achieves ~91.67% accuracy on test set

---

## 📦 Dataset Setup (RAVDESS)

1. Download the RAVDESS dataset from [Zenodo](https://zenodo.org/record/1188976).  
2. Extract all `.mp4` video files under a folder named `ravdess_video/` structured like this:

```
ravdess_video/
├── Actor_01/
│   ├── 03-01-01-01-01-01-01.mp4
│   └── ...
├── Actor_02/
│   └── ...
...
```

---

## 🧠 Model Architecture

- **Base model:** [`facebook/timesformer-base-finetuned-k400`](https://huggingface.co/facebook/timesformer-base-finetuned-k400)  
- **Classification Head:** Modified for 8 emotion classes  
- **Loss Function:** Cross-entropy  
- **Optimizer:** AdamW  
- **Training Strategy:** Hugging Face Trainer API

---

## 🧩 Emotion Classes

Emotion labels are derived from the RAVDESS filename metadata (positions 3 and 4). The model predicts one of the following:

| Label ID | Emotion    |
|----------|------------|
| 0        | Angry      |
| 1        | Calm       |
| 2        | Disgust    |
| 3        | Fearful    |
| 4        | Happy      |
| 5        | Neutral    |
| 6        | Sad        |
| 7        | Surprised  |

---

## 📊 Results

- ✅ **Test Accuracy:** ~91.67%  
- 📉 **Loss Curve:** Tracked with Hugging Face Trainer (optional to log via TensorBoard or WandB)

---

## 🚀 Future Work

- [ ] Add **multimodal fusion**: audio + text + video  
- [ ] Implement **real-time emotion detection** with webcam input  
- [ ] Quantize and export model for **mobile or edge deployment**

---

## 💬 Acknowledgements

- [Facebook TimeSformer](https://github.com/facebookresearch/TimeSformer)  
- [Hugging Face Transformers](https://huggingface.co/docs/transformers/index)  
- [RAVDESS Dataset](https://zenodo.org/record/1188976)  
- [Decord](https://github.com/dmlc/decord) for efficient frame extraction  
- [VideoMAE](https://huggingface.co/docs/transformers/model_doc/videomae)

---

