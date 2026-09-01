---
title: "Evaluasi Chatbot"
date:
  created: 2026-09-01
authors:
  - rendy
categories:
  - AI
tags: [ai, chatbot]
---

Menurut saya evaluasi merupakan kunci dari coding dengan menggunakan AI. Jika kita bisa menentukan apa itu bagus secara jelas, maka AI akan melakukan apa yang perlu dilakukan untuk mencapai definisi bagus tersebut. Begitu juga dengan pengembangan AI sendiri, dalam hal ini chatbot. Dalam 2 hari terakhir saya menghabiskan waktu untuk membangun evaluasi chatbot dan berikut beberapa hal yang saya pelajari.

<!-- more -->

Pelajaran pertama adalah tentang definisi bagus itu sendiri. Evaluasi fitur non-AI biasanya lebih jelas definisi bagusnya. Misal, fitur login, berhasil ketika username dan password yang benar berhasil login, sedangkan yang salah gagal login. Namun fitur AI seperti chatbot, ketika chatbot menjawab sebuah kalimat, takaran bagusnya itu apa? Apakah memuaskan pengguna? Atau kebenaran dari isinya? Atau kesesuaian dengan referensi yang diberikan? Selain perkara menentukan definisi bagus, evaluasi chatbot menjadi lebih sulit karena kemungkinan respon yang diberikan bisa sangat beragam. Apakah jika kalimatnya tidak sesuai, maka jadi salah? Tentu tidak, selama maknanya masih sesuai, maka penggunaan sinonim atau perubahan kalimat aktif menjadi pasif tidak menjadi masalah.

Tambahan lagi, definisi bagusnya perlu melihat masalah apa yang ditangani oleh AI. Misal kita punya chatbot untuk menangani komplain, maka definisi bagus perlu termasuk empati terhadap pengguna, sehingga pengguna merasa nyaman dan merasa didengarkan masalahnya. Ini penting untuk kepuasan pengguna dalam melaporkan komplain untuk ditindaklanjuti.

Definisi bagus ini, perlu dimasukkan sebagai rubrik. Apa saja hal yang dianggap bagus, didaftarkan lalu dijadikan sebagai bahan untuk evaluasi chatbot.

Pelajaran kedua adalah tentang proses evaluasi itu sendiri. Untuk menilai keluaran berdasarkan rubric, diperlukan AI LLM lagi untuk menilai; ini sering disebut dengan istilah _LLM Judge_. Saat blog ini ditulis, ada dua perkakas yang masuk ke radar saya: DeepEval dan Ragas. Pada dasarnya, keduanya memiliki mekanisme yang mirip dan mendukung penilaian dengan LLM Judge. Catatan, saat blog ini ditulis, Ragas sudah tidak aktif selama berbulan-bulan sedangkan DeepEval masih aktif dikembangkan. Catatan lainnya, Ragas memiliki opini kuat bahwa chatbot hanya bisa dinilai dengan binary 0-1 saja, antara berhasil / tidak. Ini tergantung selera, saya sendiri masih prefer nilai kontinyu, untuk tahu chatbotnya seberapa dekat ke sempurna.

Pelajaran ketiga tentang sifat LLM sendiri yang probabilistik dan tidak pasti. Karena responsenya bisa berubah-rubah, kadang benar kadang tidak, kita perlu tahu dia seberapa sering benar. Sehingga untuk skenario testing, perlu dibuatkan untuk mengulang tes yang sama setidaknya tiga kali utk tahu apakah responsenya konsisten benar atau tidak.

Pelajaran keempat, adalah sifat chatbot itu sendiri yang mendukung diskusi dua arah dalam sebuah sesi. Artinya, evaluasinya perlu melakukan skenario tes yang sering disebut _multiturn conversation_. Ini artinya, perlu AI bot yang berpura-pura menjadi pengguna (misalkan komplain), untuk mengevaluasi chatbot. Jadi, AI ngobrol dengan AI untuk evaluasi. Ini penting karena sifat fleksibel dari diskusi yang mungkin terjadi dengan chatbot sehingga skenario yang sudah pakem pertanyaannya jadi terlalu fragile atau rentan error padahal sebenarnya masih mencapai tujuan yang sama. Misal, ketika orang memesan produk tertentu, bisa saja dia mulai dari memesan dulu, baru memberikan kontak dia diakhir. Tapi mungkin saja sebaliknya. Fleksibilitas ini yang menyebabkan perlu AI untuk mengetes AI.

Pelajaran terakhir yang mau saya ceritakan adalah mengetes AI dengan menggunakan skenario yang dibuat oleh AI. Ini terdengar mudah dan pintar, tapi pada praktiknya ternyata kualitas test case dari AI perlu diuji kembali. Begitu juga kualitas rubrik yang digunakan. Jadi saat saya dapat skor akhir dari evaluasi, misalkan saja nilainya dapat 70 dari 100, saya pastikan kembali, apakah nilai buruk ini karena 1) test casenya yang kurang tepat, 2) rubriknya yang salah atau ambigu, 3) memang chatbotnya yang bermasalah. Kita perlu melakukan beberapa iterasi hingga poin 1 dan 2 minim, sehingga kita bisa fokus ke masalah nyata dari chatbot itu sendiri (poin 3).

Rasanya masih banyak yang ingin saya bahas, seperti metrics penilaian untuk RAG, jenis rubrik dan penilaian (binary, ordinal, float), dan hal-hal lainnya yang lebih teknis; tapi itu saja dulu deh.
