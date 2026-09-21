# 🏥 Tabip Sentetik (Ön Sürüm / Preview)

> Türkiye'nin ilk ve en kapsamlı açık kaynak Türkçe sentetik hasta veri setidir. Yapay zeka modelleri, büyük dil modelleri (LLM) ve sağlık yazılımları için optimize edilmiştir.

[![Lisans: CC BY 4.0](https://img.shields.io/badge/License-CC%20BY%204.0-lightgrey.svg)](https://creativecommons.org/licenses/by/4.0/)
[![Python](https://img.shields.io/badge/Python-3.8%2B-blue.svg)](https://www.python.org/)
[![Format: Parquet](https://img.shields.io/badge/Format-Parquet-orange.svg)](https://parquet.apache.org/)
[![Hugging Face Dataset](https://img.shields.io/badge/Hugging%20Face-Datasets-yellow.svg)](https://huggingface.co/)
[![Durum: Ön Sürüm](https://img.shields.io/badge/Status-Alpha%20%2F%20Preview-orange.svg)](#-gelecek-planları--yol-haritası)

---

## ⚠️ Proje Durumu ve Ön Sürüm Bildirimi

**TABİP Sentetik** şu anda bir **ön sürüm (Alpha / Preview)** aşamasındadır. 
* Bu sürüm; geliştiricilere, araştırmacılara ve yapay zeka meraklılarına erken erişim sağlamak ve geri bildirim toplamak amacıyla yayınlanmıştır.
* Proje aktif olarak geliştirilmekte olup; veri setleri sürekli güncellenecek, hatalar giderilecek, yeni veriler eklenecek ve kapsamı kademeli olarak genişletilecektir.

---

## 📌 Proje Hakkında
**Tabip Sentetik**, KVKK ve hasta gizliliği endişesi olmaksızın gerçekçi klinik senaryolar üzerinde algoritma geliştirmeyi mümkün kılan bağımsız bir açık veri projesidir. Sistem genelinde **2.000.000 benzersiz hasta** etrafında kümelenmiş, toplam **198.4+ Milyon satırlık** ilişkisel bir tıbbi veri ekosistemi barındırır.

* **%100 Gizlilik:** Gerçek kişi verisi içermez, tamamen sentetik mimariyle üretilmiştir.
* **Yerli Klinik Dil:** Türkiye sağlık sistemi dinamiklerine, ICD-10 tanı kodlarına ve ulusal aşı takvimine tam uyumludur.

---

## 📁 Veri Envanteri ve Hacimler

| Dosya Adı | Satır Sayısı | Açıklama |
| :--- | :--- | :--- |
| `kisiler.parquet` | 2.000.000 | Temel demografik ve kimlik profilleri |
| `hastaliklar.parquet` | 35.200.512 | ICD-10 tanılı hastalık ve süreç geçmişi |
| `laboratuvar.parquet` | 24.996.599 | Biyokimyasal tahlil ve ölçüm sonuçları |
| `ilac-atama.parquet` | 35.200.512 | Tanılarla eşleşmiş reçete ve ilaç atamaları |
| `tibbi-islemler.parquet` | 69.478.989 | Klinik müdahaleler ve operasyon prosedürleri |
| `alerjiler.parquet` | 2.291.436 | Madde duyarlılıkları ve reaksiyon geçmişi |
| `cocukluk-asileri.parquet` | 29.302.179 | Ulusal bağışıklama ve aşı takvimi kayıtları |

**Toplam Hacim:** 7 Tablo · ~198.4 Milyon Satır · 16.48 GB

---

## 🚀 Verilere Erişim ve Hızlı Başlangıç

Parquet formatındaki devasa veri setlerimizi **Hugging Face Datasets** üzerinden Python ile tek satırda projelerinize dahil edebilirsiniz:

```python
from datasets import load_dataset

# Hugging Face üzerinden veri setini yükleme
# (kullanici_adinizi kendi Hugging Face kullanıcı adınızla değiştirmelisiniz)
dataset = load_dataset("kullanici_adin/tabip-sentetik")

```

Alternatif olarak, Pandas kütüphanesiyle doğrudan URL üzerinden de okuma yapabilirsiniz:

```python
import pandas as pd

# Örnek: Demografik verileri çekme
df_kisiler = pd.read_parquet("[https://huggingface.co/datasets/kullanici_adin/tabip-sentetik/resolve/main/kisiler.parquet](https://huggingface.co/datasets/kullanici_adin/tabip-sentetik/resolve/main/kisiler.parquet)")
print(df_kisiler.head())

```

---

## 🗺️ Gelecek Planları ve Yol Haritası (Roadmap)

* [ ] **Veri Zenginleştirme:** Yeni klinik branşlar ve nadir hastalık senaryolarının eklenmesi.
* [ ] **Veri Düzenleme ve Genişletme:** Topluluk geri bildirimleriyle kolon ve ilişki optimizasyonları.
* [ ] **Ölçek Artırımı:** Hasta popülasyon hacminin ilerleyen sürümlerde artırılması.
* [ ] **Araçlar ve Betikler:** Python için yardımcı analiz ve işleme betiklerinin eklenmesi.

---

## 🎯 Kullanım Alanları

* **Yapay Zeka & LLM Eğitimi:** Doğal dil işleme ve medikal RAG sistemleri için Türkçe klinik kaynak.
* **Sağlık Bilişimi:** HBYS ve medikal yazılımlar için yük testleri ve demo ortamları.
* **Akademik Araştırmalar:** Biyoistatistik, epidemiyoloji ve veri madenciliği çalışmaları.

---

## 🤝 Katkıda Bulunma

Geliştirmelere destek olmak, hata bildirmek veya önerilerde bulunmak için **Issues** açabilir ya da **Pull Request** gönderebilirsiniz.

* E-posta: tipatlasiprojesi@gmail.com
* Web: [tabip.rf.gd](https://tabip.rf.gd?utm_source=gemini)

---

## 📄 Lisans

Bu proje **CC BY 4.0** lisansı altında korunmaktadır.
