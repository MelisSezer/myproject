# air_quality_prediction
ML Project for YAP470
Projem 3 Train + 1 Test = 4 dosyadan oluşmakta.

Train için 3 farklı ülkenin Air Quality verisini kullandım ve bunları farklı dosyalar olarak kaydettim.

Train için; 1.Türkiye verisi için hazırlanmış 1 gün sonrasını tahmin eden bir model, 2.Finlandiya, 3.Avustralya için ve her birinde xgboost, random forest, multi layer perceptron, knn olmak üzere 4 machine learning tekniği kullanıldı.

Test için; aynı şekilde TR, FI ve AU ülkeleri için model tesi yapıldı, her biri için RMSE, MAE, R² Skoru doğrulama yöntemleri kullanıldı, bunlar birlikte 1 dosyada yapıldı.

Not: 5 yıl train için kullanıldı 2 yıl test için

Train dosyaları: tr.ipynb, au.ipynb, fi.ipynb
Test dosyası: test_all_models.ipynb

- **Açıklama:** Bu notebook'ların her biri, ilgili ülkenin verisini kullanarak tam bir eğitim akışı gerçekleştirir. Bu akış şu adımları içerir:
    1.  Ham veriyi okuma ve ön işleme (birim dönüşümü, pivotlama).
    2.  Öznitelik mühendisliği (aykırı değer yönetimi, log dönüşümü, lag/rolling özellikler).
    3.  Tüm modellerin (XGBoost, RF, MLP, KNN) hiperparametre optimizasyonu.
    4.  Final modellerin eğitilmesi ve test için gerekli tüm nesnelerin (`model.pkl`, `scaler.pkl`, `selector.pkl`, `X_test.csv`, `y_test.csv`) diske kaydedilmesi.
- **Nasıl Çalıştırılır:** tr.ipynbi, fi.ipynb ve au.ipynb bu 3 train dosyası ile 3 tane engineered veri seti aynı dosya yoluna koyulduktan sonra modellerin sadece 4. blok yani training blokları çalıştırılır sonrasında test_all_models dosyası çalıştırılır sonuçlar otomatik olarak indiriliyor.
- Not: Hocam normlade çok daha erken bitmişti projem fakat githuba yükleme kısmı çok uğraştırdı ve tam olmadı çünkü çok fazla model .pkl dosyam var ve bazılarının boyutu bütük github kabul etmedi ama train uzun sürmüyor engineered dosyaları yükledim zaten total 5-10dk arasında bitiyor. pkl dosyalarınıda yükledim fakat karışık ve küçültülmüş şekilde notebook dosyasının içinde
