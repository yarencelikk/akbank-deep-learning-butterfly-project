# Akbank Derin Öğrenme Bootcamp - Kelebek Türü Sınıflandırma Projesi

Bu proje, Akbank Derin Öğrenme Bootcamp'i kapsamında, evrişimli sinir ağları (CNN) kullanılarak kelebek ve güve türlerini sınıflandırmak amacıyla geliştirilmiştir.Proje, bir derin öğrenme modelinin veri ön işlemeden model değerlendirme ve yorumlanabilirliğe kadar tüm adımlarını içermektedir.

## 📖 Projenin Amacı

Projenin temel amacı, verilen bir kelebek veya güve görselinden yola çıkarak türünü yüksek doğrulukla tahmin eden bir CNN modeli oluşturmaktır. Bu süreçte aşağıdaki hedeflere odaklanılmıştır:
* Veri temizleme, zenginleştirme (Data Augmentation) ve hazırlama tekniklerini uygulamak.
* Sıfırdan bir CNN mimarisi tasarlamak ve eğitmek.
* Model performansını artırmak için hiperparametre optimizasyonu denemeleri yapmak.
* Elde edilen modelin performansını çeşitli metriklerle (Accuracy, Classification Report, Confusion Matrix) değerlendirmek.
* Grad-CAM gibi yorumlanabilirlik teknikleri ile modelin karar mekanizmasını görselleştirmek.

## 🦋 Veri Seti

Projede, Kaggle üzerinde bulunan "Butterfly Images (40 species)" veri seti kullanılmıştır.
* **İçerik:** Veri seti, 40 farklı kelebek ve güve türüne ait görseller içermektedir.
* **Dağılım:** Veri, modelin eğitimi, doğrulanması ve test edilmesi için `train`, `valid` ve `test` olmak üzere üç alt kümeye ayrılmıştır.

## 🛠️ Kullanılan Yöntemler

Proje boyunca aşağıdaki derin öğrenme teknikleri ve kütüphaneleri kullanılmıştır:

* **Veri Ön İşleme ve Çoğaltma (Data Augmentation):**
    * Modelin genelleme yeteneğini artırmak ve ezberlemesini önlemek için eğitim verilerine `ImageDataGenerator` ile rastgele döndürme, yakınlaştırma, kaydırma gibi dönüşümler uygulanmıştır.

* **Model Mimarisi (CNN):**
    * Model, TensorFlow/Keras kütüphanesi kullanılarak sıfırdan oluşturulmuştur.
    * Mimari, `Conv2D`, `MaxPooling2D` katmanlarından oluşan bloklar üzerine kurulmuştur.
    * Ezberlemeyi azaltmak için `Dropout` katmanı ve sınıflandırma için `Dense` katmanları kullanılmıştır.

* **Hiperparametre Optimizasyonu:**
    * Model performansını iyileştirmek için iki farklı mimari (`v1` ve `v2`) denenmiştir.`v2` modelinde katman sayısı artırılmış ve öğrenme oranı (learning rate) düşürülerek daha iyi sonuçlar hedeflenmiştir.

* **Model Değerlendirme ve Yorumlanabilirlik:**
    * Modelin performansı; Accuracy/Loss grafikleri, Sınıflandırma Raporu ve Karmaşıklık Matrisi ile detaylı olarak incelenmiştir.
    * Modelin tahmin yaparken görüntünün hangi bölgelerine odaklandığını anlamak için **Grad-CAM** tekniği kullanılarak ısı haritaları oluşturulmuştur.

## 📊 Elde Edilen Sonuçlar

Yapılan hiperparametre optimizasyonu sonucunda, daha derin olan `model_v2`'nin temel modele göre daha yüksek bir başarım sergilediği gözlemlenmiştir.

* **En İyi Model:** `model_v2` (Daha Derin CNN Mimarisi)
* **Test Seti Başarısı (Accuracy):** **[92.20%]**

Grad-CAM analizi, modelin sınıflandırma yaparken büyük ölçüde kelebeklerin kanat desenleri gibi ayırt edici özelliklere odaklandığını göstermiştir.

## 🚀 Kaggle Notebook

Projenin tüm kodlarını, analizleri ve çıktılarını içeren Kaggle notebook'una aşağıdaki linkten ulaşabilirsiniz:

* **[https://www.kaggle.com/code/yarencelikkk/akbank-bootcamp-kelebeksiniflandirmaprojesi]**
* **[https://www.kaggle.com/datasets/gpiosenka/butterfly-images40-species]**
