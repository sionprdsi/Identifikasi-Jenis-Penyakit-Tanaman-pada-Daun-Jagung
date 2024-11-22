# Identifikasi Jenis Penyakit Tanaman pada Daun Jagung Menggunakan Teknologi Machine Learning - On Progress

*Identification of corn leaf diseases using machine learning technology* - On Progress.



# <summary><strong>Hi there :wave: , I'm Goo!</strong></summary>
Lifelong Learner, currently working as budagh kompeni.
<p align="left"> <img src="https://komarev.com/ghpvc/?username=goonesmile&label=Profile%20views&color=0e75b6&style=flat" alt="isrealodejobi" />
</p>

### <summary><strong>Tools:</strong></summary>
<p>
    <img src="https://img.shields.io/badge/Text%20Editor-Visual%20Studio%20Code-blue?&logo=visual%20studio%20code&logoColor=blue" />
</p>

### <summary><strong>Yosh!</strong></summary>
<p>
    - :keyboard: I’m currently learning Data Analytics. </br>
    - :speech_balloon: Ask me about anything.</br>
    - :mailbox: How to reach me: <a href="mailto:youremail@gmail.com">Email me!</a>  </br>
    - :cloud: Pronouns: She/Her. </br>
    - :game_die: Drawing and writing are part of me. </br>
<p>
 
### <summary><strong>Let's connect!</strong></summary>
<a href="https://twitter.com/yours">
  <img align="left" alt="Goo's Twitter" width="20px" src="https://simpleicons.now.sh/twitter/495f7e" />
</a>
<a href="https://www.instagram.com/yours/">
  <img align="left" alt="Goo's Instagram" width="20px" src="https://simpleicons.now.sh/instagram/495f7e" />
</a>
<a href="https://yours.com/">
  <img align="left" alt="Goo's Blog" width="20px" src="https://simpleicons.now.sh/blogger/495f7e" />
</a>








Proyek ini bertujuan untuk mengembangkan sistem deteksi penyakit tanaman jagung melalui **citra daun** menggunakan **Convolutional Neural Network (CNN)** dan **Support Vector Machine (SVM)**. Dengan pendekatan ini, petani dapat mendeteksi penyakit daun jagung secara otomatis dan cepat, yang akan meningkatkan efisiensi serta akurasi dalam diagnosis penyakit daun jagung di lapangan.

### Deskripsi Proyek
Penelitian ini bertujuan untuk:
1. Mengembangkan metode deteksi penyakit tanaman jagung melalui citra daun.
2. Menguji dan membandingkan akurasi model **CNN** dan **SVM**.
3. Mengimplementasikan model dengan akurasi tertinggi pada sistem deteksi penyakit berbasis citra.

Sistem ini dibangun menggunakan microframework **Flask** dengan bahasa pemrograman **Python** untuk memungkinkan integrasi dan pengujian model deteksi penyakit secara fleksibel.

### Pengumpulan Data
Dataset pada penelitian ini diperoleh melalui survei langsung dan observasi di ladang jagung masyarakat, menghasilkan:
- **500 gambar** dan **10 video** daun jagung.
- Data tersebut diklasifikasikan ke dalam 4 kelas: **Hawar**, **bercak daun**, **Karat**, dan **Sehat**.
  
### **Bukti Observasi Langsung**
![Bukti Observasi](https://github.com/sionpardosi/CornLeaf-Disease-Identification-Using-Machine-Learning/blob/main/Requirement/observasi%20-%20Copy.jpg)

### Fitur Utama

- **Deteksi Penyakit Daun Jagung**: Mengidentifikasi penyakit seperti _Bercak Daun_ (Leaf Spot), _Karat Jagung_ (Rust), dan _Hawar Daun_ (Blight).
- **Pemrosesan Citra**: Augmentasi gambar untuk memperkaya dataset dan menghindari overfitting, termasuk proses **rescale**, **rotate**, **zoom**, dan **flip**.
- **Model Machine Learning**: Algoritma **CNN** dan **SVM** diterapkan untuk klasifikasi gambar.
- **Evaluasi Model**: Pengukuran akurasi menggunakan **precision**, **recall**, **F1-score**, dan **confusion matrix** untuk hasil yang optimal.

### Teknologi yang Digunakan

- **Confusion matrix** digunakan untuk mengukur akurasi model, dan pengujian dilakukan menggunakan **Jupyter Notebook** / **Google Colab** dan **Visual Studio Code** sebagai teks editor utama.
- **Python**: Bahasa pemrograman utama untuk pengembangan model.
- **TensorFlow**: Framework untuk membangun model CNN.
- **OpenCV**: Digunakan untuk pemrosesan citra dan augmentasi gambar.
- **Matplotlib**: Untuk visualisasi hasil dan evaluasi model.

---

### Hasil (Coming Soon)

- **Preprocessing**: Tahapan ini mengolah citra untuk mempermudah algoritma CNN dan SVM dalam proses training, dengan menggunakan augmentasi data seperti rescale, rotate, zoom, dan flip.
- **Pelatihan**: Data latih digunakan untuk mengajari model mengenali ciri-ciri dari setiap jenis penyakit melalui proses iteratif.
- **Pengujian**: Model yang telah dilatih diuji dengan dataset uji untuk mengukur akurasi dan performanya dalam mendeteksi penyakit.
- **Evaluasi** -> Coming Soon
  
---

Dengan adanya sistem ini, diharapkan proses diagnosis penyakit tanaman jagung dapat dilakukan lebih cepat dan efisien.
