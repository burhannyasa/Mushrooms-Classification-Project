# 🍄 Mantar Sınıflandırması – Denetimli Makine Öğrenmesi

## 📌 Proje Özeti
Bu proje, UCI Mantar veri setini kullanarak mantarları **yenilebilir veya zehirli** olarak sınıflandırmak için denetimli makine öğrenmesi modelleri geliştirmektedir. Amaç, birden fazla sınıflandırma algoritmasını karşılaştırmak, kategorik özellikleri analiz etmek ve yüksek performanslı bir tahmin modeli oluşturmaktır.

---

## 📊 Veri Seti
- **Kaynak:** UCI Mantar Veri Seti (8.124 gözlem, 23 kategorik değişken).
- **Hedef Değişken:** `class` (yenilebilir / zehirli).
- Tüm değişkenler mantarın fiziksel özelliklerini (şapka şekli, yüzey, renk, koku vb.) tanımlar. Eksik veri bulunmamaktadır, veri ön işleme aşamasında özel kodlamalar (encoding) ele alınmıştır.

---

## 🔎 Keşifsel Veri Analizi (EDA)
Kategorik değişkenlerin dağılımı ve **Cramer's V korelasyon analizi** ile değişkenler arası ilişkiler incelenmiştir.

![Cramer's V Correlation](outputs/cramers_v_correlation.png)
*Özellikle koku, spor-rengi ve lamel-rengi gibi özelliklerin hedef değişken ile güçlü korelasyonu, modellerin yüksek başarısını açıklamaktadır.*

---

## ⚙️ Model Optimizasyonu ve Özellik Seçimi
İnternet kaynaklarında nadir görülen **Recursive Feature Elimination (RFECV)** metoduyla optimal değişken sayısı belirlenmiş ve **Sequential Feature Selector** ile en iyi 3 değişken seçilmiştir.

![Feature Selection Process](outputs/feature_selection_process.png)

---

## 🤖 Kullanılan Modeller ve Performans
5 katlı çapraz doğrulama ile karşılaştırılan algoritmalar: Lojistik Regresyon, KNN, SVM, Karar Ağacı, Random Forest, Extra Trees ve Bagging Sınıflandırıcı.

![Confusion Matrix](outputs/random_forest_confusion_matrix.png)

### 📈 Sonuçlar
- **Random Forest:** %99.3 doğruluk oranı ve mükemmele yakın F1 skoru ile en stabil model olarak seçilmiştir.
- **Lojistik Regresyon:** ~%97 test doğruluğu ve 0.97 ROC-AUC skoru elde edilmiştir.

---

## 🗺️ Boyut İndirgeme ve Görselleştirme
22 boyutlu veri seti **PCA** ile 2 boyuta indirgenmiş ve **K-Means** algoritması ile kümelenme yapısı analiz edilmiştir.

![PCA Clusters](outputs/pca_clusters_visualization.png)

---

## 🛠 Kullanılan Teknolojiler
- **Diller:** Python (Pandas, NumPy, Scikit-learn).
- **Görselleştirme:** Matplotlib, Seaborn.
- **Yöntemler:** GridSearchCV (Hiperparametre optimizasyonu), RFECV, PCA.

---

## 📌 Sonuç
Veri setindeki sınıflar arasındaki güçlü ayrışabilirlik sayesinde topluluk (ensemble) yöntemleri mükemmel sonuçlar vermiştir. Dayanıklılığı ve kararlılığı nedeniyle Random Forest, final modeli olarak belirlenmiştir. Detaylı teknik analizler için `reports/` klasöründeki PDF raporu inceleyebilirsiniz.
