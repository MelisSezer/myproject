# air_quality_prediction
ML Project for YAP470
Projem 3 Train + 3 Test = 6 dosyadan oluşmakta.

Train için 3 farklı ülkenin Air Quality verisini kullandım ve bunları farklı dosyalar olarak kaydettim.

Train için; 1.Türkiye verisi için hazırlanmış 1 gün sonrasını tahmin eden bir model, 2.Finlandiya, 3.Avustralya için ve her birinde xgboost, random forest, multi layer perceptron, knn olmak üzere 4 machine learning tekniği kullanıldı.

Test için; aynı şekilde TR, FI ve AU ülkeleri için model tesi yapıldı, her biri için RMSE, MAE, R² Skoru doğrulama yöntemleri kullanıldı.

Not: 5 yıl train için kullanıldı 2 yıl test için
