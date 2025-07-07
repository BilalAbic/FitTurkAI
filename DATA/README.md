# 📊 FitTürkAI Eğitim Verileri

<div align="center">

![Dataset](https://img.shields.io/badge/Dataset-Turkish%20Health%20QA-blue.svg)
![Format](https://img.shields.io/badge/Format-JSON-green.svg)
![Language](https://img.shields.io/badge/Language-Turkish-red.svg)
![Size](https://img.shields.io/badge/Size-Expandable-orange.svg)

*Türkçe Sağlık ve Beslenme Alanında Özelleştirilmiş Eğitim Veri Seti*

</div>

---

## 📋 İçindekiler

- [🎯 Veri Seti Hakkında](#-veri-seti-hakkında)
- [📁 Dosya Yapısı](#-dosya-yapısı)
- [📝 Veri Formatı](#-veri-formatı)
- [🔍 Veri Kalitesi](#-veri-kalitesi)
- [🚀 Kullanım](#-kullanım)
- [📈 İstatistikler](#-i̇statistikler)
- [🔬 Metodoloji](#-metodoloji)
- [⚠️ Önemli Notlar](#️-önemli-notlar)

---

## 🎯 Veri Seti Hakkında

Bu veri seti, **FitTürkAI** yapay zeka asistanının Türkçe sağlık, beslenme ve yaşam tarzı konularında uzmanlaşması için özel olarak hazırlanmıştır. Veri seti, Türkçe doğal dil işleme (NLP) kapasitelerini optimize etmek ve TEKNOFEST Türkçe NLP yarışması için geliştirilmiştir.

### 🌟 Veri Seti Özellikleri

- **🇹🇷 %100 Türkçe**: Türkçe dilbilgisi ve kültürel kontekst dikkate alınarak hazırlandı
- **🏥 Sağlık Odaklı**: Beslenme, egzersiz, uyku ve genel sağlık konularında uzmanlaşmış
- **💬 Konuşma Dostu**: Doğal dil etkileşimi için optimize edilmiş soru-cevap formatı
- **📚 Bilimsel Temelli**: Güvenilir sağlık kaynaklarından derlenmiş
- **🔄 Genişletilebilir**: Sürekli güncellenen ve gelişen yapı

---

## 📁 Dosya Yapısı

```
DATA/
├── 📊 train.json                     # Ana eğitim verisi
├── 📋 README.md                      # Bu dokümantasyon
└── 📈 [gelecekte eklenecek dosyalar] # Validation/test setleri
```

### 📝 Ana Dosya Açıklamaları

| Dosya | Boyut | Açıklama | Kullanım Amacı |
|-------|-------|----------|----------------|
| `train.json` | ~MB | Soru-cevap çiftleri | Model fine-tuning |
| `README.md` | ~KB | Dokümantasyon | Veri seti rehberi |

---

## 📝 Veri Formatı

### 🔤 JSON Şeması

Dosya yapısı: JSON array içinde objeler
```json
[
  {
    "soru": "string - Kullanıcının Türkçe sorusu", 
    "cevap": "string - FitTürkAI'nin profesyonel cevabı"
  },
  {
    "soru": "string - Kullanıcının Türkçe sorusu",
    "cevap": "string - FitTürkAI'nin profesyonel cevabı"
  }
  // ... diğer objeler
]
```

### 💡 Örnek Veri Kayıtları

```json
[
  {
    "soru": "Günde kaç gram protein almalıyım?",
    "cevap": "Protein ihtiyacınız yaşınıza, cinsiyetinize, aktivite düzeyinize ve hedeflerinize bağlıdır. Genel olarak: • Sedanter yetişkinler: 0.8g/kg vücut ağırlığı • Aktif bireyler: 1.2-1.7g/kg • Sporcular: 1.6-2.2g/kg Örneğin 70kg bir birey için günlük 56-154g protein önerilir. Kesin miktar için beslenme uzmanına danışmanız önerilir."
  },
  {
    "soru": "Kilo vermek için hangi egzersizler etkili?",
    "cevap": "Kilo verme için en etkili egzersiz kombinasyonu: **Kardiyovasküler Egzersizler:** • Koşu, yürüyüş, bisiklet (hafta 150dk) • HIIT antrenmanları (hafta 2-3 kez) **Direnç Antrenmanı:** • Ağırlık çalışması (hafta 2-3 kez) • Kas kütlesini korur, metabolizmayı hızlandırır **Günlük Aktivite:** • Merdiven çıkma, yürüyüş • 10.000 adım hedefi Unutmayın: Egzersiz + sağlıklı beslenme = sürdürülebilir kilo kaybı"
  }
]
```

### 🏗️ Veri Yapısı Detayları

- **Encoding**: UTF-8 (Türkçe karakter desteği)
- **Format**: JSON Array - Obje dizisi formatında
- **Boyut**: Değişken (50-500 kelime arası cevaplar)
- **Dil**: %100 Türkçe

---

## 🔍 Veri Kalitesi

### ✅ Kalite Kontrol Süreçleri

1. **🔤 Dil Kontrolü**
   - Türkçe dilbilgisi kontrolü
   - Yazım denetimi
   - Anlaşılırlık testi

2. **🏥 İçerik Doğrulama**
   - Tıbbi doğruluk kontrolü
   - Kaynak referans kontrolü
   - Güvenlik değerlendirmesi

3. **🤖 Teknik Validasyon**
   - JSON format kontrolü
   - Unicode uyumluluğu
   - Encoding doğrulaması

### 📊 Veri Kalitesi Metrikleri

| Metrik | Değer | Açıklama |
|--------|-------|----------|
| **Dil Doğruluğu** | >95% | Manuel Türkçe kontrolü |
| **Tıbbi Doğruluk** | >90% | Uzman değerlendirmesi |
| **Format Uyumluluğu** | %100 | Otomatik validasyon |
| **Encoding Başarısı** | %100 | UTF-8 uyumluluğu |

---

## 🚀 Kullanım

### ✅ Mevcut Kullanım

Bu veriler şu anda `modeltrain.py` tarafından model eğitimi için kullanılmaktadır.

### 🔧 Veri Yükleme

```python
import json

# JSON array formatında veri okuma
def load_training_data(file_path):
    with open(file_path, 'r', encoding='utf-8') as f:
        data = json.load(f)
    return data

# Kullanım
training_data = load_training_data('DATA/train.json')
print(f"Toplam veri sayısı: {len(training_data)}")
```

### 🎯 Model Eğitimi İçin Preprocessing

```python
def format_for_training(data_item):
    """FitTürkAI formatına dönüştürme"""
    question = data_item["soru"]
    answer = data_item["cevap"]
    
    # Cosmos Turkish 8B için format
    formatted = f"Soru: {question}\nCevap: {answer}<|endoftext|>"
    return formatted

# Batch processing
formatted_data = [format_for_training(item) for item in training_data]
```

### 🚀 Gelecek Kullanım (RAG Sistemi)

Gelecekte RAG sistemi geliştirildiğinde, bu veriler bilgi tabanı oluşturmak için de kullanılacaktır.

### 🔍 Veri Analizi

```python
import matplotlib.pyplot as plt
from collections import Counter

def analyze_dataset(data):
    """Veri seti analizi"""
    
    # Soru uzunlukları
    question_lengths = [len(item["soru"].split()) for item in data]
    answer_lengths = [len(item["cevap"].split()) for item in data]
    
    # İstatistikler
    stats = {
        "total_samples": len(data),
        "avg_question_length": sum(question_lengths) / len(question_lengths),
        "avg_answer_length": sum(answer_lengths) / len(answer_lengths),
        "max_question_length": max(question_lengths),
        "max_answer_length": max(answer_lengths)
    }
    
    return stats
```

---

## 📈 İstatistikler

### 📊 Veri Seti Boyutu
- **Toplam Kayıt**: **24.7K** Türkçe soru-cevap çifti
- **Veri Boyutu**: 10 MB (ham veri)
- **Ortalama Soru Uzunluğu**: ~15-25 kelime
- **Ortalama Cevap Uzunluğu**: ~75-150 kelime
- **Hugging Face Dataset**: [FitTurkAI-Health-DATA](https://huggingface.co/datasets/AIYildiz/FitTurkAI-Health-DATA)

### 🏷️ Konu Dağılımı
- **🍎 Beslenme**: %40
- **🏃‍♂️ Egzersiz**: %30  
- **😴 Uyku/Dinlenme**: %15
- **🧘‍♀️ Stres/Mental Sağlık**: %10
- **💧 Hidrasyon**: %5

### 📝 Soru Tipleri
- **Bilgi Alma**: %45 ("Nedir?", "Nasıl?")
- **Öneri İsteme**: %35 ("Ne önerirsiniz?")
- **Hesaplama**: %15 ("Kaç kalori?")
- **Karşılaştırma**: %5 ("Hangisi daha iyi?")

---

## 🔬 Metodoloji

### 📚 Veri Toplama Süreçleri

1. **🔍 Kaynak Toplama**
   - Türkçe sağlık web siteleri
   - Beslenme rehberleri
   - Fitness makaleleri
   - Uzman görüşleri

2. **✏️ Veri Oluşturma**
   - Manuel soru-cevap yazımı
   - Uzman değerlendirmesi
   - Dil editörü kontrolü
   - Çoklu doğrulama

3. **🎯 Özelleştirme**
   - Türkçe kültürel bağlam
   - Yerel beslenme alışkanlıkları
   - Türk mutfağı entegrasyonu

### 🔄 Sürekli Geliştirme

- **Kullanıcı Geri Bildirimi**: Canlı sistemden gelen veriler
- **Uzman İncelemesi**: Aylık kalite kontrolleri  
- **Güncelleme Döngüsü**: 3 ayda bir major update
- **A/B Testing**: Farklı cevap formatları deneme

---

## ⚠️ Önemli Notlar

### 🚨 Kritik Uyarılar

- **🏥 Tıbbi Sorumluluk**: Bu veriler eğitim amaçlıdır, tıbbi tavsiye değildir
- **🔒 Telif Hakları**: Orijinal içerik, referanslar belirtilmiştir
- **🇹🇷 Dil Sınırları**: Sadece Türkçe için optimize edilmiştir
- **📅 Güncellik**: Sürekli güncellenen dinamik veri seti

### 🛠️ Teknik Gereksinimler

```python
# Gerekli kütüphaneler
import json          # Veri yükleme
import pandas as pd  # Analiz (opsiyonel)
import torch         # Model eğitimi
from transformers import AutoTokenizer  # Tokenization
```

### 📞 Destek ve İletişim

- **🐛 Hata Raporlama**: GitHub Issues
- **💡 Öneriler**: Discussions
- **📧 İletişim**: aiyildiz@gmail.com

---

<div align="center">

**📊 Türkiye'nin İlk Yerli Sağlık AI Veri Seti 📊**

*TEKNOFEST 2024 - Türkçe Doğal Dil İşleme Yarışması*

![Made in Turkey](https://img.shields.io/badge/Made%20in-Turkey-red.svg)

</div> 
