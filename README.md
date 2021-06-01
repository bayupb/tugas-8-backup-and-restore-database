Nama        : I Gde Bayu Priyambada Marayasa
Kelas       : 18 TI B1
Nim         : 311810199
Matakuliah  : Praktikum Perancangan Basis Data

-------------------------------------------------------------------------------------------

Hal pertama yang dilakukan untuk Backup & Restore Database pada MYSQL

Langkah membuka database melalui TERMINAL/CMD :
Karena xampp saya berada pada Disk D: , disini saya akan memanggil xampp dengan " D: cd xampp/bin/mysql/mysql -u root " dan akan muncul MariaDB

Langkah selanjutnya :
1) use databases;
2) show databases; -> ( nama database : bayupm_311810199 )
3) show tables; -> ( pilih table yang akan dipilih yaitu : mahasiswa )

-------------------------------------------------------------------------------------------

Langkah Penguncian Table:
MariaDB [bayupm_311810199]> lock table mahasiswa write;

![image](https://user-images.githubusercontent.com/83670094/120330406-fdd19600-c316-11eb-834a-3e5d2d3075ca.png)

Langkah Backup Table:
MariaDB [bayupm_311810199]> select * into outfile 'b_mahasiswa' from mahasiswa;

![image](https://user-images.githubusercontent.com/83670094/120330532-193ca100-c317-11eb-9c23-d9e6a6db2fd0.png)

MariaDB [bayupm_311810199]> delete from mahasiswa;

![image](https://user-images.githubusercontent.com/83670094/120362004-c540b500-c334-11eb-8c4f-1640790f7137.png)


MariaDB [bayupm_311810199]> select * from mahasiswa;

![image](https://user-images.githubusercontent.com/83670094/120362038-d12c7700-c334-11eb-86ba-344fb32cf7fe.png)

-------------------------------------------------------------------------------------------

Langkah Load Data Infile Table:
MariaDB [bayupm_311810199]> select * into outfile 'b_mahasiswa' from mahasiswa;

![image](https://user-images.githubusercontent.com/83670094/120362107-e86b6480-c334-11eb-8802-046cad813c81.png)

![image](https://user-images.githubusercontent.com/83670094/120362217-0a64e700-c335-11eb-9bf1-f541f0ce7797.png)

![image](https://user-images.githubusercontent.com/83670094/120363330-3a60ba00-c336-11eb-9d19-5d966424eeac.png)

-------------------------------------------------------------------------------------------

Langkah Backup & Restore menggunakan MYSQLDUMP:
D:\xampp\mysql\bin>mysqldump -u root -p bayupm_311810199 > backup.sql

![image](https://user-images.githubusercontent.com/83670094/120362266-151f7c00-c335-11eb-9c9c-b8300f3f5277.png)

dilanjut :
D:\xampp\mysql\bin>mysqldump -u root -p bayupm_311810199 < D:\xampp\mysql\bin\backup.sql

![image](https://user-images.githubusercontent.com/83670094/120362295-1f417a80-c335-11eb-877b-af01be51bd17.png)

-------------------------------------------------------------------------------------------

Langkah Backup & Recory menggunakan di MYSQL - PHPMYADMIN:
-Pertama buka terlebih dahulu xampp nya:
  * Nyalakan MYSQL & APACHE.
 
 ![image](https://user-images.githubusercontent.com/83670094/120362578-6a5b8d80-c335-11eb-96af-4e8139f7c555.png)

-Tahap selanjutnya, pergi ke phpmyadmin, lalu klik nama database ( bayupm_311810199 )

![image](https://user-images.githubusercontent.com/83670094/120362708-8fe89700-c335-11eb-9a70-e0d52f3e121b.png)

-Setelah membuka databasenya, kemudian dilanjutkan ke bagian Menu yang ada di database dengan nama:
  - Export:
  
  ![image](https://user-images.githubusercontent.com/83670094/120362838-b9092780-c335-11eb-8a6f-91ead8896804.png)
  
  Lalu, pilih Go / Simpan
  
  - Import:

  ![image](https://user-images.githubusercontent.com/83670094/120362988-dd650400-c335-11eb-8853-49457961b73e.png)
  
  Kemudian klik bagian ' choose file ' dan pilih file database berbentuk extensi .sql, lalu pilih Go


*-----------------------------------------------------------------------------------*

**Laporan**
Karena phpmyadmin mampu memberikan pengaman yang baik untuk menjaga terjadi serangan dari hacker maupun backup harian untuk menjaga terjadi masalah teknis atau kerusakan data yang akan ditimbulkan.
Maka dari itu phpmyadmin, mampu memberikan export database berupa extensi .sql dan dilanjutkan untuk meng-import database jika dibutuhkan, sehingga memudahkan kita untuk memperbaiki data atau penambahan.
Mungkin itu yang saya bisa sampaikan.

Terimakasih-
