---
title: "Panduan Lengkap Vibe Coding dengan AI Studio"
date:
  created: 2026-05-15
authors:
  - rendy
categories:
  - Tutorial
tags: [vibe coding, ai studio, gemini, prompt engineering, ai, prototyping]
---

*Vibe coding* telah menjadi istilah umum yang sering diartikan sebagai koding dengan menggunakan AI. Istilah ini pertama disebutkan oleh Karpathy dalam post-nya di platform X, *"fully give in to the vibes, embrace exponentials, and forget that the code even exists"* [1]. Tafsiran saya terhadap kalimat ini adalah, seseorang yang melakukan *vibe coding* akan tenggelam dalam alur kreativitas – tenggelam dalam zona mewujudkan idenya dari bentuk konseptual menjadi bentuk konkret (aplikasi atau situs web) – tanpa memikirkan teknikalitas dari perwujudan bentuk konkret tersebut (kodenya). Orang yang *vibing*, sibuk berkreasi dan memikirkan ide-ide yang implementasinya didelegasikan kepada AI. Jadi, kalau kamu masih ngoding dibantu AI, menurut saya itu bukan *vibe coding*, itu koding yang dibantu AI (*AI-assisted coding*).

<!-- more -->

Nah menurut saya, *vibe coding* dalam definisi tersebut – tidak memikirkan hal teknis sama sekali – sangat menitikberatkan pada keajaiban AI dalam membuat kode yang bagus dan berkualitas. Jika AI tidak mampu membuat kode yang bekerja dengan baik (misal banyak bugs atau fiturnya bermasalah), maka seseorang tersebut akan terpaksa lepas dari zona *vibing*, karena ia perlu melihat sisi teknis dari implementasi idenya. Artinya, AI-nya harus sudah sangat mumpuni dulu untuk sampai tingkat *vibe coding*.

Saat ini, kematangan AI untuk mendukung *vibe coding* masih sangat beragam. Umumnya, AI saat ini belum mampu memberikan produk final yang matang, masih perlu diberikan banyak arahan untuk membuat kode dan aplikasi yang berkualitas. Maka dari itu, *vibe coding* sering diidentikkan dengan pembuatan prototipe atau purwarupa – model awal untuk mengetes fungsionalitas – bukan produk akhir yang memiliki reliabilitas tinggi.

Dengan menjamurnya *vibe coding*, rasa penasaran pun muncul dari pelbagai kalangan; teknis dan non-teknis. Bagaimana sih rasanya membuat aplikasi? Saya punya ide nih, semudah itu kah buatnya? Bikinnya pakai apa? Biar bagus hasilnya caranya bagaimana? Unggahan ini mencoba menjawab pertanyaan-pertanyaan tersebut dengan menggunakan salah satu perkakas *vibe coding* yang tersedia secara gratis di luar sana, yaitu AI Studio ([aistudio.google.com](https://aistudio.google.com)).

## Apa itu AI Studio?

AI Studio ([aistudio.google.com](https://aistudio.google.com)) merupakan perkakas *vibe coding* yang disediakan oleh Google. AI Studio menyediakan antarmuka yang sangat mudah digunakan untuk orang non-teknis. Untuk memulai, kamu hanya perlu untuk mengunjungi situsnya, login dengan akun Google, lalu mulai menaruh *prompt* dalam bentuk kalimat (*prompt* adalah istilah yang merujuk kepada perintah yang kita berikan kepada AI). Setelah itu kamu bisa menunggu hasil aplikasinya keluar dalam beberapa menit.

![Halaman utama AI Studio](/assets/images/20260515_vibecoding_1.png)

Kamu mungkin pernah mencoba perkakas *vibe coding* lain seperti Lovable atau Replit. Bedanya apa AI Studio ini?

- AI Studio tier gratisnya lebih leluasa. Misalnya, saat mencoba Replit, saya kehabisan kuota sebelum bisa membuat satu fitur.
- AI Studio mewajibkan aplikasi yang dibuat untuk menggunakan AI, lebih spesifik lagi menggunakan Gemini (model AI yang disediakan Google). Jadi kalau kamu hendak membuat aplikasi yang tidak ada fitur AI sama sekali, kamu tidak bisa menggunakan AI Studio.
- AI Studio terintegrasi secara matang di ekosistem Google. Selain Gemini, kalian bisa menggunakan fitur lain dengan mudah seperti fitur login dengan akun Google (SSO atau Single Sign-On), dan juga *deployment* ke Firebase dan Google Cloud untuk rilis masal / penggunaan skala besar.

Kamu yang berlatar belakang teknis seperti pembangun perangkat lunak, mungkin pernah mencoba AI-assisted coding IDE seperti Anti Gravity, Cursor, atau Windsurf. Bedanya, AI Studio lebih bersahabat untuk orang non-teknis. Halaman utamanya hanya chatbox dan preview dari aplikasi yang dibangun. Opsi teknis seperti melihat kode, bukan berada di halaman utama. Selain itu, AI Studio berjalan di platform Google dan kamu hanya bisa mengaksesnya lewat browser. Berbeda dengan AI IDE yang berjalan di komputer lokal kamu dan bisa menggunakan perkakas yang tersedia di terminal kamu.

## Tips Vibe Coding di AI Studio

Tips *vibe coding* dari saya hanya ada dua, dan ini berlaku tidak hanya di AI Studio saja, namun juga di platform lain:

1. Buat requirement dengan sangat jelas.
2. Bekerja dalam beberapa fase.

### Buat *requirement* dengan sangat jelas

*Requirement* adalah daftar fitur yang kita ingin implementasikan dalam aplikasi yang sedang kita bangun. Prinsip *requirement* yang jelas itu penting, karena tanpa requirement yang jelas, aplikasi yang dibangun sangat mungkin tidak sesuai dengan apa yang kita pikirkan. Perintah yang tidak jelas menghasilkan hasil yang tidak memuaskan, dan membuang-buang kuota token AI.

Contoh requirement yang tidak jelas adalah menggunakan satu kalimat sederhana dan berharap AI bisa memikirkan detailnya. Contohnya seperti gambar di bawah ini. AI sangat mungkin menginterpretasikan perintah tersebut menjadi sesuatu yang sangat berbeda dari apa yang kita bayangkan.

Contoh requirement yang singkat padat dan tidak jelas:

> *Buatkan aplikasi pencatat keuangan yang dapat mencatat pemasukan dan pengeluaran.*

Requirement yang tidak jelas dan ambigu bukan prompt yang baik. Misalnya contoh di atas, tidak jelas inputnya apa, apakah kalimat atau foto. Selain itu apa yang ingin dicatat tidak jelas apa saja. Bandingkan dengan contoh di bawah ini yang lebih jelas:

> *Buatkan aplikasi pencatat keuangan yang dapat mencatat pemasukan dan pengeluaran. Saya akan memberikan kalimat singkat, contoh "mi ayam 5000", lalu AI akan mencatatkan waktu, kategori, deskripsi, dan jumlah. Selain itu AI akan memberikan ringkasan pengeluaran dari awal bulan dan budgetnya berapa, hingga sekarang supaya saya tidak lebih dari budget.*

Untuk mendapatkan requirement yang jelas, kamu bisa menggunakan Gemini App di [gemini.google.com](https://gemini.google.com) untuk brainstorming. Tanyakan saja "saya mau buat aplikasi pencatatan keuangan, coba buatkan requirementnya yang lengkap", lalu kamu review apakah requirement yang diberikan cukup merepresentasikan idemu atau kamu ingin mengubahnya. Lakukan dalam beberapa iterasi sampai kamu merasa sudah jelas dan tidak ambigu.

Requirement yang kamu buat sebaiknya berisi hal-hal sebagai berikut:

1. **Tujuan**: apa tujuan akhir penggunaan yang kamu inginkan. Misal untuk melacak keuangan kamu ingin tidak melebih budget pengeluaranmu.
2. **Daftar fitur**: apa saja fitur yang kamu inginkan. Misal pencatan dan laporan pengeluaran.
3. **Detail teknis**: jika kamu orang teknis, kamu bisa sebutkan jika kamu ingin menggunakan framework atau library tertentu.

### Bekerja dalam Beberapa Fase

Saat ini AI masih memiliki banyak keterbatasan seperti halusinasi, batas konteks, dan keterbatasan AI untuk membuat hal yang kompleks. Apalagi jika kamu menggunakan AI yang cenderung cepat dan murah. Misal Gemini, ada Flash, Pro, dan Thinking. Flash cenderung cepat tapi cocok untuk tugas yang tidak begitu kompleks.

Untuk mencegah masalah dalam implementasi aplikasi, teknik yang kamu bisa lakukan adalah membagi pengerjaan aplikasi menjadi beberapa fase. Semakin kecil lingkup kerja masing-masing fase, semakin besar kemungkinan berhasilnya. Semakin besar kemungkinan berhasilnya, semakin kamu hemat token dan waktu. Usahakan sekecil mungkin sampai kamu bisa menguji apakah fitur itu sudah memuaskan atau belum.

Dalam memikirkan pemecahan fase untuk mengimplementasi semua requirement yang kamu miliki, kamu bisa menggunakan AI untuk berdiskusi tentang hal ini. Gunakan prompt seperti ini "Pecah requirement yang sudah kita diskusikan menjadi fase-fase implementasi, usahakan sekecil mungkin. Bagi berdasarkan prioritas. Pastikan setiap fase ada fitur yang bisa diuji. Tulis prompt untuk setiap fasenya." Jika kamu tidak puas dengan fase dan urutannya, minta AI untuk perbaiki. Setelah kamu mendapatkan fase-fase yang kamu inginkan, copy-paste prompt per fase untuk AI implementasi, lalu tunggu sampai selesai, dan lakukan uji terhadap fase tersebut.

Misalkan, untuk contoh kasus pencatatan keuangan, fase paling awal yang paling mudah dicapai adalah pencatatan pengeluarannya saja. Asalkan data yang kamu input masuk ke dalam basis data dan bisa dimunculkan, itu sudah cukup sebagai fase awal. Fase awal tersebut juga mudah diuji, kamu berikan input lalu kamu tampilkan dalam bentuk tabel di dalam sebuah laman.

## Tahapan Vibe Coding dengan AI Studio

AI Studio memiliki tagline *"The fastest path from prompt to prototype to production with Gemini"*, artinya AI Studio memiliki visi tidak hanya untuk membuat purwarupa, tapi bahkan sampai deployment ke production. Yang dimaksud dengan *production* adalah siap untuk digunakan secara massal.

Tahapan *vibe coding* dengan AI Studio ada tiga:

1. **Prompt**: sempurnakan prompt dalam bentuk requirement seperti yang telah kita bahas sebeumnya.
2. **Build**: copy-paste prompt per fase satu per satu. Pahami fitur-fitur AI Studio untuk mendukungmu ditahap ini (lihat di bagian "Fitur-Fitur AI Studio").
3. **Ship**: setelah semua fitur selesai dibangun dan diuji, deploy ke Firebase dan Google Cloud untuk penggunaan secara massal.

![Tahapan Prompt, Build, Ship di AI Studio](/assets/images/20260515_vibecoding_2.png)

## Fitur-Fitur dan Pengaturan AI Studio

Dalam tahap "*Build!*" kamu akan mengimplementasikan fitur-fitur dalam requirement aplikasi kamu satu per satu untuk setiap fase yang sudah kamu rencanakan. Saat mengimplementasi fitur di masing-masing fase, penting untuk kamu tahu fitur dan pengaturan apa saja yang bisa kamu gunakan.

### Gallery, Remix dan Share

Saat kamu masuk ke halaman utama AI Studio, kamu akan menemukan Gallery dan Apps di panel sebelah kiri. Apps berisi semua aplikasi yang kamu bangun, sedangkan Gallery berisi banyak sekali aplikasi yang dibangun oleh orang lain dan yang lebih menarik, kamu bisa melanjutkan aplikasi tersebut untuk kamu kustomisasi lebih lanjut dengan menggunakan fitur Remix.

![Gallery dan Apps di AI Studio](/assets/images/20260515_vibecoding_3.png)

Fitur Share menurut saya fitur yang sangat jarang ada di *vibe coding* platform. Dengan adanya fitur share, kamu bisa membagi akses ke aplikasi kamu ke orang-orang terdekatmu untuk melakukan pengujian, sehingga kamu bisa memastikan apakah aplikasi yang kamu bangun akan sukses di pasar. Kamu bisa membagikan akses ke email tertentu atau berbagi ke publik dengan memberikan link. Saya tidak menyarankan kamu membagikan aplikasi secara publik karena bisa disalahgunakan sehingga kuota kamu habis atau kamu harus membayar tagihan besar karena banyak orang yang akses secara tidak bertanggungjawab. Selalu bagikan ke email spesifik supaya aman. Selain kamu mesti tahu, bahwa aplikasi yang kamu bagikan bisa di-Remix oleh orang yang kamu undang.

![Fitur Share di AI Studio](/assets/images/20260515_vibecoding_4.png)

### Pengaturan di AI Studio

Ada beberapa hal yang bisa kamu kustomisasi sesuai dengan kebutuhanmu. Klik tombol gear atau pengaturan di kanan atas layar.

1. **Model**: kamu bisa memilih model yang kamu gunakan
    1. **Flash**: hemat kuota dan cepat, cocok untuk tugas sederhana seperti perbaikan tampilan.
    2. **Pro**: cocok untuk tugas yang kompleks, namun hati-hati karena lebih boros kuota.
2. **System instruction**: kamu bisa meminta AI untuk selalu melaksanakan instruksi di sini tanpa kamu harus memberitahukannya berulang-ulang setiap chat. Saya sarankan kamu memasukkan best practices teknis di sini, misalnya kamu bisa minta AI untuk menuliskan dokumentasi kodenya.
3. **Mode pembayaran**:
    1. **Free**: gratis
    2. **Google AI**: kamu menggunakan subscription paket Google One kamu, seperti Pro. Ini akan menggunakan kuota AI kamu dari sana.
    3. **Gemini API**: menggunakan API sehingga Pay per Use. Ketika menggunakan opsi ini, kamu perlu menghubungkan AI Studio dengan Google Cloud yang memiliki billing, sehingga penggunaan AI-nya akan ditagihkan di Google Cloud sesuai dengan penggunaan Gemini API kamu di AI Studio.

![Pengaturan Model, System Instruction, dan Mode Pembayaran](/assets/images/20260515_vibecoding_5.png)

4. **Versions**: setiap prompt yang kamu perintahkan ke AI akan mengubah kode dan menambahkan versi di sini. Sehingga jika kamu tidak suka dengan apa yang dilakukan AI dan ingin kembali ke versi sebelumnya, kamu bisa mencari versi tersebut di sini dan menekan tombol "Restore Version".

![Daftar versi dan Restore Version](/assets/images/20260515_vibecoding_6.png)

Berikut contoh "System Instruction" disadur dari [2]. Jangan lupa bahwa system instruction akan masuk ke dalam penggunaan token kalian.

```
# Coding/documenting guidelines
* Create a file per feature or related features, split as much as possible in different files;
* add docstrings to all functions to explain what they do;
* start each file with a long comment explaining in detail what the feature is about and the different use cases;
* maintain a `Design.md` document at the root of the app that documents all the features of the app;
* log as info all function calls (with their parameters) and log all genai calls with all their parameters (model used, prompt, config) and their outputs, just strip inline data;
* group all configurable items (like model names) in a centralized file;
* always create a way to test the scripts without altering the data;
```

### Preview, Code, dan Github

Anda bisa skip bagian ini jika Anda bukan orang teknis. Secara default, AI Studio akan memberikan preview aplikasimu, sehingga kamu dapat menguji aplikasimu setiap AI selesai mengimplementasikan prompt yang kamu berikan. Namun jika kamu juga seorang yang mengerti teknis, kamu dapat mengecek kode yang dibuat oleh AI. Ada beberapa hal yang menarik terkait kode yang dibuat oleh AI Studio: (1) AI Studio by default menggunakan React, (2) AI Studio akan membuat backend hanya jika diperlukan, (3) pemanggilan AI wajib dilakukan dari front end entah kenapa. Kamu bisa menghubungkan kode ini dengan Github repository. Namun saat saya menulis ini, integrasi dengan Github sedang bermasalah dan tidak dapat dilakukan.

![Preview, Code, dan integrasi Github](/assets/images/20260515_vibecoding_7.png)

### Publikasikan Aplikasimu

Ketika kamu menekan tombol Publish di kanan atas, kamu akan membuat aplikasimu tersedia di internet secara publik. Namun history chat beserta kode kamu akan tetap rahasia dan tidak terlihat. Aplikasi kamu akan menggunakan infrastruktur Google Cloud serta Firebase. Oleh karena itu, saat mempublikasikan aplikasimu, kamu akan diminta memilih Google Cloud project untuk menyimpan aplikasimu. Project ini perlu diaktifkan billingnya sehingga dapat dilakukan penagihan sesuai penggunaanmu.

![Memilih Google Cloud project saat publish](/assets/images/20260515_vibecoding_8.png)

Kamu bisa juga membatasi pengeluaran API Gemini kamu dengan menggunakan fitur "Set Spend Cap". Namun saya lihat ini hanya membatasi pengeluaran terhadap API Gemini, namun tidak terhadap resource cloud kamu, jadi tetap hati-hati ya.

![Fitur Set Spend Cap](/assets/images/20260515_vibecoding_9.png)

Sebelum mempublikasikan aplikasi kamu, pastikan aplikasi kamu sudah terlindung dengan login. Minta AI untuk membuat fitur login "Tambahkan fitur login dengan sso". Dengan ini, penggunamu terbatas oleh pengguna valid yang melakukan login dengan akun Google mereka. Ini mengamankan aplikasimu dari penggunaan yang tidak bertanggungjawab.

![Menambahkan fitur login SSO](/assets/images/20260515_vibecoding_10.png)

## Masalah dan Cara Pemecahannya

AI Studio bukan tanpa kekurangan. Ada beberapa hal yang masih bisa diperbaiki, antara lain:

1. **Kadang stuck**. Stuck saat mengerjakan tugas, atau stuck saat ada bug. Ada beberapa cara yang bisa kamu lakukan: (1) naikkan model dari Flash ke Pro, (2) mundur ke versi sebelumnya, (3) remix ke project baru.
2. **Kadang fiturnya tidak berjalan**. Saat saya sedang menggunakan Google AI Studio ini, saya selalu gagal untuk menghubungkan dengan Github. Ini saya tidak ada solusi apapun sejauh ini.

## Referensi

[1] [https://x.com/karpathy/status/1886192184808149383?lang=en](https://x.com/karpathy/status/1886192184808149383?lang=en)

[2] [https://dev.to/googleai/vibe-coding-in-google-ai-studio-my-tips-to-prompt-better-and-create-amazing-apps-3kcp](https://dev.to/googleai/vibe-coding-in-google-ai-studio-my-tips-to-prompt-better-and-create-amazing-apps-3kcp)
