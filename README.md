# 🛠️ ML Toolkit

[![Python Version](https://img.shields.io/badge/python-3.8+-blue.svg)](https://www.python.org/)
[![License: MIT](https://img.shields.io/badge/License-MIT-green.svg)](https://opensource.org/licenses/MIT)
[![Status](https://img.shields.io/badge/status-active-brightgreen.svg)]()
[![GitHub Stars](https://img.shields.io/github/stars/BerattCelikk/ml-toolkit?style=social)](https://github.com/BerattCelikk/ml-toolkit)

**[🇹🇷 Türkçe](#-mlkitk---türkçe-) | [🇬🇧 English](#-ml-toolkit---english-)**

---

## 🇹🇷 ML KİT - Türkçe 🇹🇷

`ml-toolkit`, veri bilimi ve makine öğrenmesi süreçlerini hızlandırmak için geliştirilmiş, yeniden kullanılabilir araçlar ve yardımcı fonksiyonlar bütünüdür. Karmaşık veri işleme süreçlerini basitleştirmeyi ve modelleme hatlarını standartlaştırmayı amaçlar.

### 📂 Proje Yapısı

```text
ml-toolkit/
├── preprocessing/       # Veri temizleme ve normalizasyon
│   ├── __init__.py
│   ├── cleaner.py      # Eksik veri işleme, aykırı değer tespiti
│   ├── scaler.py       # Standardizasyon ve normalizasyon
│   └── encoder.py      # Kategorik veri kodlama
├── models/             # Model şablonları ve hazır yapılar
│   ├── __init__.py
│   ├── regression.py   # Regresyon modelleri
│   ├── classification.py  # Sınıflandırma modelleri
│   └── clustering.py   # Kümeleme algoritmaları
├── evaluation/         # Performans metrikleri ve raporlama
│   ├── __init__.py
│   ├── metrics.py      # Özel metrikler
│   ├── validator.py    # Çapraz doğrulama araçları
│   └── reporter.py     # Rapor ve görselleştirme
├── utils/              # Genel amaçlı yardımcı scriptler
│   ├── __init__.py
│   ├── logger.py       # Loglama işlemleri
│   ├── config.py       # Konfigürasyon yönetimi
│   └── helpers.py      # Yardımcı fonksiyonlar
├── tests/              # Birim testleri
│   ├── test_preprocessing.py
│   ├── test_models.py
│   └── test_evaluation.py
├── examples/           # Kullanım örnekleri
│   ├── basic_pipeline.py
│   ├── advanced_example.py
│   └── notebooks/
├── requirements.txt    # Proje bağımlılıkları
├── setup.py           # Kurulum scripti
└── README.md          # Proje belgelendirmesi
```

### ✨ Özellikler

- **Veri Ön İşleme**: Eksik veri işleme, normalizasyon, ve kategorik veri kodlama
- **Model Şablonları**: Önceden yapılandırılmış ML modelleri
- **Değerlendirme Araçları**: Kapsamlı performans metrikleri ve doğrulama
- **Loglama & Raporlama**: Detaylı günlük ve görsel raporlar
- **Modüler Tasarım**: Bağımsız kullanılabilir modüller
- **Açık Kaynak**: MIT Lisansı altında

### 🚀 Kurulum

#### Gereksinimler
- Python 3.8+
- pip veya conda

#### Adım 1: Depoyu Klonlayın
```bash
git clone https://github.com/BerattCelikk/ml-toolkit.git
cd ml-toolkit
```

#### Adım 2: Sanal Ortam Oluşturun (İsteğe Bağlı)
```bash
python -m venv venv
source venv/bin/activate  # Linux/Mac
# veya
venv\Scripts\activate  # Windows
```

#### Adım 3: Bağımlılıkları Yükleyin
```bash
pip install -r requirements.txt
```

#### Adım 4: Paketi Kurun (İsteğe Bağlı)
```bash
pip install -e .
```

### 💡 Hızlı Başlangıç

#### Basit Veri Temizleme
```python
from ml_toolkit.preprocessing import DataCleaner

cleaner = DataCleaner()
clean_data = cleaner.handle_missing_values(df, strategy='mean')
clean_data = cleaner.remove_duplicates(clean_data)
clean_data = cleaner.detect_outliers(clean_data, method='iqr')
```

#### Model Eğitimi ve Değerlendirme
```python
from ml_toolkit.models import RegressionModel
from ml_toolkit.evaluation import ModelEvaluator

# Model oluştur ve eğit
model = RegressionModel(algorithm='random_forest')
model.train(X_train, y_train)

# Modeli değerlendir
evaluator = ModelEvaluator()
metrics = evaluator.evaluate(model, X_test, y_test)
print(metrics)
```

#### Kapsamlı Pipeline
```python
from ml_toolkit.preprocessing import Preprocessor
from ml_toolkit.models import ClassificationModel
from ml_toolkit.evaluation import Reporter

# Veri ön işleme
preprocessor = Preprocessor()
X_processed = preprocessor.fit_transform(X_train)

# Model eğitimi
clf = ClassificationModel(algorithm='gradient_boosting')
clf.train(X_processed, y_train)

# Rapor oluştur
reporter = Reporter()
reporter.generate_report(clf, X_test, y_test, output_path='report.html')
```

### 📚 Belgelendirme

Detaylı belgelendirme [docs/](./docs) klasöründe bulunabilir:
- [Veri Ön İşleme](./docs/preprocessing.md)
- [Modeller](./docs/models.md)
- [Değerlendirme](./docs/evaluation.md)
- [API Referansı](./docs/api_reference.md)

### 🧪 Testler

Testleri çalıştırmak için:
```bash
pytest tests/ -v
```

Kod kapsamını ölçmek için:
```bash
pytest --cov=ml_toolkit tests/
```

### 🔧 Konfigürasyon

`ml_toolkit/utils/config.py` dosyasında proje ayarlarını özelleştirebilirsiniz:
```python
from ml_toolkit.utils import Config

config = Config()
config.load_from_file('config.yaml')
config.set('model', 'random_state', 42)
```

### 📊 Örnek Projeler

Daha fazla örnek için `examples/` klasörünü kontrol edin:
- `basic_pipeline.py` - Basit iş akışı örneği
- `advanced_example.py` - Gelişmiş özelliklerin kullanımı
- `notebooks/` - Jupyter notebook örnekleri

### 🤝 Katkıda Bulunma

Katkılar çok hoş karşılanır! Lütfen aşağıdaki adımları izleyin:

1. Depoyu fork edin
2. Feature branch'i oluşturun (`git checkout -b feature/AmazingFeature`)
3. Değişiklikleri commit edin (`git commit -m 'Add some AmazingFeature'`)
4. Branch'i push edin (`git push origin feature/AmazingFeature`)
5. Pull Request oluşturun

### 📝 Lisans

Bu proje MIT Lisansı altında lisanslanmıştır. Detaylar için [LICENSE](./LICENSE) dosyasına bakın.

### 📧 İletişim

- **Yazar**: Berat Çelik
- **Email**: berat@coddiom.com
- **GitHub**: [@BerattCelikk](https://github.com/BerattCelikk)
- **Web**: [coddiom.com](https://coddiom.com)

### 🌟 Teşekkürler

Bu projeyi faydalı bulduysanız, lütfen bir yıldız ⭐ verin!

---

## 🇬🇧 ML Toolkit - English 🇬🇧

`ml-toolkit` is a comprehensive collection of reusable tools and utility functions designed to accelerate data science and machine learning workflows. It aims to simplify complex data processing pipelines and standardize modeling workflows.

### 📂 Project Structure

```text
ml-toolkit/
├── preprocessing/       # Data cleaning and normalization
│   ├── __init__.py
│   ├── cleaner.py      # Handle missing data, outlier detection
│   ├── scaler.py       # Standardization and normalization
│   └── encoder.py      # Categorical data encoding
├── models/             # Model templates and pre-built structures
│   ├── __init__.py
│   ├── regression.py   # Regression models
│   ├── classification.py  # Classification models
│   └── clustering.py   # Clustering algorithms
├── evaluation/         # Performance metrics and reporting
│   ├── __init__.py
│   ├── metrics.py      # Custom metrics
│   ├── validator.py    # Cross-validation tools
│   └── reporter.py     # Reporting and visualization
├── utils/              # General-purpose utility scripts
│   ├── __init__.py
│   ├── logger.py       # Logging operations
│   ├── config.py       # Configuration management
│   └── helpers.py      # Helper functions
├── tests/              # Unit tests
│   ├── test_preprocessing.py
│   ├── test_models.py
│   └── test_evaluation.py
├── examples/           # Usage examples
│   ├── basic_pipeline.py
│   ├── advanced_example.py
│   └── notebooks/
├── requirements.txt    # Project dependencies
├── setup.py           # Setup script
└── README.md          # Project documentation
```

### ✨ Features

- **Data Preprocessing**: Handle missing data, normalization, and categorical encoding
- **Model Templates**: Pre-configured ML models ready to use
- **Evaluation Tools**: Comprehensive performance metrics and validation
- **Logging & Reporting**: Detailed logs and visual reports
- **Modular Design**: Use independent modules as needed
- **Open Source**: MIT Licensed

### 🚀 Installation

#### Requirements
- Python 3.8+
- pip or conda

#### Step 1: Clone the Repository
```bash
git clone https://github.com/BerattCelikk/ml-toolkit.git
cd ml-toolkit
```

#### Step 2: Create Virtual Environment (Optional)
```bash
python -m venv venv
source venv/bin/activate  # Linux/Mac
# or
venv\Scripts\activate  # Windows
```

#### Step 3: Install Dependencies
```bash
pip install -r requirements.txt
```

#### Step 4: Install Package (Optional)
```bash
pip install -e .
```

### 💡 Quick Start

#### Simple Data Cleaning
```python
from ml_toolkit.preprocessing import DataCleaner

cleaner = DataCleaner()
clean_data = cleaner.handle_missing_values(df, strategy='mean')
clean_data = cleaner.remove_duplicates(clean_data)
clean_data = cleaner.detect_outliers(clean_data, method='iqr')
```

#### Model Training and Evaluation
```python
from ml_toolkit.models import RegressionModel
from ml_toolkit.evaluation import ModelEvaluator

# Create and train model
model = RegressionModel(algorithm='random_forest')
model.train(X_train, y_train)

# Evaluate model
evaluator = ModelEvaluator()
metrics = evaluator.evaluate(model, X_test, y_test)
print(metrics)
```

#### Complete Pipeline
```python
from ml_toolkit.preprocessing import Preprocessor
from ml_toolkit.models import ClassificationModel
from ml_toolkit.evaluation import Reporter

# Data preprocessing
preprocessor = Preprocessor()
X_processed = preprocessor.fit_transform(X_train)

# Model training
clf = ClassificationModel(algorithm='gradient_boosting')
clf.train(X_processed, y_train)

# Generate report
reporter = Reporter()
reporter.generate_report(clf, X_test, y_test, output_path='report.html')
```

### 📚 Documentation

Detailed documentation is available in the [docs/](./docs) directory:
- [Data Preprocessing](./docs/preprocessing.md)
- [Models](./docs/models.md)
- [Evaluation](./docs/evaluation.md)
- [API Reference](./docs/api_reference.md)

### 🧪 Testing

Run tests with:
```bash
pytest tests/ -v
```

Measure code coverage:
```bash
pytest --cov=ml_toolkit tests/
```

### 🔧 Configuration

Customize project settings in `ml_toolkit/utils/config.py`:
```python
from ml_toolkit.utils import Config

config = Config()
config.load_from_file('config.yaml')
config.set('model', 'random_state', 42)
```

### 📊 Example Projects

Check the `examples/` directory for more examples:
- `basic_pipeline.py` - Simple workflow example
- `advanced_example.py` - Advanced features usage
- `notebooks/` - Jupyter notebook examples

### 🤝 Contributing

Contributions are welcome! Please follow these steps:

1. Fork the repository
2. Create a feature branch (`git checkout -b feature/AmazingFeature`)
3. Commit your changes (`git commit -m 'Add some AmazingFeature'`)
4. Push to the branch (`git push origin feature/AmazingFeature`)
5. Create a Pull Request

---
### 🌟 Acknowledgments

If you find this project useful, please consider giving it a star ⭐!
---
