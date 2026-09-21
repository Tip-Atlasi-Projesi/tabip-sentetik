# 🏥 Tabip Sentetik (Ön Sürüm / Preview)

> Türkiye'nin ilk ve en kapsamlı açık kaynak Türkçe sentetik hasta veri setidir. Yapay zeka modelleri, büyük dil modelleri (LLM) ve sağlık yazılımları için optimize edilmiştir.

[![Lisans: CC BY 4.0](https://img.shields.io/badge/License-CC%20BY%204.0-lightgrey.svg)](https://creativecommons.org/licenses/by/4.0/)
[![Python](https://img.shields.io/badge/Python-3.8%2B-blue.svg)](https://www.python.org/)
[![Format: Parquet](https://img.shields.io/badge/Format-Parquet-orange.svg)](https://parquet.apache.org/)
[![Durum: Ön Sürüm](https://img.shields.io/badge/Status-Alpha%20%2F%20Preview-yellow.svg)](#-gelecek-planları--yol-haritası)

---

## ⚠️ Proje Durumu ve Ön Sürüm Bildirimi

**TABİP Sentetik** şu anda bir **ön sürüm (Alpha / Preview)** aşamasındadır. 
* Bu sürüm; geliştiricilere, araştırmacılara ve yapay zeka meraklılarına erken erişim sağlamak ve geri bildirim toplamak amacıyla yayınlanmıştır.
* Proje aktif olarak geliştirilmekte olup; veri setleri sürekli güncellenecek, hatalar giderilecek, yeni veriler eklenecek ve kapsamı kademeli olarak genişletilecektir.
* Üretim (production) ortamlarında kullanmadan önce veri yapılarındaki güncellemeleri takip etmeniz önerilir.

---

## 📌 Proje Hakkında
**Tabip Sentetik**, KVKK ve hasta gizliliği endişesi olmaksızın gerçekçi klinik senaryolar üzerinde algoritma geliştirmeyi mümkün kılan bağımsız bir açık veri projesidir. Sistem genelinde **2.000.000 benzersiz hasta** etrafında kümelenmiş, toplam **198.4+ Milyon satırlık** ilişkisel bir tıbbi veri ekosistemi barındırır.

* **%100 Gizlilik:** Gerçek kişi verisi içermez, tamamen sentetik mimariyle üretilmiştir.
* **Yerli Klinik Dil:** Türkiye sağlık sistemi dinamiklerine, ICD-10 tanı kodlarına ve ulusal aşı takvimine tam uyumludur.

---

## 📁 Veri Envanteri ve Hacimler

| Dosya Adı | Satır Sayısı | Boyut | Açıklama |
| :--- | :--- | :--- | :--- |
| `kisiler.parquet` | 2.000.000 | 93.46 MB | Temel demografik ve kimlik profilleri |
| `hastaliklar.parquet` | 35.200.512 | 5.70 GB | ICD-10 tanılı hastalık ve süreç geçmişi |
| `laboratuvar.parquet` | 24.996.599 | 2.48 GB | Biyokimyasal tahlil ve ölçüm sonuçları |
| `ilac-atama.parquet` | 35.200.512 | 1.73 GB | Tanılarla eşleşmiş reçete ve ilaç atamaları |
| `tibbi-islemler.parquet` | 69.478.989 | 4.13 GB | Klinik müdahaleler ve operasyon prosedürleri |
| `alerjiler.parquet` | 2.291.436 | 264.76 MB | Madde duyarlılıkları ve reaksiyon geçmişi |
| `cocukluk-asileri.parquet` | 29.302.179 | 2.09 GB | Ulusal bağışıklama ve aşı takvimi kayıtları |

**Toplam Hacim:** 7 Tablo · ~198.4 Milyon Satır · 16.48 GB

---

## 🚀 Hızlı Başlangıç (Python ile Okuma)

Parquet formatı sayesinde devasa veri setlerini bilgisayarınızda saniyeler içinde Pandas ile sorgulayabilirsiniz:

```python
import pandas as pd

# Demografik verileri yükleme
df_kisiler = pd.read_parquet('data/kisiler.parquet')
print(f"Toplam Hasta Sayısı: {len(df_kisiler):,}")

# Hastalıklar tablosunu inceleme
df_hastalik = pd.read_parquet('data/hastaliklar.parquet')
print(df_hastalik.head())

```

---

## 🗺️ Gelecek Planları ve Yol Haritası (Roadmap)

Projenin ön sürüm aşamasından kararlı sürüme geçiş sürecinde planlanan geliştirmeler:

* [ ] **Veri Zenginleştirme:** Yeni klinik branşlar, nadir hastalık senaryoları ve detaylı klinik metadataların eklenmesi.
* [ ] **Veri Düzenleme ve Genişletme:** Topluluktan gelen geri bildirimler doğrultusunda kolon yapıları, verilerin kapsamı ve ilişkisel tutarlılıkların optimize edilmesi.
* [ ] **Ölçek Artırımı:** Hasta popülasyon hacminin ve parametre çeşitliliğinin ilerleyen sürümlerde daha üst seviyelere çıkarılması.
* [ ] **Dokümantasyon ve Araçlar:** Python için yardımcı veri işleme betikleri ve zenginleştirilmiş Jupyter Notebook örnekleri.

---

## 🎯 Kullanım Alanları

* **Yapay Zeka & LLM Eğitimi:** Doğal dil işleme ve medikal RAG sistemleri için Türkçe klinik metin kaynağı.
* **Sağlık Bilişimi:** HBYS ve medikal yazılımlar için yük testleri ve simülasyon ortamları.
* **Akademik Araştırmalar:** Biyoistatistik, epidemiyoloji ve veri madenciliği çalışmaları.

---

## 🤝 Katkıda Bulunma

Bu ön sürüm aşamasında projemize katkıda bulunmak, eksik veya hatalı gördüğünüz noktaları bildirmek için **Issues** açabilir ya da **Pull Request** gönderebilirsiniz. Topluluk odaklı bu gelişime destekleriniz bizim için çok değerlidir!

* E-posta: tipatlasiprojesi@gmail.com
* Web: [tabip.rf.gd](https://tabip.rf.gd?utm_source=gemini)

---

## 📄 Lisans

Bu proje **CC BY 4.0** lisansı altında korunmaktadır. Detaylı bilgi için `LICENSE` dosyasına göz atabilirsiniz.
