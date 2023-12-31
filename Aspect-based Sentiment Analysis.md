Aspect-Based Sentiment Analysis (ABSA) adalah sub-bidang dari analisis sentimen yang fokus pada identifikasi sentimen terkait dengan aspek-aspek tertentu dalam suatu teks. Metode-metode yang digunakan dalam ABSA dapat dikategorikan menjadi beberapa jenis: Metode Berbasis Aturan (_rule-based_), Metode Berbasis Pembelajaran Mesin (_machine learning_), Metode Berbasis _Deep Learning_, dan Metode Hibrida.

1. **Metode Berbasis Aturan** menggunakan aturan dan kamus sentimen yang telah ditentukan untuk mengidentifikasi aspek dan menilai sentimen. Beberapa karya ilmiah dalam kategori ini mencakup riset oleh [Poria et al. (2016)](https://sentic.net/sarcasm-detection-with-deep-convolutional-neural-networks.pdf) yang melihat ke dalam tweets sarkastik dan [Ghadery et al. (2019)](https://arxiv.org/abs/1812.03361) yang menggunakan pendekatan berbasis pengelompokan (_clustering_) dan _soft cosine similarity measure_ untuk mendeteksi kategori aspek.

2. **Metode Berbasis Pembelajaran Mesin** melibatkan penggunaan algoritma klasifikasi seperti SVM, Naive Bayes, dan Decision Trees. Ini dapat dibagi lagi menjadi:
    - **Feature-Based Methods**: Metode ini menggunakan fitur seperti bag-of-words dan n-grams. Contohnya adalah karya oleh [Pontiki et al. (2016)](https://aclanthology.org/S16-1002/) dan [Ma et al. (2017)](https://arxiv.org/abs/1709.00893).
    - **Embedding-Based Methods**: Metode ini menggunakan embedding kata seperti Word2Vec. Karya oleh [He et al. (2018)](https://aclanthology.org/P18-2092/) dan [Zhou et al. (2016)](https://aclanthology.org/D16-1058/) adalah contoh dari pendekatan ini.

3. **Metode Berbasis Deep Learning** menggunakan arsitektur jaringan saraf yang lebih kompleks seperti CNN, RNN, LSTM, GRU, dan Transformers:
    - **CNN**: [Dos Santos & Gatti (2014)](https://aclanthology.org/C14-1008/) dan [Kim (2014)](https://aclanthology.org/D14-1181/) menggunakan CNN untuk analisis sentimen teks singkat. CNN dapat digunakan untuk mengidentifikasi pola lokal dalam data teks dan efektif dalam mengambil fitur penting dari data.
    - **RNN dan Variannya**: [Tang et al. (2015)](https://aclanthology.org/D15-1167/) dan [Liu et al. (2016)](https://www.ijcai.org/Proceedings/16/Papers/408.pdf) mengeksplorasi penggunaan RNN dan LSTM untuk klasifikasi teks. RNN dan variannya seperti Long Short-Term Memory (LSTM) dan Gated Recurrent Units (GRU) sangat efektif dalam mengolah data urutan seperti teks.
    - **Transformers dan Model Berbasis Attention**: [Sun et al. (2019)](https://aclanthology.org/N19-1035/) dan [Xu et al. (2019)](https://aclanthology.org/N19-1242/) memanfaatkan BERT untuk ABSA. Model seperti BERT (Bidirectional Encoder Representations from Transformers) dan GPT (Generative Pretrained Transformer) telah menunjukkan hasil yang sangat baik dalam berbagai tugas NLP, termasuk ABSA.
     
        Lebih lanjut lagi tentang metode ini:
        1. [Singh et al. (2022)](https://doi.org/10.1002/cpe.7589) mengusulkan pendekatan untuk klasifikasi sentimen lintas domain menggunakan DeBERTa (_Decoding-enhanced BERT_), yaitu BERT yang ditingkatkan dengan mekanisme perhatian yang terpisah (_disentangled attention_). Model ini memanfaatkan embedding kalimat dan aspek untuk mengekstrak informasi dari dokumen teks dan menggunakan mekanisme perhatian terpisah untuk mengkode setiap kata menjadi dua vektor (konten dan posisi). Hasil eksperimen menunjukkan bahwa model DeBERTa yang telah disesuaikan mengungguli metode klasifikasi sentimen lintas domain yang ada.
        
        2. [Wang et al. (2020)](https://doi.org/10.1609/aaai.v34i10.7248) menggabungkan fine-tuning BERT dengan pendekatan berbasis fitur untuk ekstraksi aspek dalam ulasan. Penelitian ini menunjukkan bahwa fine-tuning BERT secara langsung dengan lapisan spesifik tugas dapat membatasi kinerja, dan oleh karena itu, penulis menggabungkan pendekatan fine-tuning dengan pendekatan berbasis fitur untuk ekstraksi aspek.
        
        3. [Yang et al. (2022)](https://doi.org/10.1016/j.ipm.2022.103038) kemungkinan membahas model transformer yang dirancang untuk analisis sentimen berbasis aspek yang dapat menangani beberapa modalitas data masukan. Meskipun abstrak tidak disediakan, judul menunjukkan fokus pada analisis sentimen berbasis aspek multimodal.
        
        4. [Yu et al. (2023)](https://doi.org/10.1109/TAFFC.2022.3171091) memperkenalkan model _Hierarchical Interactive Multimodal Transformer_ (HIMT) untuk analisis sentimen berbasis aspek multimodal (ABMSA). Model ini mengekstrak fitur penting dengan konsep semantik dari gambar melalui deteksi objek dan menggunakan modul interaksi hierarkis untuk memodelkan interaksi antara teks-aspek dan gambar-aspek, diikuti oleh interaksi teks-gambar.
        
        5. [Lebmeier et al. (2022)](https://doi.org/10.1007/978-3-031-26390-3_31) mengeksplorasi reproduktivitas dan pelaporan ketidakpastian dalam analisis sentimen berbasis aspek. Penulis menggunakan berbagai _benchmark dataset_ yang tersedia untuk publik dan memperkenalkan pengaturan terkait pra-pemrosesan, pemisahan latihan/validasi, ukuran kinerja, dan kuantifikasi ketidakpastian (quantification of uncertainty).

    - **Autoencoders**: [Li et al. (2017)](https://aclanthology.org/P18-1087/) dan [Li et al. (2018)](https://arxiv.org/abs/1805.00760) menggunakan autoencoders untuk ekstraksi istilah aspek. Autoencoders dapat digunakan untuk pembelajaran fitur yang tidak diawasi (_unsupervised_) dalam data teks.
  
Tabel komparasi semua Paper yang sudah disebutkan di atas:

| Penulis dan Tahun | Metode Penelitian | Algoritma Deep Learning | Dataset | Kinerja Model |
|-------------------|-------------------|-------------------------|---------|---------------|
| [Poria et al. (2016)](https://sentic.net/sarcasm-detection-with-deep-convolutional-neural-networks.pdf) | Analisis tweets sarkastik menggunakan CNN | CNN | Dataset tweets | Efektif dalam mendeteksi sarkasme |
| [Ghadery et al. (2019)](https://arxiv.org/abs/1812.03361) | Deep learning untuk ekstraksi aspek dan klasifikasi sentimen | CNN, LSTM | Dataset ulasan | Meningkatkan akurasi dalam ekstraksi aspek dan klasifikasi sentimen |
| [Pontiki et al. (2016)](https://aclanthology.org/S16-1002/) | Semeval-2016 task 5 untuk ABSA | - | Dataset Semeval-2016 | Menyediakan benchmark untuk ABSA |
| [Ma et al. (2017)](https://arxiv.org/abs/1709.00893) | Interactive attention networks untuk ABSA | LSTM | Dataset ulasan produk | Memperbaiki akurasi dalam mengidentifikasi sentimen terkait aspek |
| [He et al. (2018)](https://aclanthology.org/P18-2092/) | Memanfaatkan pengetahuan dokumen untuk ABSA | LSTM | Dataset ulasan | Memperbaiki kinerja dalam ABSA |
| [Zhou et al. (2016)](https://aclanthology.org/D16-1058/) | Attention-based LSTM untuk ABSA | LSTM | Dataset ulasan | Efektif dalam menangkap informasi penting terkait aspek |
| [Dos Santos & Gatti (2014)](https://aclanthology.org/C14-1008/) | CNN untuk analisis sentimen teks singkat | CNN | Dataset umum sentimen | Baik dalam analisis sentimen teks singkat |
| [Kim (2014)](https://aclanthology.org/D14-1181/) | CNN untuk klasifikasi kalimat | CNN | Beberapa dataset teks | Efektif dalam klasifikasi teks |
| [Tang et al. (2015)](https://aclanthology.org/D15-1167/) | RNN untuk klasifikasi sentimen dokumen | LSTM | Dataset ulasan | Baik dalam klasifikasi sentimen pada level dokumen |
| [Liu et al. (2016)](https://www.ijcai.org/Proceedings/16/Papers/408.pdf) | RNN dengan pembelajaran multi-tugas | LSTM | Beberapa dataset klasifikasi teks | Efektif dengan pendekatan multi-tugas |
| [Sun et al. (2019)](https://aclanthology.org/N19-1035/) | BERT untuk ABSA dengan kalimat tambahan | BERT | Dataset ulasan | Memperbaiki pemahaman konteks dalam ABSA |
| [Xu et al. (2019)](https://aclanthology.org/N19-1242/) | Post-training BERT untuk ABMSA | BERT | Dataset ulasan | Meningkatkan akurasi dalam ABMSA |
| [Singh et al. (2022)](https://doi.org/10.1002/cpe.7589) | DeBERTa untuk klasifikasi sentimen lintas domain | DeBERTa | - | Peningkatan kinerja dibandingkan metode klasifikasi sentimen lintas domain |
| [Wang et al. (2020)](https://doi.org/10.1609/aaai.v34i10.7248) | Fine-tuning BERT dengan pendekatan berbasis fitur untuk ekstraksi aspek | BERT | - | Penggabungan fine-tuning BERT dengan pendekatan berbasis fitur meningkatkan kinerja |
| [Yang et al. (2022)](https://doi.org/10.1016/j.ipm.2022.103038) | Model transformer untuk ABSA multimodal | Transformer | - | - |
| [Yu et al. (2023)](https://doi.org/10.1109/TAFFC.2022.3171091) | HIMT untuk ABMSA multimodal | Transformer | - | - |
| [Lebmeier et al. (2022)](https://doi.org/10.1007/978-3-031-26390-3_31) | Reproduktivitas dan pelaporan ketidakpastian dalam ABMSA | - | Benchmark dataset publik | Fokus pada pra-pemrosesan, pemisahan latihan/validasi, ukuran kinerja, dan kuantifikasi ketidakpastian |

Catatan: Hyperlink mengarah ke sumber paper atau abstraknya. Untuk informasi lebih detail, silakan merujuk ke sumber asli.
