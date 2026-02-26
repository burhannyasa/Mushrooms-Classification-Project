# 🍄 Mantar Sınıflandırması – Denetimli Makine Öğrenmesi

## 📌 Proje Özeti
Bu proje, UCI Mantar veri setini kullanarak mantarları **yenilebilir veya zehirli** olarak sınıflandırmak için denetimli makine öğrenmesi modelleri geliştirmektedir.  

Amaç, birden fazla sınıflandırma algoritmasını karşılaştırmak, kategorik özellikleri analiz etmek ve yüksek performanslı bir tahmin modeli oluşturmaktır.

---

## 📊 Veri Seti
- Kaynak: UCI Mantar Veri Seti  
- Gözlem Sayısı: 8.124  
- Özellikler: 23 kategorik değişken  
- Hedef Değişken: `class` (yenilebilir / zehirli)

Tüm değişkenler mantarın fiziksel özelliklerini (şapka şekli, yüzey, renk, koku, lamel özellikleri, sap özellikleri, spor rengi, popülasyon ve habitat) tanımlar.  

Eksik veri bulunmamaktadır, sadece özel kodlamalar vardı ve bunlar veri ön işleme aşamasında ele alındı.

---

## 🔎 Keşifsel Veri Analizi
- Kategorik değişkenlerin dağılım analizi  
- Cramer's V korelasyon analizi  
- Yüksek tahmin gücüne sahip özelliklerin belirlenmesi (örn. koku, spor-rengi, lamel-rengi)

Bazı özelliklerin hedef değişken ile güçlü korelasyonu, modellerin yüksek başarı göstermesini açıklamaktadır.

---

## 🤖 Kullanılan Modeller
5 katlı çapraz doğrulama ile karşılaştırılan algoritmalar:  

- Lojistik Regresyon  
- K-En Yakın Komşu  
- Destek Vektör Makineleri  
- Karar Ağacı  
- Random Forest  
- Extra Trees  
- Bagging Sınıflandırıcı  

---

## ⚙️ Model Optimizasyonu
- GridSearchCV ile hiperparametre optimizasyonu  
- RFECV ve Sıralı Özellik Seçimi ile özellik seçimi  
- ROC eğrisi ve AUC analizi  

---

## 📈 Sonuçlar
- Lojistik Regresyon: ~%97 test doğruluk  
- ROC-AUC Skoru: 0,97  
- Random Forest: Neredeyse mükemmel sınıflandırma performansı (F1 ≈ 0,99)

Random Forest, en stabil ve dengeli model olarak öne çıktı.

---

## 🛠 Kullanılan Teknolojiler
- Python  
- Pandas  
- NumPy  
- Scikit-learn  
- Matplotlib  
- Seaborn  

---

## 📌 Sonuç
Veri setindeki sınıflar arasındaki güçlü ayrışabilirlik nedeniyle, topluluk (ensemble) yöntemleri neredeyse mükemmel sonuçlar verdi. Dayanıklılığı ve kararlılığı nedeniyle Random Forest, final modeli olarak seçildi.
