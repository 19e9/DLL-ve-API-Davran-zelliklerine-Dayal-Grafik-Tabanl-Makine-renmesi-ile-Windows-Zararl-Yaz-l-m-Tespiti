# DLL ve API Davranış Özelliklerine Dayalı Grafik Tabanlı Makine Öğrenmesi ile Windows Zararlı Yazılım Tespiti

Bu proje, Windows çalıştırılabilir dosyalarının statik analizinden elde edilen API çağrı dizileri ve DLL ilişkilerine dayalı olarak, zararlı yazılım tespiti gerçekleştirmeyi amaçlamaktadır. Grafik benzeri yapılar üzerinden davranışsal öznitelikler çıkarılmış ve bu veriler farklı makine öğrenmesi algoritmalarıyla sınıflandırılmıştır.

## 🔍 Proje Özeti

- Yöntem: Statik analiz (API + DLL)
- Veri: 601 örnek (.exe dosya)
- Öznitelik türleri: Sayısal (API/DLL sayısı, çeşitlilik, şüpheli içerik, etkileşimli özellikler)
- Algoritmalar:  
  - K-means (kümelenme)
  - KNN  
  - Logistic Regression  
  - Decision Tree  
  - Random Forest  
  - XGBoost  
  - LightGBM

## 📊 Kullanılan Modeller ve Sonuçlar

| Model              | Accuracy | F1-Score | Precision | Recall |
|-------------------|----------|----------|-----------|--------|
| K-means           | -        | -        | -         | -      |
| KNN               | 0.80     | 0.79     | 0.78      | 0.80   |
| Logistic Regression | 0.82   | 0.81     | 0.80      | 0.82   |
| Decision Tree     | 0.78     | 0.77     | 0.75      | 0.79   |
| Random Forest     | 0.84     | 0.84     | 0.85      | 0.82   |
| XGBoost           | 0.85     | 0.85     | 0.86      | 0.83   |
| **LightGBM**      | **0.87** | **0.86** | **0.88**  | **0.85** |

## 🛠️ İçerik

- `Models.ipynb`: Tüm modellerin eğitimi, test edilmesi ve karşılaştırılması
- `data/`: İşlenmiş öznitelik dosyaları (isteğe bağlı)
- `results/`: Model çıktıları, confusion matrix ve grafikler

## 📁 Öznitelikler

Aşağıda bazı örnek öznitelikler listelenmiştir:

- `API_SAYISI`
- `DLL_SAYISI`
- `SUPHELI_VAR_MI`
- `SUPHELI_FONK_LISTE`
- `API_DLL_ORANI`
- `ETKILESIM_DLL_SUPHELI = DLL_SAYISI * SUPHELI_VAR_MI`

## 🧠 Kullanım

> Notebook çalıştırılmadan önce gerekli kütüphaneler yüklenmelidir:

```bash
pip install pandas scikit-learn xgboost lightgbm matplotlib seaborn


##Sunum
https://prezi.com/p/edit/tzzzd-x-_e_p/
