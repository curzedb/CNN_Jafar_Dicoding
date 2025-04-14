# CNN-Based Rock-Paper-Scissors Detection
**Proyek Klasifikasi untuk membedakan antara jari yang menunjukkan Gunting, Batu, atau Kertas Menggunakan Algoritma CNN**

📌 **Dibuat untuk**: Submission Proyek Akhir kelas Dicoding X IDCamp - Machine Learning Beginer

-------------------------------------------------------------------


## 📝 Deskripsi Proyek
Proyek ini mengimplementasikan **Convolutional Neural Network (CNN)** untuk mengklasifikasikan gambar tangan menjadi 3 kategori:
- Gunting
- Batu
- Kertas

Dataset yang digunakan: <a href="https://github.com/dicodingacademy/assets/releases/download/release/rockpaperscissors.zip">rockpaperscissor.zip</a> (2.000+ Gambar).

-----------------------------------------------------------------------

## 🛠️ Tools
- **Bahasa Pemrograman**: Python 3
- **Framework**: TensorFlow
- **Libraries**: NumPy, Matplotlib, os, zipfile
- **Platform**: Google Colab

-----------------------------------------------------------------------
## 📊 Struktur Dataset  
```
dataset/  
  ├── rps-cv-images/  
  │   ├── scissors/
  |   ├── rock/  
  │   └── paper/    
  |  
  └── ─── scissors/ 
      ├── rock/  
      └── paper/  
```

---------------------------------------------------------------------
## 🧠 Arsitektur Model CNN  
```python
model = tf.keras.models.Sequential([
    tf.keras.layers.Conv2D(32, (3,3), activation='relu', input_shape=(150, 150, 3)),
    tf.keras.layers.MaxPooling2D(2, 2),
    tf.keras.layers.Conv2D(64, (3,3), activation='relu'),
    tf.keras.layers.MaxPooling2D(2,2),
    tf.keras.layers.Conv2D(128, (3,3), activation='relu'),
    tf.keras.layers.MaxPooling2D(2,2),
    tf.keras.layers.Conv2D(128, (3,3), activation='relu'),
    tf.keras.layers.MaxPooling2D(2,2),
    tf.keras.layers.Flatten(),
    tf.keras.layers.Dense(512, activation='relu'),
    tf.keras.layers.Dense(3, activation='softmax')
    ])

model.compile(loss = 'categorical_crossentropy',
              optimizer=tf.optimizers.Adam(),
              metrics=['accuracy'])
model.summary()
```
**Hyperparameter**:  
- Optimizer: `Adam`  
- Loss: `Categorycal_Crossentropy`  
- Epochs: `16`  
- Batch Size: `32`

-----------------------------------------------------------------------
## 📈 Hasil Evaluasi  
| Metric      | Validation |
|-------------|------------|
| Accuracy    | 98.3%      |
| Loss        | 0.74       |

-----------------------------------------------------------------------
## Implementasi
![image](https://github.com/user-attachments/assets/771a3787-02f9-40d8-842b-93e3eb9c9d1b)


