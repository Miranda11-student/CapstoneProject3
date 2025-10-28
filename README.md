# Prediksi Harga Apartemen Daegu Menggunakan Machine Learning
# Contents

1. Business Problem Understanding
2. Data Understanding
3. Data Preprocessing
4. Modeling
5. Conclusion
6. Recommendation

****
## Business Problem Understanding
* Context : Stakeholder ingin menjalankan bisnis jual beli apartemen
* Problem Statement : Stakeholder kesulitan menentukan harga jual yang kompetitif.
* Goal :Dapat menciptakan tool yang dapat digunakan oleh stakeholder untuk menentukan harga penjualan apartementemen yang kompetitif
* Analytic Approach : model regresi.
* Metric Evaluation : RMSE,MAE dan MAPE

## Data Understanding

HallwayType :Tipe apartemen
TimeToSubway : Waktu yang dibutuhkan ke stasiun kereta bawah tanah terdekat
SubwayStation  : Nama stasiun kereta bawah tanah terdekat
N_FacilitiesNearBy(ETC)	: Nama stasiun kereta bawah tanah terdekat
N_FacilitiesNearBy(PublicOffice) :Jumlah fasilitas perkantoran di sekitar
N_SchoolNearBy(University) :Jumlah universitas di sekitar
N_Parkinglot(Basement) : Jumlah tempat parkir
YearBuilt	: Tahun apartemen dibangun
N_FacilitiesInApt :	Jumlah fasilitas di dalam apartemen
Size(sqft): 	Ukuran apartemen (dalam kaki persegi)
Sale Price : Harga Penjualan

## Data Preprocessing
* Collect Data
* Handling Data Type
* Handling Data Duplicate
* Drop Columns
* Missing Value
* Normalized Data
* Handle Outliers
* Fixed Data

## Modeling
* Melakukan Data Features Transformation
* Melakukan modeling , memutuskan untuk memakai model XGBoost

## Conclution
Berdasarkan data di bahwa fitur  'HallwayType	'('HallwayType_terraced') ,'Size'dan 'N_FacilitiesInApt' merupakan fitur yang paling berpengaruh terhadap fitur 'Sale Price'
Berdasarkan model diatas kita mengacu pada nilai RMSE setelah dilakukan hyperparamter tunning sebesar 46781 won . Kita dapat menyimpulakn bahwa Rata-rata, prediksi harga model Anda melenceng **+- 46871 won** dari harga jual apartemen yang sebenarnya.

Ada kemungkinan prediksinya meleset lebih jauh karena bias yang dihasilkan model masih cukup tinggi bila kita hitung berdasarkan hasil model sebesar +- 46871 won . Bias yang dihasilkan bisa terjadi karena kurangnya fitur fitur yang dapat menunjang improvisasi prediksi pada model.

Lakukan A/B testing terhadap model untuk mengoptimalkan kinerja, meningkatkan rasio konversi, dan mendapatkan wawasan tentang preferensi pengguna berdasarkan data yang terkumpul.

## Reccomendation

1. Menambahkan fitur yang lebih korelatif terhadap fitur 'saleprice' seperti 'Bedroom','Bathroom', dan 'Room' serta fitur lokasi seperti 'address','Lattitude', dan 'Longtitude' agar dapat dibuatkan grafik bertujuan agar stakeholder lebih mudah membaca persebaran apartemennya(data) serta adanya penambahan data terkini dan tentu akan dapat mengimprovisasi kapasitas prediksi dari model.
2. Model yang sudah dibangun ini bisa dimanfaatkan untuk pengembangan model selanjutnya semisal adanya data terbaru yang didapat ditahun berikutnya.
3. Setelah kita melakuakn A/B testing kita dapat Mengecek prediksi mana saja yang memiliki nilai error yang tinggi. Lalu, kita dapat mengelompokkan nilai mean dari nilai error tersebut. Setelahnya kita bisa mengecek hubungan antara error tersebut dengan tiap variabel independen. Pada akhirnya kita dapat mengetahui sebenarnya variabel mana saja dan aspek apa yang menyebabkan model menghasilkan error yang tinggi, sehingga kita bisa melakukan training ulang dengan penerapan feature engineering lainnya.
4. Hasil feature importance harus digunakan oleh stakeholder untuk menginformasikan keputusan mereka. Contoh, fitur  'HallwayType	'('HallwayType_terraced') sangat penting, investasi lebih lanjut dalam tipe apartemen terutama yang memiliki teras terbukti memberikan laba atas investasi yang baik (Return on Investment) atau fitur 'Size' salah satu fitur yang sangat penting, investasi lebih lanjut dalam luas apartemen terbukti memberikan laba atas investasi yang baik (Return on Investment)

