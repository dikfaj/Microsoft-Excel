# Coffee Sales Dashboard

## Tujuan
Proyek ini bertujuan untuk memberikan wawasan mendalam mengenai penjualan kopi serta memfasilitasi pengambilan keputusan bisnis yang lebih bijak. 

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
Dengan menggunakan fungsi `VLOOKUP` untuk menambahkan kolom Customer Name, Country, dan Loyalty Card dari tabel `Customers` ke dalam tabel `Orders`. Contohnya adalah <br/> `=VLOOKUP(C2;customers!$A$2:$I$1001;2;0)`.
- INDEX dan MATCH <br/>
Dengan menggunakan funsgi `INDEX` dan `MATCH` untuk menambahkan kolom Coffee Type, Roast Type Size, Unit Price dari tabel `Products` ke tabel `Orders`. Contohnya adalah `=INDEX(products!$A$1:$G$49;MATCH(orders!$D2;products!$A$1:$A$49;0);MATCH(I$1;products!$A$1:$G$1;0))`
- IF <br/>
Untuk memudahkan dalam membaca data, kita perlu mengubah beberapa data seperti pada kolom `Coffee Type` dan `Roast Type Size` ke dalam kolom baru.<br/>
Berikut adalah formula untuk mengubah `Coffee Type` menjadi `Coffee Type Name`. <br/> `=IF(J2="Rob";"Robusta";IF(J2="Exc";"Excelsa";IF(J2="Ara";"Arabica";IF(J2="Lib";"Liberica";""))))` <br/>
Berikut adalah formula untuk mengubah `Roast Type Size` menjadi `Roast Type Name`. <br/> `=IF(K2="M";"Medium";IF(K2="L";"Light";IF(K2="D";"Dark")))`.
- Perkalian
Dengan menggunakan perkalian untuk menghitung `sales` dengan cara mengalikan `unit price` dengan `quantity`

Berikut adalah data setelah melalui proses Data Integration
![after integration](https://github.com/dikfaj/Microsoft-Excel/assets/39393133/ef338681-2177-404b-96c8-92a8e664ccd4)

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
  ![Done](https://github.com/dikfaj/Microsoft-Excel/assets/39393133/7a21974d-0d7a-4265-9839-26721b199d74)
