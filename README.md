# Identifikasi Jenis Penyakit Tanaman pada Daun Jagung Menggunakan Teknologi Machine Learning

**Identification of corn leaf diseases using machine learning technology**

Proyek ini bertujuan untuk mengembangkan sistem deteksi penyakit tanaman jagung melalui **citra daun** menggunakan **Convolutional Neural Network (CNN)** dan **Model Transfer Learning DenseNet121**. Dengan pendekatan ini, petani dapat mendeteksi penyakit daun jagung secara otomatis dan cepat, meningkatkan efisiensi serta akurasi dalam diagnosis penyakit daun jagung di lapangan.

---

### Deskripsi Proyek

Penelitian ini bertujuan untuk:

1. Mengembangkan metode deteksi penyakit tanaman jagung melalui citra daun.
2. Menguji dan membandingkan akurasi model **CNN** dan **Model Transfer Learning DenseNet121**.
3. Mengimplementasikan model dengan akurasi tertinggi pada sistem deteksi penyakit berbasis citra.

Sistem ini dibangun menggunakan microframework **Flask** dengan bahasa pemrograman **Python** untuk memungkinkan integrasi dan pengujian model deteksi penyakit secara fleksibel.

---

### Pengumpulan Data

Dataset pada penelitian ini diperoleh melalui survei langsung dan observasi di ladang jagung masyarakat, menghasilkan:

- **5368 gambar** dan **10 video** daun jagung.
- Data tersebut diklasifikasikan ke dalam 4 kelas: **Hawar**, **Bercak Daun**, **Karat**, dan **Sehat**.

---

### **Bukti Observasi Langsung**
![Bukti Observasi](https://github.com/sionpardosi/CornLeaf-Disease-Identification-Using-Machine-Learning/blob/main/Requirement/observasi%20-%20Copy.jpg)

---

### Fitur Utama

- **Deteksi Penyakit Daun Jagung**: Mengidentifikasi penyakit seperti _Bercak Daun_ (Leaf Spot), _Karat Jagung_ (Rust), dan _Hawar Daun_ (Blight).
- **Pemrosesan Citra - Roboflow / OpenCV**: Augmentasi gambar untuk memperkaya dataset dan menghindari overfitting, termasuk proses **rescale**, **rotate**, **zoom**, dan **flip**.
- **Model Machine Learning**: Algoritma **CNN** dan **Transfer Learning DenseNet121** diterapkan untuk klasifikasi gambar.
- **Evaluasi Model**: Pengukuran akurasi menggunakan **precision**, **recall**, **F1-score**, dan **confusion matrix** untuk hasil yang optimal.

---

### Teknologi yang Digunakan

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

### Preprocessing dan Augmentasi Gambar dengan Roboflow

Untuk memastikan gambar berada dalam format yang sesuai dan meningkatkan akurasi model, kami menggunakan **Roboflow** untuk melakukan preprocessing dan augmentasi gambar secara otomatis. Berikut adalah teknik yang diterapkan:

#### **Preprocessing**:

1. **Auto-Orient**: Menyesuaikan orientasi gambar agar tidak terbalik.
2. **Static Crop**: Pemotongan gambar untuk memperkecil fokus:
   - **Horizontal Region**: Pemotongan 25%-75% bagian horizontal.
   - **Vertical Region**: Pemotongan 27%-75% bagian vertikal.
3. **Resize**: Mengubah ukuran gambar menjadi **640x640** piksel.

#### **Augmentasi**:

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

---

### Penerapan Canny Edge Detection

Teknik **Canny Edge Detection** digunakan untuk memvisualisasikan fitur penting pada gambar daun jagung yang dapat membantu model fokus pada elemen yang relevan:

![Visualisasi Edge Detection](https://github.com/sionpardosi/CornLeaf-Disease-Identification-Using-Machine-Learning/blob/main/Visualisasi%20Data/Edge%20Detection.png)

---

### Hasil

- **Preprocessing**: Tahapan ini mempersiapkan gambar untuk algoritma CNN dan SVM dengan augmentasi data seperti rescale, rotate, zoom, dan flip.
- **Pelatihan**: Data latih digunakan untuk mengajari model mengenali ciri-ciri setiap jenis penyakit.
- **Pengujian**: Model yang telah dilatih diuji dengan dataset uji untuk mengukur akurasi dan performa deteksi.
- **Evaluasi**: Menilai hasil menggunakan metrik seperti confusion matrix, precision, recall, dan F1-score.

---

### Evaluasi Model

#### **Evaluasi Model pada Data Validasi**:

Model dievaluasi dengan data validasi untuk mengukur *loss* dan *accuracy*. Ini memberikan gambaran tentang kinerja model pada data yang tidak terlihat sebelumnya:

![Visualisasi Validation Accuracy](https://github.com/sionpardosi/CornLeaf-Disease-Identification-Using-Machine-Learning/blob/main/Visualisasi%20Data/Visualisasi%20Validation%20Accuracy.png)

#### **Evaluasi dengan Confusion Matrix**:

Confusion Matrix digunakan untuk mengukur prediksi model vs label sebenarnya, memberikan wawasan lebih mendalam tentang kesalahan klasifikasi.

![Visualisasi Confusion Matrix](https://github.com/sionpardosi/CornLeaf-Disease-Identification-Using-Machine-Learning/blob/main/Visualisasi%20Data/Visualisasi%20Confusion%20Matrix.png)

---

### Performance: Evaluasi Overfitting

1. **Plot Loss**: Menampilkan perbandingan antara **Training Loss** dan **Validation Loss**.
2. **Plot Akurasi**: Menampilkan perbandingan antara **Training Accuracy** dan **Validation Accuracy**.
3. **Interpretasi**: Mengamati apakah ada perbedaan signifikan antara akurasi pelatihan dan validasi yang menunjukkan **overfitting** atau **underfitting**.

![Visualisasi Performance Evaluasi Overfitting Validation Loss](https://github.com/sionpardosi/CornLeaf-Disease-Identification-Using-Machine-Learning/blob/main/Visualisasi%20Data/Visualisasi%20Performance%20Evaluasi%20Overfitting%20Validation%20Loss.png)

![Visualisasi Performance Evaluasi Overfitting Validation Accuracy](https://github.com/sionpardosi/CornLeaf-Disease-Identification-Using-Machine-Learning/blob/main/Visualisasi%20Data/Visualisasi%20Performance%20Evaluasi%20Overfitting%20Validation%20Accuracy.png)

---

### Prediction: Prediksi Gambar Tunggal

Melakukan prediksi terhadap satu gambar baru menggunakan model yang telah dilatih dan visualisasikan hasil prediksi dengan label kelasnya:

![Visualisasi Prediction](https://github.com/sionpardosi/CornLeaf-Disease-Identification-Using-Machine-Learning/blob/main/Visualisasi%20Data/Visualisasi%20Prediction.png)
a
---

### Kesimpulan

Model CNN dan **DenseNet121** telah menunjukkan potensi yang sangat baik dalam mendeteksi penyakit daun jagung dengan tingkat akurasi yang memadai. Penelitian ini membuka jalan untuk pengembangan sistem deteksi otomatis berbasis AI dalam pertanian untuk mempermudah dan mempercepat diagnosis penyakit tanaman jagung.

---

### Kontak

Jika ada pertanyaan lebih lanjut, silakan hubungi saya melalui email di **[email@example.com]**.

---

Terima kasih telah membaca!
