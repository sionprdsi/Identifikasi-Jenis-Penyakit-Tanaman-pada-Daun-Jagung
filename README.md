# Identifikasi Jenis Penyakit Tanaman pada Daun Jagung Menggunakan Teknologi Machine Learning

*Identification of corn leaf diseases using machine learning technology* 

Proyek ini bertujuan untuk mengembangkan sistem deteksi penyakit tanaman jagung melalui **citra daun** menggunakan **Convolutional Neural Network (CNN)** dan **Model Transfer Learning DenseNet121**. Dengan pendekatan ini, petani dapat mendeteksi penyakit daun jagung secara otomatis dan cepat, meningkatkan efisiensi serta akurasi dalam diagnosis penyakit daun jagung di lapangan.

---

## Deskripsi Proyek

Penelitian ini bertujuan untuk:

1. Mengembangkan metode deteksi penyakit tanaman jagung melalui citra daun.
2. Menguji dan membandingkan akurasi model **CNN** dan **Model Transfer Learning DenseNet121**.
3. Mengimplementasikan model dengan akurasi tertinggi pada sistem deteksi penyakit berbasis citra.

Sistem ini dibangun menggunakan microframework **Flask** dengan bahasa pemrograman **Python** untuk memungkinkan integrasi dan pengujian model deteksi penyakit secara fleksibel.

---

## Pengumpulan Data

Dataset pada penelitian ini diperoleh melalui survei langsung dan observasi di ladang jagung masyarakat, menghasilkan:

- **5,368 gambar** dan **10 video** daun jagung.  
- Data diklasifikasikan ke dalam 4 kelas:  
  - **Hawar Daun** (Blight)  
  - **Bercak Daun** (Leaf Spot)  
  - **Karat** (Rust)  
  - **Sehat** (Healthy) 
  
---

### **Bukti Observasi Langsung**
![Bukti Observasi](https://github.com/sionpardosi/CornLeaf-Disease-Identification-Using-Machine-Learning/blob/main/Requirement/observasi%20-%20Copy.jpg)

---

## **Fitur Utama**

- **Deteksi Penyakit Daun Jagung**: Mengidentifikasi penyakit seperti _Hawar Daun_, _Bercak Daun_, dan _Karat_.  
- **Pemrosesan Citra**: Melakukan augmentasi data untuk memperkaya dataset dan mencegah overfitting.  
- **Model Machine Learning**:  
  - **Convolutional Neural Network (CNN)**  
  - **Transfer Learning DenseNet121**  
- **Evaluasi Model**:  
  Menggunakan metrik seperti **precision**, **recall**, **F1-score**, dan **confusion matrix**.  
- **Visualisasi Data Performance**: Menyediakan insight dari hasil analisis dataset.  
- **Prediksi**: Melakukan prediksi terhadap gambar Test dengan menggunakan model yang telah dilatih

---

## Teknologi yang Digunakan

#### **Tools:**
<p>
    <img src="https://img.shields.io/badge/Language-Python-blue?logo=python&logoColor=white" />
    <img src="https://img.shields.io/badge/Framework-Flask-green?logo=flask&logoColor=white" />
    <img src="https://img.shields.io/badge/Algorithm-CNN-orange?logo=python&logoColor=white" />
    <img src="https://img.shields.io/badge/Algorithm-SVM-blue?logo=python&logoColor=white" />
    <img src="https://img.shields.io/badge/Library-TensorFlow-red?logo=tensorflow&logoColor=white" />
    <img src="https://img.shields.io/badge/Library-OpenCV-lightblue?logo=opencv&logoColor=white" />
    <img src="https://img.shields.io/badge/Library-Matplotlib-005C4B?logo=matplotlib&logoColor=white" />
    <img src="https://img.shields.io/badge/Tool-Jupyter%20Notebook-FFD43B?logo=python&logoColor=white" />
    <img src="https://img.shields.io/badge/Tool-Google%20Colab-FF6F00?logo=googlecolab&logoColor=white" />
    <img src="https://img.shields.io/badge/Editor-Visual%20Studio%20Code-007ACC?logo=visualstudiocode&logoColor=white" />
</p>

---

# Preprocessing dan Augmentasi Gambar dengan Roboflow & OpenCV

Untuk memastikan gambar berada dalam format yang sesuai dan meningkatkan akurasi model, kami menggunakan **Roboflow** & **OpenCV** untuk melakukan preprocessing dan augmentasi gambar secara otomatis. Berikut adalah teknik yang diterapkan:

### **Preprocessing**:

1. **Auto-Orient**: Menyesuaikan orientasi gambar agar tidak terbalik.
2. **Static Crop**: Pemotongan gambar untuk memperkecil fokus:
   - **Horizontal Region**: Pemotongan 25%-75% bagian horizontal.
   - **Vertical Region**: Pemotongan 27%-75% bagian vertikal.
3. **Resize**: Mengubah ukuran gambar menjadi **640x640** piksel.

### **Augmentasi**:

1. **Outputs per Training Example**: Roboflow menghasilkan **3 output gambar** untuk setiap gambar dalam dataset.
2. **Flip Horizontal**: Gambar dibalik secara horizontal.
3. **Grayscale**: 15% gambar diterapkan filter grayscale.
4. **Hue**: Perubahan hue antara **-25° hingga +25°**.
5. **Saturation**: Saturasi disesuaikan antara **-25% hingga +25%**.
6. **Brightness**: Kecerahan gambar diubah dalam rentang **-25% hingga +25%**.
7. **Exposure**: Exposure disesuaikan antara **-12% hingga +12%**.
8. **Crop**: Gambar dipotong secara acak.
9. **90 Derajat Rotation**: Gambar diputar 90 derajat.

Dengan semua augmentasi ini, dataset menjadi lebih kaya dan model lebih tahan terhadap overfitting.

---

### Visualisasi Data Gambar

Pada tahap ini, kami memvisualisasikan beberapa gambar dari dataset untuk memberikan gambaran mengenai kelas-kelas yang ada:

![Visualisasi Gambar Kelas Dataset](https://github.com/sionpardosi/CornLeaf-Disease-Identification-Using-Machine-Learning/blob/main/Visualisasi%20Data/Visualisasi%20gambar%20kelas%20dataset.png)


### Penerapan Canny Edge Detection

Teknik **Canny Edge Detection** digunakan untuk memvisualisasikan fitur penting pada gambar daun jagung yang dapat membantu model fokus pada elemen yang relevan:

![Visualisasi Edge Detection](https://github.com/sionpardosi/CornLeaf-Disease-Identification-Using-Machine-Learning/blob/main/Visualisasi%20Data/Edge%20Detection.png)

---

# Class Distribution

class_labels = {0: 'Bercak', 1: 'Hawar', 2: 'Karat', 3: 'Sehat'}

![Class Distribution Dataset](https://github.com/sionpardosi/CornLeaf-Disease-Identification-Using-Machine-Learning/blob/main/Visualisasi%20Data/Class%20Distribution%20Dataset.png)

---

# Architecture Model CNN Identifikasi Jenis Penyakit Tanaman pada Daun Jagung

![Aksitektur Model](https://github.com/sionpardosi/CornLeaf-Disease-Identification-Using-Machine-Learning/blob/main/Visualisasi%20Data/Aksitektur%20model.png)

---

# Evaluasi Model

### **Evaluasi Model pada Data Validasi (Visualisasi Validation Accuracy)**:

Model dievaluasi dengan data validasi untuk mengukur *loss* dan *accuracy*. Ini memberikan gambaran tentang kinerja model pada data yang tidak terlihat sebelumnya:

![Visualisasi Validation Accuracy](https://github.com/sionpardosi/CornLeaf-Disease-Identification-Using-Machine-Learning/blob/main/Visualisasi%20Data/Visualisasi%20Validation%20Accuracy.png)

### **Evaluasi dengan Confusion Matrix**:

Confusion Matrix digunakan untuk mengukur prediksi model vs label sebenarnya, memberikan wawasan lebih mendalam tentang kesalahan klasifikasi.
-> Menghitung **Confusion Matrix** untuk menilai distribusi prediksi, Menampilkan **Classification Report** yang mencakup Precision, Recall, dan F1-Score, Menampilkan hasil precision, recall, dan f1-score.

#### **Rumus Masing Masing Parameter**:
![Rumus](https://github.com/sionpardosi/CornLeaf-Disease-Identification-Using-Machine-Learning/blob/main/Visualisasi%20Data/Rumus%20Confusion%20Matrix.png)

#### **Rumus Tabel Confusion Matrix**:
![Rumus](https://github.com/sionpardosi/CornLeaf-Disease-Identification-Using-Machine-Learning/blob/main/Visualisasi%20Data/Rumus%20Tabel%20Confusion%20Matrix.png)

#### **Visualisasi Confusion Matrix**:

![Visualisasi Confusion Matrix](https://github.com/sionpardosi/CornLeaf-Disease-Identification-Using-Machine-Learning/blob/main/Visualisasi%20Data/Visualisasi%20Confusion%20Matrix.png)

#### **Classification Report**:
![Hasilnya](https://github.com/sionpardosi/CornLeaf-Disease-Identification-Using-Machine-Learning/blob/main/Visualisasi%20Data/Classification%20Report.png)

---

# Perfomance

### Performance: Evaluasi Overfitting

1. **Plot Loss**: Menampilkan perbandingan antara **Training Loss** dan **Validation Loss**.
2. **Plot Akurasi**: Menampilkan perbandingan antara **Training Accuracy** dan **Validation Accuracy**.
3. **Interpretasi**: Mengamati apakah ada perbedaan signifikan antara akurasi pelatihan dan validasi yang menunjukkan **overfitting** atau **underfitting**.

![Visualisasi Performance Evaluasi Overfitting Validation Loss](https://github.com/sionpardosi/CornLeaf-Disease-Identification-Using-Machine-Learning/blob/main/Visualisasi%20Data/Visualisasi%20Performance%20Evaluasi%20Overfitting%20Validation%20Loss.png)

![Visualisasi Performance Evaluasi Overfitting Validation Accuracy](https://github.com/sionpardosi/CornLeaf-Disease-Identification-Using-Machine-Learning/blob/main/Visualisasi%20Data/Visualisasi%20Performance%20Evaluasi%20Overfitting%20Validation%20Accuracy.png)

![Visualisasi Performance Accuracy dan loss per Epoch](https://github.com/sionpardosi/CornLeaf-Disease-Identification-Using-Machine-Learning/blob/main/Visualisasi%20Data/Visualisasi%20Performance%20Accuracy%20dan%20loss%20per%20Epoch.png)

---


# **Hasil**

- **Evaluasi**: Menilai hasil menggunakan metrik seperti **confusion matrix**, **precision**, **recall**, dan **F1-score**.  
- **Performance**: Model menunjukkan akurasi tinggi dalam mengidentifikasi penyakit daun jagung.  

---

# Prediction

### Prediction: Predict and Visualize a Single Image
Melakukan prediksi terhadap satu gambar baru menggunakan model yang telah dilatih dan visualisasikan hasil prediksi dengan label kelasnya:

![Visualisasi Prediction](https://github.com/sionpardosi/CornLeaf-Disease-Identification-Using-Machine-Learning/blob/main/Visualisasi%20Data/Visual%20Prediction.png)

---

# Kesimpulan

Model CNN dan **DenseNet121** telah menunjukkan potensi yang sangat baik dalam mendeteksi penyakit daun jagung dengan tingkat akurasi yang memadai. Penelitian ini membuka jalan untuk pengembangan sistem deteksi otomatis berbasis AI dalam pertanian untuk mempermudah dan mempercepat diagnosis penyakit tanaman jagung.

---

# Langkah-Langkah Menjalankan Proyek

## 1. Download atau Clone Repository

- Buka terminal atau command prompt.
- Clone repository dengan perintah:
  ```bash
  git clone https://github.com/sionpardosi/CornLeaf-Disease-Identification-Using-Machine-Learning.git

Atau, unduh proyek dalam format ZIP melalui tombol "Code" di halaman GitHub dan ekstrak file ke direktori yang diinginkan.

## 2. Instalasi Dependensi
- Masuk ke direktori proyek:
  ```bash
  cd CornLeaf-Disease-Identification-Using-Machine-Learning

## 3. Persiapkan Dataset

Unduh dataset yang diperlukan dengan menggunakan Roboflow dari folder : [tautan GitHub](https://github.com/sionpardosi/CornLeaf-Disease-Identification-Using-Machine-Learning/blob/main/Dataset/Dataset.txt).

atau

Anda bisa mengikuti langkah-langkah berikut untuk mengunduh dataset menggunakan Roboflow:

1. Install `roboflow` jika belum terpasang:
   ```bash
   !Install `roboflow` jika belum terpasang dengan menjalankan perintah berikut: `!pip install roboflow`. Setelah itu, unduh dataset yang diperlukan dengan kode berikut: `from roboflow import Roboflow; rf = Roboflow(api_key="sFsgBqWcv09QR1Yku5mC"); project = rf.workspace("sion-pardosi-hbf7k").project("identification-cornleaf-diseases"); version = project.version(1); dataset = version.download("folder")`. Pastikan API key yang digunakan benar dan sesuai, serta periksa struktur folder dataset sesuai dengan dokumentasi proyek.

                













# License

This project is licensed under the [MIT License](LICENSE).