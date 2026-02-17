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
  - Deskripsi: Prediksi pertumbuhan ekonomi menggunakan machine learning.
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
- Struktur Data: Struktur data bersifat nested dan fleksibel:

```json
{
  "elements": [
    {
      "id": 123456,
      "lat": -6.2,
      "lon": 106.8,
      "tags": {
        "name": "Restaurant A",
        "amenity": "restaurant"
      }
    }
  ]
}
```

- Flexibilitas: Struktur fleksibel, field dapat berbeda tergantung query, dan tidak memiliki schema tetap seperti database relasional.
- Challenges: Struktur nested kompleks, membutuhkan parsing JSON, dan data bisa tidak lengkap pada beberapa lokasi.
- Aksesibilitas: Dapat diakses langsung melalui HTTP request, tidak memerlukan akun atau API key, serta open data berbasis komunitas.

### 2.3 Potensi Use Cases
- Use Case 1:
  - Deskripsi: Analisis lokasi bisnis berdasarkan data geografis.
  - Manfaat Bisnis: Menentukan lokasi strategis pembukaan cabang; analisis kompetitor berdasarkan lokasi.
  - Technical Requirements: JSON parsing; Geographic Information System (GIS); data visualization tools.
- Use Case 2:
  - Deskripsi: Sistem navigasi atau rekomendasi tempat terdekat.
  - Manfaat Bisnis: Meningkatkan layanan berbasis lokasi; mendukung aplikasi transportasi dan delivery.
  - Technical Requirements: API integration; location processing; geographic data analysis.

## 3. Analisis Data Tidak Terstruktur (Unstructured Data)

### 3.1 Deskripsi Sumber Data
- Tipe Data: Teks laporan kesehatan
- Format: PDF
- Ukuran Data: ± 50–200 MB
- Sumber: World Health Organization Reports (<https://www.who.int/publications>)

### 3.2 Karakteristik
- Kompleksitas: Bahasa alami, paragraf panjang, tidak memiliki struktur tabel.
- Storage Requirements: Ukuran data besar dan membutuhkan document storage.
- Processing Challenges: Perlu NLP, ekstraksi teks dari PDF, named entity recognition.
- Data Quality Issues: Ambiguitas bahasa, istilah medis kompleks, format dokumen berbeda.
- Accessibility: Perlu PDF reader dan text extraction tools.

### 3.3 Potensi Use Cases
- Use Case 1:
  - Deskripsi: Analisis tren penyakit global.
  - Manfaat Bisnis: Mendukung kebijakan kesehatan; pengembangan obat.
  - Technical Requirements: NLP; text mining; machine learning.
- Use Case 2:
  - Deskripsi: Ekstraksi insight penelitian kesehatan.
  - Manfaat Bisnis: Mendukung riset farmasi; pengambilan keputusan kesehatan publik.
  - Technical Requirements: NLP model; data preprocessing; knowledge extraction.

## 4. Kesimpulan dan Rekomendasi

### 4.1 Ringkasan Temuan
- Structured Data: Mudah dianalisis, schema jelas, cocok untuk analisis statistik dan bisnis.
- Semi-structured Data: Fleksibel, cocok untuk data geografis berbasis lokasi, dan dapat diakses real-time tanpa API key, namun butuh parsing JSON serta validasi kelengkapan data.
- Unstructured Data: Informasi paling kaya, sulit diproses, perlu teknologi AI/NLP.

### 4.2 Rekomendasi
- Technical Recommendations: Gunakan data warehouse untuk structured data; gunakan pipeline API + JSON parsing + GIS untuk semi-structured data; gunakan NLP untuk unstructured data.
- Business Recommendations: Gunakan structured data untuk reporting; gunakan semi-structured data geografis untuk strategi lokasi dan layanan berbasis lokasi; gunakan unstructured untuk strategic insights.
- Implementation Priorities: Structured data → prioritas awal; semi-structured (geospatial integration) → tahap pengembangan sistem; unstructured → advanced analytics.

### 4.3 Next Steps
- Short-term Actions: Download dataset sample; uji query Overpass API; setup data pipeline.
- Long-term Planning: Integrasi data geospasial ke sistem analitik; implement machine learning system; data integration platform.
- Resource Requirements: Data engineer; data analyst; GIS specialist; storage infrastructure.

## 5. Lampiran
- Data Samples:
  - World Bank GDP CSV sample: <https://data.worldbank.org/indicator/NY.GDP.MKTP.CD>
  - OpenStreetMap Overpass JSON sample: <https://overpass-api.de/api/interpreter>
  - OpenStreetMap Overpass sample query: `https://overpass-api.de/api/interpreter?data=[out:json];node["amenity"="restaurant"](-6.2,106.8,-6.1,106.9);out;`
  - WHO Report PDF sample: <https://www.who.int/publications>
- Technical Documentation:
  - World Bank Data Docs: <https://datahelpdesk.worldbank.org>
  - OpenStreetMap Overpass API Docs: <https://wiki.openstreetmap.org/wiki/Overpass_API>
  - WHO Publications: <https://www.who.int/publications>
- Reference Materials:
  - OpenStreetMap Map Features: <https://wiki.openstreetmap.org/wiki/Map_features>
