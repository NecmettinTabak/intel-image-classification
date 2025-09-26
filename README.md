# 🧠 Intel Image Classification with Deep Learning (Keras + CNN)

Bu proje, Akbank Derin Öğrenme Bootcamp kapsamında gerçekleştirilmiştir.  
Amaç, **Intel Image Classification** veri seti kullanarak **Convolutional Neural Network (CNN)** ile görüntü sınıflandırma modelinin geliştirilmesidir.

---

## 📂 Veri Seti

Intel Image Classification veri seti, **Kaggle** üzerinden sağlanmıştır.  
Veri kümesi, 6 farklı sınıftan (bina, orman, buzulluk, dağ, deniz, sokak) oluşan 25.000+ eğitim ve 7.000+ test görüntüsünden oluşmaktadır.

- 📁 `seg_train/`: Eğitim ve doğrulama verileri  
- 📁 `seg_test/`: Test verileri  

🔗 [Veri Seti - Kaggle](https://www.kaggle.com/datasets/puneet6060/intel-image-classification)

---

## 🧪 Veri Hazırlama ve Artırma

Overfitting'i engellemek ve modelin genelleme kabiliyetini artırmak amacıyla veri artırma (Data Augmentation) uygulanmıştır.

Kullanılan teknikler:

- `Rescale`
- `rotation_range`
- `width_shift_range`
- `height_shift_range`
- `shear_range`
- `zoom_range`
- `horizontal_flip`
- `brightness_range`
- `validation_split`

---

## 🏗️ Model Mimarisi

Model, **Keras** kullanılarak oluşturulan klasik bir CNN mimarisine sahiptir.

- 3 adet `Conv2D + MaxPooling2D` bloğu
- `Flatten` katmanı
- `Dense` katman (ReLU)
- `Dropout (0.5)`  
- `Output layer` (6 sınıflı softmax)

**Optimizer:** Adam (learning_rate=0.0005)  
**Loss Function:** Categorical Crossentropy

---

## 🧠 Model Eğitimi

Model, 10 epoch boyunca eğitim ve doğrulama verileriyle eğitilmiştir.  
Eğitim ve doğrulama metrikleri aşağıdaki gibi grafiklerle görselleştirilmiştir:

- 📈 Accuracy (Doğruluk)  
- 📉 Loss (Kayıp)  

Ayrıca, `model.save("intel_model.h5")` komutu ile model `.h5` formatında kaydedilmiştir.

---

## 📊 Performans Değerlendirmesi

### ✅ Confusion Matrix

Tüm sınıflar için karışıklık matrisi görselleştirilmiştir.  
Her sınıf için modelin ne kadar doğru tahmin yaptığı gözlemlenmiştir.

### 📄 Classification Report

| Metric | Precision | Recall | F1-score |
|--------|-----------|--------|----------|
| Ortalama | 0.79 | 0.79 | 0.79 |

En iyi başarı `forest`, `street` ve `glacier` sınıflarında elde edilmiştir.

---

## 📁 Dosyalar

| Dosya Adı | Açıklama |
|-----------|----------|
| `akbank-notebook.ipynb` | Tüm eğitim, görselleştirme ve test işlemlerini içeren Jupyter Notebook |
| `intel_model.h5` | Eğitilmiş model dosyası (Kaggle notebook içinde kaydedilmiştir) |

---

## 🔗 Kaggle Notebook Linki

Notebook'u çalıştırmak ve model dosyasını görüntülemek için:

👉 [Kaggle Notebook - akbank-notebook.ipynb](https://www.kaggle.com/code/necmettintabak/akbank-notebook)

Notebook çıktıları görünür durumdadır ve model sağ taraftaki “Output” klasöründen indirilebilir.

---

## 👤 Katılımcı

**Necmettin Tabak**  
E-posta: necmettintabak@gmail.com  
GitHub: [NecmettinTabak](https://github.com/NecmettinTabak)

---

