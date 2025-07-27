# air_quality_prediction
ML Project for YAP470
Projem 3 Train + 1 Test = 4 dosyadan oluşmakta.

Train için 3 farklı ülkenin Air Quality verisini kullandım ve bunları farklı dosyalar olarak kaydettim. Test için de 1 ortak dosyam var. Train dosyaları: tr.ipynb, au.ipynb, fi.ipynb Test dosyası: test_all_models.ipynb

Bu projenin temel amacı, OpenAQ API'sinden temin edilen 7 yıllık zaman serisi verilerini kullanarak **Türkiye (TR)**, **Finlandiya (FI)** ve **Avustralya (AU)** için 6 temel hava kirleticisinin (`CO`, `NO2`, `O3`, `PM10`, `PM25`, `SO2`) **1 gün sonraki** seviyelerini tahmin etmektir.

Proje kapsamında, bu tahmin problemini çözmek için iki ana yöntem geliştirilmiş ve karşılaştırılmıştır:
1.  **Yöntem 1:** Kapsamlı öznitelik mühendisliğine dayalı **Klasik Makine Öğrenmesi** modelleri (XGBoost, Random Forest, MLP, KNN).
2.  **Yöntem 2:** Verinin sıralı doğasını ve istatistiksel özetlerini birleştiren **Hibrit Derin Öğrenme** modeli RNN-LSTM.

Not: 5 yıl train için kullanıldı 2 yıl test için



- **Açıklama:** Final_kodlar klasöründe 4 kod dosyam var geri kalan 500e yakın tüm proje çıktıları (eğitilmiş modeller, test verileri, sonuç raporları vb.) google drivedadır. Çünkü github bu kadar fazla dosyayı ve büyük boyutları kabul etmiyor.
- **Nasıl Çalıştırılır:** tr.ipynbi, fi.ipynb ve au.ipynb bu 3 train dosyası ile test_all_models.ipynb test dosyası aynı klasöre konur drivedan indirilenler de aynı dosyaya konur ve test dosyası çalıştırılır.
