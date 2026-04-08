<h1> Spatial vs Airbnb Listing Bangkok Performance Analysis </h1>

## 1. Project Overview
Data set ini merupakan kumpulan listing Airbnb di Bangkok dengan review dari 15/12/2012 hingga 28/12/2022. Performa listing bisa dilihat dari beberapa faktor seperti harga, jarak listing ke BTS/pusat sistem transit, jarak listing ke pusat wisata, berapa banyak review, review per bulan, etc. Dari faktor-faktor yang ada, stakeholder ingin melihat ***"Bagaimana faktor spatial (jarak ke pusat kota, akses ke transportasi umum, dan destinasi wisata) dan lokasi mempengaruhi performa listing?"***.

Untuk mengetahui bagaimana faktor spatial dan lokasi mempengaruhi performa listing, berikut merupakan pendekatan analitis yang akan dilakukan:
1. Analisis performa listing berdasarkan zona jarak ke pusat kota
1. Analisis performa listing berdasarkan akses ke BTS (Bangkok Transit System)
1. Analisis performa listing berdasarkan zona jarak ke destinasi wisata dan bandara
1. Analisis korelasi - Spatial vs Performa
    - Bagaimana jarak listing ke landmarks mempengaruhi performa listing (harga, review/month, availability, etc)

## 2. Data Sources
- [data/raw](link) - Airbnb Listings Bangkok 2012-2022

## 3. Technologies Used
- Programming Language: Python (e.g., Pandas, NumPy)
- Visualization: Matplotlib, Seaborn, Folium
- Interactive Dashboard: Tableau
- Version Control: Git
- Others: Jupyter Notebook

## 4. Project Structure

```
├── README.md          <- The top-level README for developers using this project.
|
├── data
│   ├── raw            <- Data from third party sources.
│   └── cleaned        <- The data that has been cleaned.
│
├── notebooks          <- Jupyter notebooks. Naming convention is a number (for ordering),
│                         the creator's initials, and a short `-` delimited description, e.g.
│                         `1.0-jqp-initial-data-exploration`.
│
├── reports            <- Generated analysis as PowerPoint, PDF, LaTeX, etc.
|   ├── slide          <- Generated PowerPoint
│   └── figures        <- Generated graphics and figures to be used in reporting
│
├── requirements.txt   <- The requirements file for reproducing the analysis environment, e.g.
│                         generated with `pip freeze > requirements.txt`
│
└── src                <- Source code for use in this project.

```

## 5. Summary of Finding
### 5.1 Business Insight
1. **Lokasi sangat menentukan harga & performa**
    - Semakin dekat ke pusat kota --> harga median lebih tinggi dan frekuensi booking (reviews/month) lebih tinggi
    - Ada gradien jelas: pusat kota = premium, pinggiran = lebih murah & demand lebih rendah
1. **Akses transportasi (BTS) = faktor paling kuat**
    - Properti <1 km dari BTS:
        - Harga bisa berkali lipat lebih tinggi
        - Lebih sering dipesan
    - BTS proximity = prediktor spatial paling kuat terhadap harga & demand
1. **Korelasi kedekatan ke bandara dan tempat wisata tidak terlalu kuat**
    - Bandara: hampir tidak berpengaruh
    - Wisata (Wat Pho, Khao San): hanya korelasi lemah–moderat
        - Artinya: wisata ≠ driver utama, mobilitas (transport) lebih penting
1. **Review & aktivitas listing**
    - Listing dengan review:
        - Lebih “hidup” --> indikasi demand
    - Listing tanpa review:
        - Potensi underperform / baru / tidak kompetitif
### 5.2 Actionable Recommendation
1. **Host (Pemilik Properti)**
    1. Prioritaskan lokasi dekat BTS
        - Jika sudah dekat --> gunakan sebagai selling point utama
        - Jika tidak --> kompensasi dengan harga atau fasilitas
    1. Strategi pricing berbasis lokasi
        - Menetapkan harga di atas median pasar untuk listing di zona <1 km
        - Menonjolkan value/experience (ruang lebih luas, fasilitas tambahan, desain, view, dll) untuk listing >4 km alih-alih bersaing harga dengan zona pusat
    1. Optimasi listing
        - Mencantumkan jarak atau waktu tempuh actual ke BTS terdekat
        - Gunakan diskon early booking atau promo first guest untuk listing yang jauh dari pusat kota dan BTS
    1. Segmentasi pasar
        - Short stay (1–7 hari) --> wisatawan
        - Long stay --> pekerja remote / ekspatriat

1. **Guest/Customer (Traveler/Tourist/Digital Nomads)**
    1. Pilih dekat BTS --> hemat waktu & biaya transport
    1. Jangan hanya fokus ke tempat wisata
    1. Pertimbangkan:
        - harga vs akses transport (trade-off utama)

1. **Airbnb (Platform)**
    1. Ranking algorithm berbasis BTS proximity
        - Boost listing dekat transportasi publik
    1. Tambah fitur product
        - Mengintegrasikan skor konektivitas transportasi (BTS, MRT, bus) sebagai filter pencarian resmi
        - Meningkatkan relevansi hasil dan membantu wisatawan yang memprioritaskan mobilitas
    1. Smart pricing recommendation (Host tools)
        - Mengembangkan pricing assistant yang membandingkan harga listing baru dengan median zona spasialnya (0–2 km, 2–5 km, dll.) dan akses BTS
        - Memberikan rekomendasi harga optimal
    1. Highlight “transport convenience”
        - Tambahkan label:
            - “Near BTS”
            - “Easy commute”
    1. Aktivasi listing pasif
        - Target listing tanpa review:
            - campaign onboarding
            - insentif first booking

1. **Investor/Developer**
    1. Fokus investasi dekat BTS
        - Faktor paling impactful
    1. Strategi yield:
        - Pusat kota --> capital gain + high nightly rate
        - Pinggiran --> occupancy play
    1. Diversifikasi:
        - Short stay + long stay portfolio

## 6. Contact
- Name: Muhammad Ilman Mughni
- Email: ilmanmughni29@gmail.com
- Linkedin: https://www.linkedin.com/in/milmanmughni/
