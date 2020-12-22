#Membangun Infrastruktur Apache Spark 
1. login ke VM dengan memasukkan ip public VM pada bagian host Name (or IP address). kemudian masukkan username dan password V< untuk memulai membangun infrastruktur apache spark.
2. Sebelum memasang perangkat lunak baru, ada baiknya untuk menyegarkan basis data paket perangkat lunak lokal Anda untuk memastikan Anda mengakses versi terbaru. 
Buka terminal dan ketik perintah dibawah ini : 

sudo apt-get update 

3. Install Java  Untuk melakukan instalasi pada java bisa menggunakan perintah dibawah : 

sudo apt-get install default-jdk 
 
4. kalau sudah sudah dilakukan kita mengecek kembali versi yang digunakan : 

java –version 
 
5. Create Direktori Membuat Direktori baru untuk minyampan file apache dengan menggunakan perintah : 

mkdir –p /opt/responsi 
dan kemudian  
cd /opt/responsi 
  
6. Download apche spark package  
Selanjutnya kita harus mendownload paket-paket dari apache spark 
untuk mendownload bisa mengakses https://spark.apache.org/downloads.html dan pilih spark yang ingin digunakan dan download. 
Atau bisa menggunakan perintah dibawah ini : 

wget https://downloads.apache.org/spark/sprak1.4.7/spark-2.4.7-bin-hadoop2.7.tgz

7. Comperesed Selanjutnya melakukan proses kompresi dari file apche yang telah didownload dengan menggunakan perintah : 

tar -xvf spark-2.4.7-bin-hadoop2.7.tgz 
 
8. Configure the Environment Sebelum memulai server master Spark, ada beberapa variabel yang perlu dikonfigurasi. 

vi~/.bashrc 
Dan masukkan  
Start Apcahe Spark 

9. Setelah dikonfigurasi, selanjutnya adalah memulai server master Spark. Perintah sebelumnya menambahkan direktori yang diperlukan ke variabel PATH sistem, jadi perintah ini dapat dijalankan dari direktori mana pun: 

start-master.sh 
   
10. Web interface
ini untuk mengetahui proses yang berjalan dan lokasi spark yang dapat di akses melalui web. Selain itu juga untuk mengetahui url spark untuk digunakan menjalankan perintah slave nantinya. 

ss –tunelp | grep 8080 
 
11. Create new File Membuat sebuah file dapat menggunakan perintah dibawah :  

pico input.text 
 
Text yang akan dimasukan : 
   
12. Setelah itu di save. 

13.Verify spark shell installation 
Untuk memverifikasi apakah spark-shell dipasang dengan benar. Ketik spark-shell di terminal. 

Spark-shell 
 
14. memanggil file ke dalam sini dengan cara mengetikan perintah dibawah : 

val inputfile = sc.textFile(“input.text”) 
Kita telah berhasil mengambil file nya 
  
15. Seluruh hasil akan tersimpan dalam direktori output dan kemudian save 
 
16. Exit Spark-Shell 
Untuk keluar dari spark-shella, 

tekan CTRL C. 
Kemudian masuk ke dalam direktori output untuk mengecek hasil spark 

cd output/ 

Setelah itu 

Cat part-00000 
 
17. Shut Down Apache Spark 
Untuk mematikan proses dari Apache dapat menggunakan perintah dibawah 

stop-slave.sh 
stop-master.sh 
 
 exit ()
 
