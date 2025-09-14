[![Review Assignment Due Date](https://classroom.github.com/assets/deadline-readme-button-22041afd0340ce965d47ae6ef1cefeee28c7c493a6346c4f15d667ab976d596c.svg)](https://classroom.github.com/a/tPVgLsdF)
| Name | NRP | Class |
| ---- | --- | ----- |
| Farrel Aqilla Novianto  | 5025241015 | C |

## Task 1

- Flag

  `JARKOM25{Ja0G_Bbbb4ng3t_S1_PYWP9XS2P54HDRMJ5C16W5T343J8EN0xl0vel1q5dd15kiwcil3cmag1webb7_38748655c6ad6e04d90ceea38d04d3a4}`

> a. Berapa banyak packet yang terekam pada file pcapng?

> _a. How many packets are recorded in the pcapng file?_

**Answer:** `9596`

- Filter expression

  `-`

- Explanation

  `Melihat total packets dari capture file properties`

- Output result

  <img width="1007" height="240" alt="image" src="https://github.com/user-attachments/assets/85dcf82d-838a-44c4-ae7c-aa751e0586da" />

<br>
<br>

> b. Ada berapa jenis protocol (total) yang terekam pada traffic?

> _b. How many types of protocol (totals) are recorded in the traffic?_

**Answer:** `12`

- Filter expression

  `-`

- Explanation

  `Melihat total protokol dari protocol hierarchy (menghitung per baris)`

- Output result

  <img width="595" height="312" alt="image" src="https://github.com/user-attachments/assets/1fd998d7-885a-4d99-81dc-5532ab0d6855" />

<br>
<br>

> c. Ada berapa jenis protocol berbasis TCP yang terekam pada traffic?

> _c. How many types of TCP-based applications protocol are recorded in the traffic?_

**Answer:** `8`

- Filter expression

  `-`

- Explanation

  `Melihat total protokol dari protocol hierarchy (menghitung anggota TCP)`

- Output result

  <img width="497" height="178" alt="image" src="https://github.com/user-attachments/assets/e9169562-0601-4777-b588-7b2292156eb3" />

  <br>
  <br>

> d. Ada berapa banyak packet dengan protokol TCP murni yang terekam pada traffic (tanpa data)?

> _d. How many packets with pure TCP protocol are recorded in the traffic (without data)?_

**Answer:** `3223`

- Filter expression

  `tcp && !telnet && !vnc && !hipercontracer && !http && !thrift && !sigcomp && !data`

- Explanation

  `Untuk mencari TCP murni, saya filter hanya untuk TCP (sisanya kita kecualikan) dan tanpa data`

- Output result

  <img width="1918" height="1078" alt="image" src="https://github.com/user-attachments/assets/bd802763-196a-47e0-af44-5561858a4493" />

## Task 2

- Flag

  `JARKOM25{N1c3_0ne_b4nggg_BGMMZUSHLXyuMM13yopsdvmblnaznwffyaobmc3r4t0ps59381054465374417941_898e683a37cfc5267d44d03037eaef29}`

> a. Berapa banyak packet berhasil yang berbasis murni TCP dan memiliki flag [ACK]?

> _a. How many packets succeed that are pure TCP based and have [ACK] flag?_

**Answer:** `3209`

- Filter expression

  `tcp.flags.ack==1 && !telnet && !vnc && !hipercontracer && !http && !thrift && !sigcomp && !data && !tcp.analysis.flags`

- Explanation

  `Untuk mencari TCP murni dan berflag ACK, saya filter hanya untuk TCP (sisanya kita kecualikan) dan tanpa data serta filter flag hanya ACK dan kecualikan paket TCP yang error dengan mengecualikan paket yang memiliki flag aneh`

- Output result

  <img width="1918" height="1078" alt="image" src="https://github.com/user-attachments/assets/c119448f-0152-47be-94e0-28d5f6ca46aa" />

  <br>
  <br>

> b. Berapa banyak packet berhasil yang berbasis murni TCP yang hanya memiliki flag [ACK]?

> _b. How many packets succeed that are pure TCP based and have only [ACK] flag?_

**Answer:** `3172`

- Filter expression

  `tcp.flags==0x010 && !telnet && !vnc && !hipercontracer && !http && !thrift && !sigcomp && !data && !tcp.analysis.flags`

- Explanation

  `Untuk mencari TCP murni dan hanya berflag ACK, saya filter hanya untuk TCP (sisanya kita kecualikan) dan tanpa data serta filter flag hanya ACK yang ditandai dengan nilai heksadesimal 0x010 dan kecualikan paket TCP yang error dengan mengecualikan paket yang memiliki flag aneh`

- Output result

  <img width="1918" height="1078" alt="image" src="https://github.com/user-attachments/assets/aba9f553-fc31-40e3-80be-02aee5933245" />

  <br>
  <br>

> c. Berapa banyak packet berhasil yang berbasis murni TCP dan memiliki flag selain hanya [ACK]?

> _c. How many packets succeed that are pure TCP based and contain flags other than just [ACK] flag?_

**Answer:** `49`

- Filter expression

  `!tcp.flags==0x010 && !telnet && !vnc && !hipercontracer && !http && !thrift && !sigcomp && !data && !tcp.analysis.flags`

- Explanation

  `Untuk mencari TCP murni dan tidak berflag ACK, saya filter hanya untuk TCP (sisanya kita kecualikan) dan tanpa data serta filter flag bukan ACK dengan mengecualikan TCP dengan flag ACK yang ditandai dengan nilai heksadesimal 0x010 dan kecualikan paket TCP yang error dengan mengecualikan paket yang memiliki flag aneh`

- Output result

  <img width="1918" height="1078" alt="image" src="https://github.com/user-attachments/assets/8197867e-9e5b-4aef-ae92-22c12652fa34" />

  <br>
  <br>

## Task 3

- Flag

  `JARKOM25{W0w_Y0uU_h4V33e_d0n3_444_90od_j0bB_LV1IUg0dl1k3yvpal0h782vvpocbdajpff_d3938c13b518c5986db57679bfab38c2}`

> a. Pada port berapa client telnet terbuka?

> _a. In what port is the telnet client open?_

**Answer:** `54184`

- Filter expression

  `telnet`

- Explanation

  `Client telnet terbuka pada port 54184`

- Output result

  <img width="1918" height="1078" alt="image" src="https://github.com/user-attachments/assets/f31fbc81-4a23-4ece-9591-79058f1a2e20" />

  <br>
  <br>

> b. Berapa byte file response yang dikirim dari server?

> _b. How many bytes of the response files are sent from the server?_

**Answer:** `1449`

- Filter expression

  `telnet`

- Explanation

  `IP server telnet adalah 172.16.16.102 karena default port telnet adalah 23. Follow TCP stream salah satu paket telnet dan kita lihat conversation dari server`

- Output result

  <img width="1270" height="995" alt="image" src="https://github.com/user-attachments/assets/ff6ec24e-de1a-436a-8e05-d5f00534a054" />

  <br>
  <br>

> c. Apa username yang digunakan client telnet untuk berhubungan dengan server?

> _c. What telnet client's username is used to connect with the server?_

**Answer:** `jovyan`

- Filter expression

  `telnet`

- Explanation

  `Follow TCP stream salah satu paket telnet dan kita lihat conversation dari client (input keyboard)`

- Output result

  <img width="677" height="142" alt="image" src="https://github.com/user-attachments/assets/06c77f24-af21-469b-95cc-193896a9d870" />

  <br>
  <br>

> d. Apa password client telnet?

> _d. What is the telnet client's password?_

**Answer:** `123`

- Filter expression

  `telnet`

- Explanation

  `Follow TCP stream salah satu paket telnet dan kita lihat conversation dari semuanya`

- Output result

 <img width="103" height="70" alt="image" src="https://github.com/user-attachments/assets/775d3657-7e59-4bd3-984c-b1fea32ea28f" />

  <br>
  <br>

## Task 4

- Flag

  `JARKOM25{G04t__a4n4liz333er_05OHILJB0A5M8GFZLO8Lfr0g27wybtzom360h8sr3ys8653575432_008a3fcfa550d2cc213cfb3f0e3e9663}`

> a. Apa perintah pertama yang ditulis client pada koneksi telnet?

> _a. What is the first command that client wrote on telnet connection?_

**Answer:** `echo`

- Filter expression

  `telnet`

- Explanation

  `Follow TCP stream salah satu paket telnet dan kita lihat conversation dari client (innput keyboard) lalu cari command shell yang pertama kali di input yaitu echo`

- Output result

  <img width="1253" height="685" alt="image" src="https://github.com/user-attachments/assets/27d5cabc-557e-4d2b-99d8-4ea2a2f0cba9" />

  <br>
  <br>

> b. Apa nama file .txt di server (ditulis bersama ekstensinya)?

> _b. What is the name of .txt file on the server (write with the extension)?_

**Answer:** `test.txt`

- Filter expression

  telnet`

- Explanation

  `Follow TCP stream salah satu paket telnet dan kita lihat conversation dari client lalu cari file .txt menggunakan fitur find`

- Output result

  <img width="1270" height="1071" alt="image" src="https://github.com/user-attachments/assets/f2bed63c-ebe0-4f50-872e-cc0cd6f97f1e" />

  <br>
  <br>

> c. Apa kata pertama dari frasa yang dimasukkan client ke dalam file sebelumnya?

> _c. What is the first word that the client inserted into the previous file?_

**Answer:** `Jarkom`

- Filter expression

  `telnet`

- Explanation

  `Follow TCP stream salah satu paket telnet dan kita lihat conversation dari client lalu cari command >> test.txt untuk melihat apa kalimat yang dimasukkan ke dalam file test.txt`

- Output result

  <img width="1278" height="1077" alt="image" src="https://github.com/user-attachments/assets/a5a7bd07-f5b7-4232-9fb1-730ac2e6cd97" />

  <br>
  <br>

## Task 5

- Flag

  `JARKOM25{n4il0ng_m1lk_dr4g000n_VVJSP4ZHHFEAAJYH7D9ANL5AZRJHB8cr0cxz7b5h1ylwfochseidlmb431_f3bbc6393c419f567d5a1157e24fa0d1}`

> a. Berapa banyak packet berbasis HTTP yang terekam pada file pcapng?

> _a. How many HTTP packets are recorded in the pcapng file?_

**Answer:** `298`

- Filter expression

  `http`

- Explanation

  `Filter menggunakan HTTP dan lihat banyak paket dibawah (displayed)`

- Output result

  <img width="1918" height="1078" alt="image" src="https://github.com/user-attachments/assets/34aa2dbb-5f72-4d2d-9c42-767aa0deeb98" />

  <br>
  <br>

> b. Ada berapa HTTP packet yang berupa response?

> _b. How many response HTTP packets are recorded in the traffic?_

**Answer:** `149`

- Filter expression

  `http.response`

- Explanation

  `Filter menggunakan HTTP dan hanya paket yang berupa response, lihat banyak paket dibawah (displayed)`

- Output result

  <img width="1918" height="1078" alt="image" src="https://github.com/user-attachments/assets/be7d682e-95b4-43bb-9a60-7ac80db27b0f" />

  <br>
  <br>

> c. Ada berapa paket berbasis HTTP yang berhasil?

> _c. How many HTTP packets that succeed?_

**Answer:** `296`

- Filter expression

  `http && !tcp.analysis.flags`

- Explanation

  `Filter menggunakan HTTP dan hanya paket yang berhasil dengan mengecualikan anomali TCP, lihat banyak paket dibawah (displayed)`

- Output result

  <img width="1919" height="1079" alt="image" src="https://github.com/user-attachments/assets/b944f94e-e16d-43e6-9611-4312fcc92045" />

  <br>
  <br>

> d. Apa alamat IP dari client HTTP yang tersambung lokal dengan mesin lain?

> _d. What is the client HTTP IP Address in connection with other local machine?_

**Answer:** `172.16.16.101`

- Filter expression

  `http && tcp.host==80`

- Explanation

  `Filter menggunakan HTTP yang memiliki port 80 karena port localhost untuk HTTP bernilai 80, lihat source IP (client)`

- Output result

  <img width="1313" height="267" alt="image" src="https://github.com/user-attachments/assets/e86b3d2f-8bbc-492e-8ee8-c489c3c2abab" />

  <br>
  <br>

## Task 6

- Flag

  `JARKOM25{br0mb44rdin0u_Cr0ccc0c0c0cdi1l10l_1137175225awaesamkgz881e0nsh1n0buVFY7805ND6LS5OD_c6366d487bc89f516d802b32b18f7801}`

> a. Apakah kamu menemukan fake flag? Tuliskan seluruhnya!

> _a. Did you find the fake flag? Write it whole!_

**Answer:** `FakeFlag{JarkomGampang}`

- Filter expression

  `http.request && frame contains ".txt"`

- Explanation

  `Filter menggunakan request HTTP dan saya kepikiran untuk mencari file .txt. Akhirnya saya menemukan file flag.txt yang berisi fake flag lalu follow HTTP stream`

- Output result

  <img width="1086" height="212" alt="Screenshot 2025-09-14 021503" src="https://github.com/user-attachments/assets/e0e4e8ea-7770-4307-bd22-edfae3c440f3" />
  <img width="503" height="338" alt="image" src="https://github.com/user-attachments/assets/8cba59ce-d9b5-47e7-9bac-12d53feecdee" />

  <br>
  <br>

> b. Tuliskan username dan password yang tertulis! (format username:password)

> _b. Write the written username and password! (format username:password)_

**Answer:** `Rey:123`

- Filter expression

  `http.request && frame contains ".txt"`

- Explanation

  `Filter menggunakan request HTTP dan saya kepikiran untuk mencari file .txt. Akhirnya saya menemukan file passwd.txt yang berisi username dan password lalu follow HTTP stream`

- Output result

  <img width="1086" height="212" alt="Screenshot 2025-09-14 021503" src="https://github.com/user-attachments/assets/fdfa1279-f90e-42a1-a3a9-25a99d23df6b" />
  <img width="504" height="359" alt="image" src="https://github.com/user-attachments/assets/bf08880f-32b6-49fa-84d7-67a8b85b91ec" />

  <br>
  <br>

## Task 7

- Flag

  `JARKOM25{tr4l4lel0_tr1lil1_wrj0fa0x1kk3b0s0sCN61M5E96JZRVY4_0e46125f3b8d0cb35eef163cc654f146}`

> Apa nama gambar yang direquest oleh client? (tulis dengan ekstensinya)

> _What is the image that is being requested by the client? (write with its extension)_

**Answer:** `donalbebek.jpg`

- Filter expression

  `http.request && frame contains ".jpg" || frame contains ".png" || frame contains ".jpeg"`

- Explanation

  `Filter menggunakan request HTTP dan saya kepikiran untuk mencari file gambar dengan 3 kemungkinan ekstensi yaitu .jpg, .png, atau .jpeg. Akhirnya saya menemukan file gambar yang ternyata bernama donalbebek.jpg`

- Output result

  <img width="1219" height="269" alt="image" src="https://github.com/user-attachments/assets/c0fded1e-ad63-419b-93d9-e44345801502" />

  <br>
  <br>

## Task 8

- Flag

  `JARKOM25{y0u_4r3_s0_G00d_1n_F0r3nsic_WNY1XEXLB4B4394X7T4OF9RJV9NWGQx45y4n6c2gqmzc6juirs8jnvq4naa1_64e91a31462463a70b9d71c8f9a6b16f}`

> a. Berapa banyak packet berbasis FTP yang terekam pada file pcapng? (with the data)

> _a. How many FTP packets are recorded in the pcapng file? (with the data)_

**Answer:** `81`

- Filter expression

  `ftp || ftp-data`

- Explanation

  `Filter FTP dan datanya (ftp-data)`

- Output result

  <img width="1919" height="1079" alt="image" src="https://github.com/user-attachments/assets/bf8062a8-067b-4515-9b0b-fe2734d3401e" />

  <br>
  <br>

> b. Apa username dan password client di koneksi FTP? (tulis dalam format username:password)

> _b. What is the client's username and password in FTP connection? (write in following format username:password)_

**Answer:** `rey:password123lingangu`

- Filter expression

  `ftp || ftp-data`

- Explanation

  `Filter FTP dan datanya lalu kita follow TCP stream salah satu paket`

- Output result

  <img width="1270" height="241" alt="Screenshot 2025-09-14 022441" src="https://github.com/user-attachments/assets/b0633c4c-582e-49b1-9560-0610a9acde3b" />

  <br>
  <br>

> c. What is the client's command for showing server directory that was sent on request packet?

> _c. Apa command client untuk melihat direktori server yang dikirimkan dalam request packet?_

**Answer:** `LIST`

- Filter expression

  `ftp-data`

- Explanation

  `Filter ftp-data untuk melihat command apa yang akan melihat file didalam direktori. Disini terlihat LIST adalah command yang tepat`

- Output result

  <img width="1293" height="368" alt="image" src="https://github.com/user-attachments/assets/e104bbb1-9349-4c15-b2f2-f07c93d140e0" />

  <br>
  <br>

## Task 9

- Flag

  `JARKOM25{j4rk000000mmm_g4mpp4444n9999999_91744391828i41L4hlli951clci321k0ncolGBM9XVCBEYDWCFV_ec8934c27fcfbfa34b026993cc89ee07}`

> a. Apa alamat IP dari FTP server?

> _a. What is the FTP server IP Address?_

**Answer:** `172.16.16.101`

- Filter expression

  `ftp`

- Explanation

  `Filter FTP dan cari info yang berisi response dan lihat source IP`

- Output result

  <img width="1919" height="1078" alt="image" src="https://github.com/user-attachments/assets/0687ad04-05d3-4461-ac07-d7f183f4ce7f" />

  <br>
  <br>

> b. Berapa banyak file yang ada dalam direktori FTP server?

> _b. How many files are there inside the FTP server directory?_

**Answer:** `7`

- Filter expression

  `ftp-data`

- Explanation

  `Filter ftp-data dan cari info LIST paling pertama dan follow TCP stream untuk menghitung banyak file`

- Output result

  <img width="1278" height="370" alt="image" src="https://github.com/user-attachments/assets/05cb932a-99d0-48c9-94be-d42384e0e3a6" />
  <img width="704" height="229" alt="image" src="https://github.com/user-attachments/assets/f1c02d73-2c64-45cd-bd54-d21322d74ec2" />

  <br>
  <br>

> c. Apa nama dari file yang digunakan dalam page.html? (tulis lengkap namanya beserta ekstensinya dan dipisahkan dengan koma ',')

> _c. What are the filenames used in the page.html? (write the filebames with their extensions and separate them with comma ',')_

**Answer:** `pokijan.jpg,research_center.jpg`

- Filter expression

  `ftp-data`

- Explanation

  `Filter ftp-data dan cari info LIST paling pertama dan follow TCP stream untuk melihat nama file gambar`

- Output result

  <img width="1279" height="372" alt="image" src="https://github.com/user-attachments/assets/35be277f-7c61-4d79-914a-66a496fdd56e" />
  <img width="524" height="182" alt="image" src="https://github.com/user-attachments/assets/65f659b2-5f14-4210-adcb-317316220072" />

  <br>
  <br>

## Task 10

- Flag

  `JARKOM25{f1nisssshs55s5s533s_l1n333ee333E3_95702533652910bh4oi2s0ty345215123123FHD6KNFOAK3BZFQ_02864a2e03e51faa4abc7bb780dafe16}`

> a. Apa nama file yang mengandung string terencode?

> _a. What is the filename that contains encoded string?_

**Answer:** `secret.txt`

- Filter expression

  `ftp-data`

- Explanation

  `Filter ftp-data dan cari file berekstensi .txt serta amati apakah dia berisi encoded string, ternyata kita menemukan secret.txt`

- Output result

  <img width="1919" height="1079" alt="image" src="https://github.com/user-attachments/assets/5cf9b55d-4a10-4c7d-91b1-fec7f8273283" />

  <br>
  <br>

> b. Apa nama file hasil copy file sebelumnya?

> _b. What is the filename of the previous file copy?_

**Answer:** `secret1.txt`

- Filter expression

  `ftp-data`

- Explanation

  `Filter ftp-data dan cari file berekstensi .txt serta amati apakah dia berisi encoded string, ternyata kita menemukan secret1.txt yang mirip dengan secret.txt. Penambahan angka 1 dinama file menunjukkan bahwa secret1.txt adalah hasil salinan dari secret.txt`

- Output result

  <img width="1919" height="1079" alt="image" src="https://github.com/user-attachments/assets/693d554b-0bb5-4b75-acd4-15007a3f5c6d" />

  <br>
  <br>

> c. What is the decoded string from the previous file?

> _c. Apa decoded string dari file tersebut?_

**Answer:** `Pada suatu hari Rey bertemu dengan Nailong the Milk Dragon. Ketika bertemu, Rey mengajarkan Nailong apa itu Jaringan Komputer. Nailong pun senang karena ternyata Jaringan Komputer itu gampang.`

- Filter expression

  `ftp-data`

- Explanation

  `Kalau kita lihat, encoded string berformat Base64. Oleh karena itu, kita salin seluruh encoded string dan kita translate di internet menggunakan Base64 Decoder`

- Output result

  <img width="1014" height="82" alt="image" src="https://github.com/user-attachments/assets/26d733a5-69c6-4408-a877-572a1cb17b16" />
  <img width="981" height="687" alt="image" src="https://github.com/user-attachments/assets/d41576ab-7026-4574-b22e-39f1efe1a0bf" />

  <br>
  <br>

## Summary
Praktikum Jaringan Komputer 1 mencakup beberapa tantangan. Mulai dari crimping, hingga melakukan Capture The Flag menggunakan Wireshark. Crimping adalah suatu kegiatan menyambungkan kabel UTP dengan RJ45 sebagai konektornya. Pada praktikum tersebut dibutuhkan pengetahuan teori mengenai urutan kabel, dan keterampilan menggunakan alat. Kemudian pada praktikum Wireshark, diberikan beberapa soal yang harus diselesaikan. Soal-soal tersebut dapat diselesaikan dengan menganalisis packet capture file dengan menggunakan Wireshark. Diperlukan pengetahuan seperti teori penggunaan Wireshark, display filter, dan find string. Dalam praktiknya, juga diperlukan ketelitian dalam menganalisis packet capture file. Sehingga praktikum Wireshark dapat terselesaikan.
## Problems
Kurangnya pengetahuan saya menggunakan Wireshark menjadi tantangan karena beberapa soal yang belum saya solve ternyata menggunakan flter yang belum pernah saya coba. Ini murni kesalahan saya, karena seharusnya sebagai praktikan harus selalu mencoba semua kemungkinan yang ada untuk menemukan solusi.
