# 🚀 Aritmetica Numerelor Mari: Analiză de Performanță CPU vs. GPU

![Python](https://img.shields.io/badge/Python-3.x-blue?style=flat&logo=python)
![CUDA](https://img.shields.io/badge/Numba-CUDA-green?style=flat&logo=nvidia)

## 📖 Despre Proiect
Acest proiect de licență analizează implementarea și optimizarea operațiilor aritmetice pe **numere mari (Arbitrary-Precision Arithmetic)** folosind arhitecturi paralele. Proiectul compară execuția secvențială pe CPU cu execuția masiv paralelizată pe GPU, utilizând biblioteca **Numba** pentru programare CUDA în Python.

Scopul este evidențierea momentului de "crossover" în care GPU-ul devine mai eficient decât CPU-ul și analiza impactului transferului de date prin PCIe.

## ⚡ Funcționalități Principale

### 🧮 Algoritmi Implementați
1.  **Operații de Bază:** Adunare și Scădere (propagare transport/borrow).
2.  **Înmulțire Clasică (Schoolbook):**
    * Implementare CPU 
    * Implementare GPU folosind operații atomice (`cuda.atomic.add`).
3.  **Algoritmul Karatsuba:** Implementare recursivă pe CPU pentru comparație cu forța brută a GPU-ului.
4.  **Înmulțirea Montgomery:** Aritmetică modulară eficientă, esențială pentru criptografie (RSA).

### 📊 Testare și Validare
* **Testbench Unificat:** Verificarea automată a corectitudinii matematice (Bit-exact).
* **Precizie Variabilă:** Teste de scalabilitate de la 64 biți la 8192+ biți.
* **Analiză Grafică:** Generarea automată a graficelor de performanță (Timp de execuție, Speedup, Analiză Latență vs. Calcul).

## 🛠️ Tehnologii Utilizate
* **Limbaj:** Python
* **GPU Computing:** Numba (CUDA JIT)
* **Structuri de date:** NumPy (Arrays uint64)
* **Mediu de dezvoltare:** Google Colab (Tesla T4 GPU)

## 📈 Concluzii
* Pentru numere mici, latența transferului de date către GPU domină timpul de execuție, CPU-ul fiind mai rapid.
* Pentru numere mari (peste 1024 biți), paralelismul GPU oferă un avantaj semnificativ, în special la operațiile cu complexitate pătratică (Înmulțire).

## 🚀 Rulare
Proiectul este conceput pentru a rula în **Google Colab**:
1.  Deschideți notebook-ul.
2.  Activați acceleratorul hardware: `Runtime -> Change runtime type -> T4 GPU`.
3.  Rulați celulele în ordine (Configurare -> Testbench -> Benchmark-uri).



