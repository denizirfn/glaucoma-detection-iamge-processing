# image_processing_for_glokom
# Glokom Görüntü İşleme Projesi

Bu proje, glokom hastalığının tespiti amacıyla fundus (retina) görüntüleri üzerinde çeşitli görüntü işleme tekniklerinin uygulanmasını kapsamaktadır. Proje Python programlama dili ve OpenCV kütüphanesi kullanılarak geliştirilmiştir.

## 🔍 Proje Amacı

Glokom, genellikle göz içi basıncının artmasına bağlı olarak optik sinirlerin zarar görmesiyle ortaya çıkan bir göz hastalığıdır. Bu projede, fundus görüntüleri üzerinde görüntü işleme teknikleri kullanılarak glokoma dair belirtilerin tespiti hedeflenmiştir.

## 📌 Aşamalar ve Kullanılan Teknikler

### 1. Ön İşleme

- **Gri Tonlama (Grayscale):**  
  Renkli (BGR) fundus görüntüleri gri tonlamaya dönüştürülerek yalnızca parlaklık bilgisi korunmuştur. Bu dönüşüm, aydınlatma sorunlarıyla daha etkili başa çıkmayı sağlar.

- **Morfolojik Açılma:**  
  Gri tonlamalı görüntüler üzerinde `morphological opening` uygulanarak arka plan tahmini yapılmış, bu arka plan orijinal görüntüden çıkarılmış ve görüntüye DC seviyesi eklenmiştir.

### 2. Damar Yapılarının Belirginleştirilmesi ve Çıkarılması

- **CLAHE (Kontrast Sınırlı Adaptif Histogram Eşitleme):**  
  Görüntü kontrastını artırarak düşük kontrastlı alanlarda daha net sonuçlar elde edilmiştir.

- **Morfolojik Gradient:**  
  Damar kenarlarını belirginleştirmek için uygulanmıştır.

- **Eşikleme (Thresholding):**  
  Damar maskesi oluşturulmuştur; damar bölgeleri beyaz olarak işaretlenmiştir.

- **Inpainting (Yeniden Boyama):**  
  Damarların bulunduğu bölgeler, çevresindeki piksellerin tahmini kullanılarak görüntüden kaldırılmıştır.

### 3. Optik Disk ve Cup Tespiti

- **Multi-thresholding:**  
  Optik disk ve cup bölgeleri farklı eşik değerleri kullanılarak segment edilmiştir. Bu işlem, glokom gibi göz hastalıklarının tanısında oldukça önemlidir.

## 📸 Örnek Görseller

| Görsel Açıklama | Görsel |
|----------------|--------|
| Şekil 1: Glokom hastalığına ait örnek fundus görseli | ![Şekil1](./images/şekil1.jpg) |
| Şekil 2: Illumination Correction uygulanmış görsel | ![Şekil2](./images/şekil2.jpg) |
| Şekil 3: Kan damarları çıkarılmış görsel | ![Şekil3](./images/şekil3.jpg) |
| Şekil 4: Optik disk segmentasyonu | ![Şekil4](./images/şekil4.jpg) |
| Şekil 5: Optik cup segmentasyonu | ![Şekil5](./images/şekil5.jpg) |


## 🛠️ Kullanılan Teknolojiler

- Python
- OpenCV
- NumPy
- Matplotlib

## 👨‍💻 Geliştiriciler

- **Yeliz İrfan**  
  Konya Teknik Üniversitesi  
  Bilgisayar Mühendisliği Bitirme Projesi Ara dönem çalışması(2025)

---

