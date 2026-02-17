## Nama        : Irham Najib Azimul Qowi
## NIM         : 244311045
## Prodi/Kelas : TRPL/4B

## 1. Analisis Data Terstruktur (Structured Data)

### 1.1 Deskripsi Sumber Data
- Nama Database/Dataset: World Bank GDP Data (Gross Domestic Product per Country)
- Format: CSV
- Ukuran Data: ± 5–10 MB
- Sumber: World Bank Open Data (<https://data.worldbank.org/indicator/NY.GDP.MKTP.CD>)

### 1.2 Karakteristik
- Schema/Struktur: Dataset berbentuk tabel dengan kolom Country Name, Country Code, Indicator Name, Indicator Code, Year, dan GDP Value.
- Tipe Data: Text (negara, indikator), Integer (tahun), Float (nilai GDP).
- Relasi antar Data: Relasi antar negara dan tahun (time-series), setiap negara memiliki data GDP per tahun.
- Kualitas Data: Sangat tinggi (divalidasi World Bank), terdapat missing value pada beberapa negara berkembang.
- Frekuensi Update: Tahunan.

### 1.3 Potensi Use Cases
- Use Case 1:
  - Deskripsi: Analisis pertumbuhan ekonomi negara.
  - Manfaat Bisnis: Membantu investor menentukan negara tujuan investasi; mendukung perencanaan ekspansi perusahaan global.
  - Technical Requirements: SQL / Python / Excel; data visualization tools (Tableau/PowerBI).
- Use Case 2:
  - Deskripsi: Prediksi pertumbuhan ekonomi menggunakan machine learning untuk menangani kemiskinan di dunia.
  - Manfaat Bisnis: Forecast kondisi pasar global; risk management.
  - Technical Requirements: Python; machine learning model; time series analysis.

## 2. Analisis Data Semi-Terstruktur (Semi-structured Data)

### 2.1 Deskripsi Sumber Data
- Nama Dataset/File: OpenStreetMap Geographic Data (Overpass API Response)
- Format: JSON
- Ukuran Data: ± 10 KB – 1 MB per request
- Sumber: OpenStreetMap Overpass API (<https://overpass-api.de/api/interpreter>)
- Sample data langsung bisa dibuka:
  - `https://overpass-api.de/api/interpreter?data=[out:json];node["amenity"="restaurant"](-6.2,106.8,-6.1,106.9);out;`
- (Tidak perlu login atau API key)

### 2.2 Karakteristik
- Format Spesifik: JSON (key-value format).
- Struktur Data: Struktur data bersifat nested dan fleksibel.
- Flexibilitas: Struktur fleksibel, field dapat berbeda tergantung query, dan tidak memiliki schema tetap seperti database relasional.
- Challenges: Struktur nested kompleks, membutuhkan parsing JSON, dan data bisa tidak lengkap pada beberapa lokasi.
- Aksesibilitas: Dapat diakses langsung melalui HTTP request, tidak memerlukan akun atau API key, serta open data berbasis komunitas.

### 2.3 Potensi Use Cases
- Use Case 1:
  - Deskripsi: Analisis lokasi bisnis umkm yang strategisberdasarkan data geografis.
  - Manfaat Bisnis: Menentukan lokasi strategis pembukaan cabang; analisis kompetitor berdasarkan lokasi.
  - Technical Requirements: JSON parsing; Geographic Information System (GIS).
- Use Case 2:
  - Deskripsi: Sistem navigasi atau rekomendasi tempat terdekat.
  - Manfaat Bisnis: Meningkatkan layanan berbasis lokasi; mendukung aplikasi transportasi dan delivery.
  - Technical Requirements: API integration; location processing; geographic data analysis.

## 3. Analisis Data Tidak Terstruktur (Unstructured Data)

### 3.1 Deskripsi Sumber Data
- Tipe Data: Teks laporan kesehatan masyarakat
- Format: PDF
- Ukuran Data: ± 2–10 MB per dokumen
- Sumber: Centers for Disease Control and Prevention (CDC) (<https://www.cdc.gov>)
- Contoh sample (langsung download PDF — tanpa login): <https://www.cdc.gov/mmwr/volumes/72/wr/pdfs/mm7201a1-h.pdf>

### 3.2 Karakteristik
- Kompleksitas:
  - Data berupa bahasa alami.
  - Berisi paragraf panjang dan narasi ilmiah.
  - Tidak memiliki struktur tabel yang konsisten.
- Storage Requirements:
  - Membutuhkan document storage.
  - Ukuran file relatif besar dibanding data terstruktur.
- Processing Challenges:
  - Membutuhkan teknik Natural Language Processing (NLP).
  - Ekstraksi teks dari PDF.
  - Named entity recognition dan text mining.
- Data Quality Issues:
  - Ambiguitas bahasa.
  - Istilah medis kompleks.
  - Format dokumen bervariasi.
- Accessibility:
  - Dapat diakses langsung melalui website CDC.
  - Membutuhkan PDF reader atau tools ekstraksi teks.

### 3.3 Potensi Use Cases
- Use Case 1:
  - Deskripsi: Analisis tren penyakit dan laporan kesehatan masyarakat untuk pengalokasian pengobatan gratis bagi masyarakat.
  - Manfaat Bisnis:
    - Mendukung kebijakan kesehatan publik.
    - Perencanaan layanan kesehatan.
    - Pengembangan produk kesehatan.
  - Technical Requirements: NLP; machine learning.
- Use Case 2:
  - Deskripsi: Ekstraksi informasi penting dari laporan kesehatan.
  - Manfaat Bisnis:
    - Mendukung riset farmasi.
    - Pengambilan keputusan kesehatan berbasis data.
  - Technical Requirements: NLP; data preprocessing.

## 4. Kesimpulan dan Rekomendasi

### 4.1 Ringkasan Temuan
- Structured Data: Memiliki schema jelas, mudah dianalisis, dan cocok untuk analisis statistik.
- Semi-structured Data: Fleksibel dan cocok untuk data real-time, namun membutuhkan preprocessing.
- Unstructured Data: Mengandung informasi kaya tetapi sulit diproses.

### 4.2 Rekomendasi
- Technical Recommendations: Gunakan data warehouse untuk structured data, API pipeline untuk semi-structured data, dan NLP untuk unstructured data.
- Business Recommendations: Structured data untuk reporting, semi-structured untuk monitoring, dan unstructured untuk analisis strategis.
- Implementation Priorities:
  - Structured data
  - Semi-structured data
  - Unstructured data

### 4.3 Next Steps
- Short-term Actions: Mengunduh dataset dan menyiapkan pipeline data.
- Long-term Planning: Implementasi machine learning dan integrasi data.
- Resource Requirements: Data engineer, data analyst, dan infrastruktur penyimpanan.

## 5. Lampiran
- Data Samples
  - Data Terstruktur :
  ```csv
  "Country Name","Country Code","Indicator Name","Indicator Code","1960","1961","1962","1963","1964","1965","1966","1967","1968","1969","1970","1971","1972","1973","1974","1975","1976","1977","1978","1979","1980","1981","1982","1983","1984","1985","1986","1987","1988","1989","1990","1991","1992","1993","1994","1995","1996","1997","1998","1999","2000","2001","2002","2003","2004","2005","2006","2007","2008","2009","2010","2011","2012","2013","2014","2015","2016","2017","2018","2019","2020","2021","2022","2023","2024",
  "Aruba","ABW","GDP (current US$)","NY.GDP.MKTP.CD","","","","","","","","","","","","","","","","","","","","","","","","","","","405586592.178771","487709497.206704","596648044.692737","695530726.256983","764804469.273743","872067039.106145","958659217.877095","1083240223.46369","1245810055.86592","1320670391.06145","1379888268.15642","1531843575.41899","1665363128.49162","1722905027.93296","1873452513.96648","1896456983.24022","1961843575.41899","2044111731.84358","2254830726.25698","2360017318.43575","2469782681.56425","2677641340.78212","2843024581.00559","2553793296.08939","2453597206.70391","2637859217.87709","2615208379.88827","2727849162.01117","2790849720.67039","2962906703.91061","2983637430.1676","3092427932.96089","3276187709.49721","3346623191.45988","2471419181.71957","2880902798.92288","3324034443.26581","3834729616.12027","4265650673.00236",
  "Africa Eastern and Southern","AFE","GDP (current US$)","NY.GDP.MKTP.CD","24205688712.3759","24958886027.4641","27073233856.5389","31769135008.6453","30279553206.6418","33806176716.8471","36927249593.1569","38444163573.9168","41742001495.4024","47048523178.8515","47593907819.7874","52188685166.5557","56726057494.0767","73083598128.682","89535976340.3864","95295754526.8723","96006417139.9692","109208244154.943","124083421003.115","142099959764.832","178472295521.021","185108969364.767","178355547527.525","185755503030.119","170038515839.183","149335153752.165","160553515127.741","190175229570.901","207368870172.406","220613390803.074","256383050159.487","276918502950.348","241188307967.9","239981176638.05","243477534983.306","273327034187.587","273427612467.252","288270699674.414","268728127688.21","265321007618.974","287041984552.036","260849957489.123","269746009737.979","358116081062.427","445974808500.088","521561976778.096","587500469826.421","674999944547.619","726770401376.729","726921646144.603","863822114606.332","959822476083.878","969265729636.028","981308886976.783","998836162271.296","910002035578.038","831868076442.431","978076465866.452","1020955778298.17","1018714795912.35","938607563405.087","1114144799994.21","1228967879390.01","1179359054880.45","1242693542929.85",
  "Afghanistan","AFG","GDP (current US$)","NY.GDP.MKTP.CD","","","","","","","","","","","","","","","","","","","","","","","","","","","","","","","","","","","","","","","","","3521418059.92345","2813571753.87253","3825701438.99963","4520946818.54581","5224896718.67782","6203256538.70967","6971758282.29351","9747886187.39393","10109297047.5432","12416152732.0567","15856668555.8336","17805098206.3141","19907329777.5872","20146416757.5987","20497128555.6972","19134221644.7325","18116572395.0772","18753456497.8159","18053222687.4126","18799444490.1128","19955929052.1496","14259995441.0759","14497243872.1337","17152234636.8715","",
  "Africa Western and Central","AFW","GDP (current US$)","NY.GDP.MKTP.CD","11904805741.6831","12707719290.6273","13630588814.3032","14468913698.0467","15803564796.4118","16920876929.6607","18033947666.935","16493541543.816","17022596883.7037","19301191937.1478","26696924213.8055","24496786001.8079","29489425515.7538","36890633234.1126","49687223643.2392","57280116275.6847","68385552348.1688","71789497552.1911","78778080489.5676","96681064864.1808","121445961252.94","217606540487.256","196264853551.918","151421439334.1","131373058519.308","138005066699.39","109517776160.1","112641148828.574","111770322169.923","104577372052.932","124277825786.697","130794315519.503","125449432677.392","130547124413.669","135350756019.393","207843864308.605","263563556144.176","276460023661.745","297126502718.937","140119071338.285","142700161610.079","150714426912.056","180129182230.862","208646527354.851","257939299771.713","316515667947.035","402077365740.581","470947616490.719","574259808704.121","515037106035.659","605794323433.505","691133400013.31","748030003656.802","844180401591.48","904071921008.085","778022057597.448","700028168335.244","694051345937.233","777840323023.311","1026996211935.8","963784699293.976","1026651004045.79","1063649130876.99","938238370514.198","736384961061.523",
  "Angola","AGO","GDP (current US$)","NY.GDP.MKTP.CD","","","","","","","","","","","","","","","","","","","","","5930503400.96263","5550483035.96497","5550483035.96497","5784341596.36339","6131475065.17815","7554065410.121","7072536108.69711","8084412414.26566","8769836768.83482","10201780976.6696","11229515599.3048","10603784541.197","8307810973.58848","5768720421.61367","4438321017.39068","5538749259.94714","7526421519.16979","7648380195.59902","6506221615.78722","6152923310.44546","9129594970.15301","8936079117.73136","17311512432.451","20342128111.9753","26997977896.5924","41396636383.3725","58653659979.711","73037821926.6813","98790432989.4067","81705175408.3893","95546919754.7633","125551634704.473","143572907527.976","148845200696.792","153449860496.402","102543067840.732","59878249719.3279","84376935689.3366","89512794227.495","80734428592.5368","58852456453.8769","79559543805.2963","131212208930.344","107167747140.127","100998916781.079",
  ```
  - Data Semi Terstruktur:
  ```json
  {
    "type": "node",
    "id": 824318011,
    "lat": -6.1853139,
    "lon": 106.8292687,
    "tags": {
      "amenity": "restaurant",
      "name": "Burger Bangor"
    }
  }
  ```
  - Data Tidak Terstruktur:
  <https://www.cdc.gov/mmwr/volumes/72/wr/pdfs/mm7201a1-h.pdf>

- Technical Documentation:
  - Data diunduh dalam format CSV dan diproses menggunakan tools analisis data seperti Microsoft Excel atau Python (Pandas) untuk pembersihan data, analisis statistik, dan visualisasi.
  - Data diakses melalui HTTP request dan diproses menggunakan teknik parsing JSON untuk mengekstrak informasi lokasi yang relevan menggunakan Python atau tools pengolahan data.
  - Data berupa dokumen PDF yang diproses menggunakan teknik ekstraksi teks dan analisis Natural Language Processing (NLP) untuk memperoleh informasi dari teks.
