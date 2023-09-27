# Bike Sales Dashboard
Seorang sales manager ingin mengetahui bagaimana profil seseorang mempengaruhi pembelian sepeda. Oleh karena itu, dia meminta seorang Data Analyst untuk membuatkan dashboard agar dia dapat mengambil keputusan.

## Tentang Dataset
Dataset ini berisi 13 variabel dan 1026 baris.
Variabelnya adalah
- ID
- Marital Status
- Gender
- Income
- Children
- Education
- Occupation
- Home Owner
- Cars
- Commute Distance
- Region
- Age
- Purchase Bike

Berikut adalah contoh dari dataset tersebut <br/>

![Data overview](https://github.com/dikfaj/Microsoft-Excel/assets/39393133/dd8281bf-4da9-417f-af94-143f495b5cc4)


## Data Preprocessing
Sebelum masuk ke dalam pengolahan data. Hal pertama yang harus dilakukan adalah memastikan data yang akan diolah sudah terhindar dari missing value, duplicate data dan lain-lain. <br/>
Dengan menggunakan fitur `Conditional Formatting - Highlight Cell Rules - Duplicate Values` kita dapat mengetahui apakah terdapat duplicate data atau tidak. <br/>
Duplicate data ditandai dengan warna merah, untuk menghapus duplicate data tersebut kita dapat menggunakan fitur `Remove Duplicate` pada tab `Data`.

![duplicate](https://github.com/dikfaj/Microsoft-Excel/assets/39393133/700bd3c9-d13b-4d19-be42-fb7fe39d1d54)
Ditemukan duplicate data sebanyak 26 data. Setelah duplicate data dihapus, data berkurang dari 1026 baris menjadi 1000 baris. <br/>

Selanjutnya adalah mengubah `Marital Status` dari `M` dan `S` menjadi `Married` dan `Single`. Hal ini bertujuan untuk memudahkan dalam membaca data. Proses perubahan dapat dilakukan dengan fitur  `Find And Replace` atau dengan shortcut `CTRL + H`. <br/>
Hal yang sama juga dilakukan pada kolom `Gender`. Kita ubah `M` menjadi `Male` dan `F` menjadi `Female`. <br/>

Berikut adalah tampilan ketika data tersebut sudah kita ubah.<br/>
![Trans](https://github.com/dikfaj/Microsoft-Excel/assets/39393133/a7434314-971f-44e3-b18a-e21ffeb8ffb4)

Hal yang sama juga dilakukan pada kolom `Commute Distance` agar data berurutan secara ascending, kita ubah `10+ Miles` menjadi `More Than 10 Miles`. <br/>
![commute](https://github.com/dikfaj/Microsoft-Excel/assets/39393133/0d5b7ca0-7164-4460-8d6e-ba0a74d6fb0d)
![commute1](https://github.com/dikfaj/Microsoft-Excel/assets/39393133/a2f0e7db-ed24-47e5-92f7-e65c472b3058)

Pada kolom `Age`, range data antara `25 sampai 89 tahun`. Kita akan buat kolom baru dengan nama `Age Bracket` untuk menyimpan data dengan ketentuan sebagai berikut:
- 11 - 26 : Gen Z
- 27 - 42 : Gen Y
- 43 - 58 : Gen X
- diatas 59 : Baby Boomers

Berikut adalah tampilan data setelah melalui proses Data Preprocessing dan siap untuk divisualisasikan.<br/>
![DONE](https://github.com/dikfaj/Microsoft-Excel/assets/39393133/3898d085-a3f0-4117-8459-2e013c66bb4d)
## Pivot Table

## Dashboard
