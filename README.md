# air_quality_prediction
ML Project for YAP470
Projem 3 Train + 3 Test = 6 dosyadan oluşmakta.

Train için 3 farklı ülkenin Air Quality verisini kullandım ve bunları farklı dosyalar olarak kaydettim.

Train için; 1.Türkiye verisi için hazırlanmış 1 gün sonrasını tahmin eden bir model, 2.Finlandiya, 3.Avustralya için ve her birinde xgboost, random forest, multi layer perceptron, knn olmak üzere 4 machine learning tekniği kullanıldı.

Test için; aynı şekilde TR, FI ve AU ülkeleri için model tesi yapıldı, her biri için RMSE, MAE, R² Skoru doğrulama yöntemleri kullanıldı.

Not: 5 yıl train için kullanıldı 2 yıl test için

## Klasör Yapısı

- **/data/**: Ham, işlenmiş ve öznitelik mühendisliği yapılmış veri setlerini içerir.
- **/notebooks/**: Projenin çalıştırılabilir Jupyter Notebook dosyalarını içerir.
- **/saved_models/**: Eğitim sonrası kaydedilen tüm modelleri, ölçekleyicileri ve özellik seçicileri (.pkl) içerir.
- **/results/**: Test setlerini, model tahminlerini ve sonuç özet tablolarını (.csv) içerir.
- `requirements.txt`: Projenin çalışması için gerekli Python kütüphaneleri ve versiyonları.

## Notebook'ların Açıklaması ve Nasıl Çalıştırılacağı

Proje, eğitim ve test süreçlerini birbirinden ayıran modüler bir yapıya sahiptir.

### 1. Eğitim Notebook'ları (`tr.ipynb`, `fi.ipynb`, `au.ipynb`)

- **Açıklama:** Bu notebook'ların her biri, ilgili ülkenin verisini kullanarak tam bir eğitim akışı gerçekleştirir. Bu akış şu adımları içerir:
    1.  Ham veriyi okuma ve ön işleme (birim dönüşümü, pivotlama).
    2.  Öznitelik mühendisliği (aykırı değer yönetimi, log dönüşümü, lag/rolling özellikler).
    3.  Tüm modellerin (XGBoost, RF, MLP, KNN) hiperparametre optimizasyonu.
    4.  Final modellerin eğitilmesi ve test için gerekli tüm nesnelerin (`model.pkl`, `scaler.pkl`, `selector.pkl`, `X_test.csv`, `y_test.csv`) diske kaydedilmesi.
- **Nasıl Çalıştırılır:** Bu dosyalar, modelleri yeniden eğitmek için kullanılır. Her biri bağımsız olarak çalıştırılabilir. Örneğin, `tr.ipynb` dosyasını çalıştırmak, Türkiye için tüm modelleri ve test nesnelerini üretecektir.

### 2. Test Notebook'u (`test_all_models.ipynb`)

- **Açıklama:** Bu dosya, projenin **nihai sonuçlarını yeniden üretmek** için kullanılır. **Yeniden eğitim yapmaz.** Sadece, eğitim notebook'ları tarafından daha önce oluşturulmuş ve kaydedilmiş olan `.pkl` ve `.csv` dosyalarını yükler. Yüklenen bu nesnelerle test verileri üzerinde tahmin yapar ve tüm ülkeler/modeller/kirleticiler için performans metriklerini (RMSE, R², MAE) hesaplayarak özet bir tablo oluşturur.
