# Coffee Sales Dashboard

## Tujuan
Proyek ini bertujuan untuk memberikan wawasan mendalam mengenai penjualan kopi serta memfasilitasi pengambilan keputusan bisnis yang lebih bijak. 

## Daftar Isi
- [Tentang Dataset](#tentang-dataset)
- [Data Preprocessing](#data-preprocessing)
- [Visualisasi Data](#visualisasi-data)
- [Hasil Analisis](#hasil-analisis)

## Tentang Dataset
Dataset ini terdiri dari 3 tabel yaitu `orders`, `customers`, dan `products`. Berikut adalah contoh dari ketiga tabel tersebut.
- Tabel Orders <br/>
![Orders](https://github.com/dikfaj/Microsoft-Excel/assets/39393133/18e5a5f4-a965-46e0-8463-f5ca9d48dbbe)
<br/>Terdiri dari kolom Order ID, Order Date, Customer ID, Product ID dan Quantity.
- Tabel Customers <br/>
![customers](https://github.com/dikfaj/Microsoft-Excel/assets/39393133/92e57dd3-af70-4a1f-acea-7de938d6c805)
<br/>Terdiri dari kolom Customer ID, Customer Name, Email, Phone Number, Address Line 1, City, Country, Postcode dan Loyalty Card.
- Tabel Products<br/>
![products](https://github.com/dikfaj/Microsoft-Excel/assets/39393133/45fe61ea-5e4b-4f2d-8ef9-5b2894af6610)
<br/>Terdiri dari kolom Product ID, Coffee Type, Roast Type Size, Unit Price, Price per 100g dan Profit.

## Data Preprocessing
### Data Integration
Langkah pertama yang dilakukan adalah menggabungkan ketiga tabel tersebut menjadi satu tabel utuh dengan menggunakan beberapa fungsi.
- VLOOKUP <br/>
Dengan menggunakan fungsi `VLOOKUP` untuk menambahkan kolom Customer Name, Country, dan Loyalty Card dari tabel `Customers` ke dalam tabel `Orders` dan `Profit` dari tabel products. Contohnya adalah <br/> `=VLOOKUP(C2;customers!$A$2:$I$1001;2;0)`.
- INDEX dan MATCH <br/>
Dengan menggunakan funsgi `INDEX` dan `MATCH` untuk menambahkan kolom Coffee Type, Roast Type Size, Unit Price dari tabel `Products` ke tabel `Orders`. Contohnya adalah `=INDEX(products!$A$1:$G$49;MATCH(orders!$D2;products!$A$1:$A$49;0);MATCH(I$1;products!$A$1:$G$1;0))`
- IF <br/>
Untuk memudahkan dalam membaca data, kita perlu mengubah beberapa data seperti pada kolom `Coffee Type` dan `Roast Type Size` ke dalam kolom baru.<br/>
Berikut adalah formula untuk mengubah `Coffee Type` menjadi `Coffee Type Name`. <br/> `=IF(J2="Rob";"Robusta";IF(J2="Exc";"Excelsa";IF(J2="Ara";"Arabica";IF(J2="Lib";"Liberica";""))))` <br/>
Berikut adalah formula untuk mengubah `Roast Type Size` menjadi `Roast Type Name`. <br/> `=IF(K2="M";"Medium";IF(K2="L";"Light";IF(K2="D";"Dark")))`.
- Perkalian
  Dengan menggunakan perkalian untuk menghitung `sales` dengan cara mengalikan `unit price` dengan `quantity`. Dan `profit` dikali dengan `quantity`

Berikut adalah data setelah melalui proses Data Integration
![after integration](https://github.com/dikfaj/Microsoft-Excel/assets/39393133/e89c545c-4a31-4088-a0d7-d86caa96d5d5)

### Data Formatting
- Mengubah Format Tanggal
  Mengubah format kolom `date` menjadi dd-mmm-yyyy (contoh: 12-Sep-2023)
  ![date](https://github.com/dikfaj/Microsoft-Excel/assets/39393133/9631f766-9620-4cfb-ab63-0f80bdb96e4b)
- Mengubah Format Angka
  Mengubah kolom `Size` menjadi "0,0 Kg" (contoh: 1,5 Kg) dan kolom Harga `Unit Price` dan `Sales` menjadi Dollar Amerika (contoh: $3.25) <br/>
  ![currency](https://github.com/dikfaj/Microsoft-Excel/assets/39393133/0f3a2e82-4008-4709-9ac5-c68047b9e84f)
  ![size](https://github.com/dikfaj/Microsoft-Excel/assets/39393133/b02e599d-5684-4c2f-8221-e42e34076186)
- Data Duplikat
  Memeriksa data duplikat di menu `Data` - `Remove Duplicate`
- Format Tabel
  Terakhir adalah memformat tabel menjadi format Table di menu `Insert` - `Table` untuk mempermudah manajemen dan perbaruan data

  Berikut adalah tampilan dari data yang siap untuk diolah.
 ![Done](https://github.com/dikfaj/Microsoft-Excel/assets/39393133/c704c4c9-badc-41bb-b74a-c89c51cd0652)

## Visualisasi Data
Analisis data menggunakan `Pivot Table` kemudian dibuat menjadi chart.
- Total Sales Over Time menggunakan Line Chart
- Sales By Country menggunakan Bar Chart
- Top 5 Customers menggunakan Bar Chart
- Menambahkan Timeline dan Slicers pada grafik pivot untuk filtering interaktif

Berikut adalah tampilan dashboard interaktif yang telah dibuat
![dashboard](https://github.com/dikfaj/Microsoft-Excel/assets/39393133/387ad85d-9e0c-456a-9695-d107cd235c24)

## Hasil Analisis
- <b>Tren penjualan:</b> Dengan menggunakan Line Chart yang interakif dapat melihat tren penjualan kopi dalam beberapa tahun terakhir. Tren penjualan kopi menunjukan penjualan yang stabil dari tahun ke tahun.
- <b>Produk Terlaris:</b> Produk terlaris diantara ke empat jenis kopi adalah Excelsa.
- <b>Profit<b/>: Walaupun Excelsa menjadi kopi dengan penjualan tertinggi, kopi jenis Liberica menghasilkan profit paling tinggi.
- <b>Kontribusi Pelanggan:</b> Beberapa pelanggan berkontribusi signifikan terhadap penjualan kopi. Selain itu, Amerika menjadi negara dengan penjualan tertinggi. Tidak heran bahwa negara ini merupakan negara dengan konsumsi kopi terbesar di dunia.Dengan data ini stakeholder bisa memutuskan untuk memberikan reward kepada para pelanggan dengan penjualan tertinggi. 

