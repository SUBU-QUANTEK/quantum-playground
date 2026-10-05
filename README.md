# ⚛️ QUANTEK Quantum Playground

Sakarya Uygulamalı Bilimler Üniversitesi **QUANTEK** topluluğu için hazırlanmış, tarayıcı tabanlı interaktif kuantum geliştirme ve deney ortamı.

Bu depo sayesinde bilgisayarınıza Python, sanal ortam (venv) veya Qiskit yüklemenize gerek kalmadan, doğrudan **GitHub Codespaces** üzerinden bulutta kuantum devreleri tasarlayıp çalıştırabilirsiniz.

---

## 🚀 30 Saniyede Nasıl Başlatılır?

1. Sağ üstte bulunan yeşil **`<> Code`** butonuna tıklayın.
2. Açılan menüden **`Codespaces`** sekmesine geçin.
3. **`Create codespace on main`** butonuna basın.
4. Birkaç saniye içinde tam donanımlı Visual Studio Code ortamınız Qiskit ve gerekli tüm kütüphanelerle birlikte tarayıcınızda açılacaktır.

---

## 🛠️ Ortam İçeriği ve Yüklü Kütüphaneler

- **Python 3.10+** & Jupyter Notebook Desteği
- **Qiskit & Qiskit Aer** (Devre simülasyonları için)
- **Matplotlib & Pylatexenc** (Kuantum devrelerini ve histogramları çizdirmek için)

---

## 🧪 Hızlı Başlangıç Örneği (Bell Durumu / Dolaşıklık)

Depo içindeki `ornek_devre.ipynb` dosyasını açabilir veya yeni bir Python dosyası açarak şu kodu doğrudan çalıştırabilirsiniz:

```python
from qiskit import QuantumCircuit
from qiskit_aer import AerSimulator

# 2 kubitlik devre oluştur
qc = QuantumCircuit(2)

# Bell Durumu: H kapısı + CNOT
qc.h(0)
qc.cx(0, 1)
qc.measure_all()

# Simülatörde çalıştır
sim = AerSimulator()
sonuc = sim.run(qc).result()
counts = sonuc.get_counts()

print("Ölçüm Sonuçları:", counts)
