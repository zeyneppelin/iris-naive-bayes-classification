# iris-naive-bayes-classification
Iris species classification using Gaussian Naive Bayes with preprocessing, evaluation, and model comparison (SVC &amp; Logistic Regression).

# Iris Naive Bayes Classification

## Proje Özeti
Bu projede Iris veri seti kullanılarak çiçek türleri (Species) sınıflandırılmıştır. 
Çalışma, veriyi inceleme ve görselleştirme adımlarından başlayıp; veri temizleme, kategorik dönüşüm, ölçekleme, modelleme ve performans değerlendirme adımlarını içeren uçtan uca bir sınıflandırma akışı sunar.

Ayrıca ana model olan Gaussian Naive Bayes sonuçları; karşılaştırma amaçlı SVC (RBF Kernel) ve Logistic Regression modelleriyle birlikte değerlendirilmiştir.

Veri Seti
- Dosya: 11-iris.csv
- Hedef değişken (tahmin edilen): Species
- Özellikler (kullanılan kolonlar): Sepal/Petal ölçümleri
- Not: Id kolonu bilgi taşımadığı için veri setinden çıkarılmıştır.

## Yapılan Adımlar

1) Veri Yükleme ve İlk İnceleme
- CSV dosyası okunmuştur.
- İlk/son satırlar, kolon tipleri ve veri boyutu incelenmiştir.
- Eksik değer kontrolü yapılmıştır (isnull().sum()).

2) Keşifsel Veri Analizi (EDA)
Verinin sınıflar açısından ayrışıp ayrışmadığını görmek için görselleştirmeler yapılmıştır:
- pairplot ile değişkenler arası ilişkiler
- Sepal ve Petal ölçümleri için sınıfa göre (hue=Species) scatter plot görselleri

 3) Veri Temizleme
- Id kolonu model için anlamlı bilgi taşımadığı için kaldırılmıştır.

4) Kategorik Değişkenin Sayısallaştırılması
- Species kolonu LabelEncoder ile sayısal forma dönüştürülmüştür.
  (Amaç: Makine öğrenmesi algoritmalarının hedef değişkeni sayısal olarak işleyebilmesi.)

5) Feature/Target Ayrımı
- X: Species dışındaki ölçüm kolonları
- y: Species

 6) Train/Test Ayrımı
- Veri seti %75 eğitim, %25 test olacak şekilde ayrılmıştır (test_size=0.25).
- Amaç: Model performansını daha önce görülmemiş test verisi üzerinde ölçmek.

7) Ölçekleme (StandardScaler)
- Özellikler StandardScaler ile ölçeklenmiştir:
  - Train: fit_transform
  - Test: transform
- Amaç: Ölçek farklılıklarının özellikle mesafe/optimizasyon tabanlı modellerde etkisini azaltmak.

8) Modelleme: Gaussian Naive Bayes
- GaussianNB ile model eğitilmiş ve test verisi üzerinde tahmin alınmıştır.

9) Performans Değerlendirme
Gaussian Naive Bayes modeli için:
- Accuracy
- Classification Report
- Confusion Matrix

10) Karşılaştırma Modelleri
Karşılaştırma amacıyla iki ek model kurulmuştur:
- SVC (kernel="rbf")
- Logistic Regression

Üç model için confusion matrix sonuçları ısı haritası (heatmap) şeklinde yan yana görselleştirilmiştir:
- Naive Bayes
- SVC
- Logistic Regression


Kullanılan Teknolojiler
- Python
- pandas, numpy
- matplotlib, seaborn
- scikit-learn

   pip install pandas numpy matplotlib seaborn scikit-learn

