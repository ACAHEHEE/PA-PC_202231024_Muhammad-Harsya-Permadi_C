# UAS Pengolahan Citra Digital
## Muhammad Harsya Permadi
## 202231024
![image](https://github.com/user-attachments/assets/0c8a1012-a407-436e-9d22-579c7024a505)<br>
Codingan di atas memuat tiga library yang penting untuk pemrosesan gambar dan visualisasi data: <br>
cv2: Library OpenCV untuk pemrosesan gambar dan video <br>
numpy: Library NumPy untuk komputasi numerik dan manipulasi array <br>
matplotlib.pyplot: Fungsi pyplot dari library Matplotlib untuk membuat visualisasi data <br>
![image](https://github.com/user-attachments/assets/0e9b374b-2dc1-482e-b56d-122652baf36e)<br>
Kode ini membaca gambar masukan dari file dengan nama gambar daun.jpeg dan menyimpannya dalam variabel input_image. <br>
Fungsi cv2.imread() digunakan untuk membaca gambar dan mengembalikannya sebagai array NumPy.<br>
Gambar yang dibaca oleh cv2.imread() dalam format BGR (Blue-Green-Red). Kode ini mengonversi gambar ke format RGB (Red-Green-Blue) menggunakan fungsi cv2.cvtColor(). Format RGB lebih umum digunakan dalam pemrosesan gambar.<br>
![image](https://github.com/user-attachments/assets/60cd383f-b421-49eb-9d08-9a4fca67a67c)<br>
Baris ini mengonversi gambar dari BGR ke HSV (Hue-Saturation-Value). HSV sering digunakan untuk segmentasi gambar berbasis warna karena memisahkan informasi warna dari informasi intensitas.<br>
![image](https://github.com/user-attachments/assets/8059803e-7be1-439d-bd50-43674cadeed9)<br>
bag_bawah: Batas bawah untuk Hue (0), Saturation (50), dan Value (50).<br>
bag_atas: Batas atas untuk Hue (30), Saturation (255), dan Value (255).<br>
Fungsi cv2.inRange() membuat mask biner mask_buah di mana piksel dalam rentang warna yang ditentukan disetel ke 255 (putih) dan lainnya ke 0 (hitam).<br>
![image](https://github.com/user-attachments/assets/eb39e8d9-b160-4504-abee-a8d051504d20)<br>
daun_bawah: Batas bawah untuk Hue (30), Saturation (40), dan Value (40).<br>
daun_atas: Batas atas untuk Hue (198), Saturation (255), dan Value (255).<br>
Fungsi cv2.inRange() membuat mask biner mask_daun di mana piksel dalam rentang warna yang ditentukan disetel ke 255 (putih) dan lainnya ke 0 (hitam).<br>
![image](https://github.com/user-attachments/assets/440ad2db-923f-4f7c-8b50-3bbd6343a3c8)<br>
Baris-baris ini menerapkan masker mask_buah dan mask_daun ke gambar asli img menggunakan operasi bitwise AND. Gambar yang dihasilkan buah dan daun hanya berisi piksel yang sesuai dengan buah dan daun yang diidentifikasi, masing-masing.<br>
![image](https://github.com/user-attachments/assets/8ce6235f-9322-4118-aebf-a746087bc6d2)<br>
![image](https://github.com/user-attachments/assets/a87594db-e60e-452f-af72-8a6497d67722)<br>
plt.subplots() membuat subplot dengan 2 baris dan 2 kolom.<br>
axs[i, j].imshow() menampilkan gambar di subplot (i, j).<br>
axs[i, j].set_title() mengatur judul subplot (i, j).<br>
plt.tight_layout() mengatur tata letak subplot agar tidak saling tumpang tindih.<br>
plt.show() menampilkan gambar<br>
Codingan di gambar ini menampilkan gambar RAW, mask buah, gambar buah, dan gambar daun dalam 4 subplot. Gambar RAW adalah gambar asli yang dimuat. Mask buah adalah gambar hitam putih yang menunjukkan area buah dalam gambar RAW. Gambar buah adalah gambar yang hanya menunjukkan area buah dalam gambar RAW. Gambar daun adalah gambar yang hanya menunjukkan area daun dalam gambar RAW.<br><br>
## Penjelasan Hasil Gambar<br>
Gambar 1: Gambar RAW<br>
Gambar RAW adalah gambar asli yang dimuat tanpa modifikasi apa pun.<br><br>
Gambar 2: Mask Buah<br>
Mask buah adalah gambar hitam putih yang menunjukkan area buah dalam gambar RAW.<br>
Area buah berwarna putih, sedangkan area lain berwarna hitam.<br>
Mask ini digunakan untuk memisahkan area buah dari area lain dalam gambar RAW.<br><br>
Gambar 3: Buah Ajaaa<br>
Gambar ini hanya menunjukkan area buah dalam gambar RAW.<br>
Area buah berwarna merah, sedangkan area lain berwarna hitam.<br>
Gambar ini dihasilkan dengan menggabungkan gambar RAW dan mask buah.<br><br>
Gambar 4: Daun Ajaa<br>
Gambar ini hanya menunjukkan area daun dalam gambar RAW.<br>
Area daun berwarna hijau, sedangkan area lain berwarna hitam.<br>
Gambar ini dihasilkan dengan menggabungkan gambar RAW dan mask daun.<br>


