# Tutorial 11

### Reflection 1: Minikube Start

1. Compare the application logs before and after you exposed it as a Service.
Try to open the app several times while the proxy into the Service is running.
What do you see in the logs? Does the number of logs increase each time you open the app?

Sebelum diexpose sebagai service:
![](images/1.png)
Log hanya menampilkan informasi bahwa aplikasi telah memulai HTTP server dan UDP server pada port yang berbeda.

<br>

Setelah diexpose sebagai service:
![](images/2.png)
Log kini menampilkan request yang masuk ke dalam aplikasi. Setiap kali aplikasi diakses, jumlah log bertambah, muncul log `GET /` yang menunjukkan request GET yang masuk ke dalam aplikasi.

<br>

2. Notice that there are two versions of `kubectl get` invocation during this tutorial section.
The first does not have any option, while the latter has `-n` option with value set to `kube-system`.
What is the purpose of the `-n` option and why did the output not list the pods/services that you explicitly created?

Opsi -n pada perintah kubectl get digunakan untuk menentukan namespace pencarian suatu objek. `-n kube-system` digunakan untuk mencari objek pada namespace kube-system.

Perintah yang telah dijalankan tidak menampilkan daftar pods/service karena mungkin daftar pods/service tersebut belum dibuat pada namespace `kube-system`. Daftar pods/services mungkin berada pada namespace lain selain kube-system sehingga tidak ditampilkan ketika kita menjalankan perintah dengan `-n kube-system`.
