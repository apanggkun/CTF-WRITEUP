# CTF Writeup: Let's Help John!

- Kategori: Web
- Poin: 100
- Description: Oh no! My ex-cellmate got jailed again! Help me leave a key for him!
- Penulis: Ultramy

## Solution

Ini adalah tantangan web yang sederhana menggunakan **Burpsuite**.

Ketika pertama kali mengakses situs web, Anda akan melihat ini![image](https://github.com/user-attachments/assets/c3cc7a02-205f-43b2-b225-0278c1fa20f5)


Jadi saya klik play, duhhh

![image](https://github.com/user-attachments/assets/c555c191-f464-4192-9d38-267712a82466)


Karena dikatakan harus dirujuk dari situs resmi, saya mengubah referer menjadi `http://state.com` dalam request http
![image](https://github.com/user-attachments/assets/1653cd20-5e97-4e24-98dd-873d8df5cb39)


Berhasil gais, situs web berikutnya meminta kita untuk mengubah nilai cookie dari quantity dari `Limited` menjadi `Unlimited`. Jadi sekarang kita periksa saja dan lihat nilai apa yang harus diubah. Setelah kita tahu nilai apa yang ingin diubah, kita tinggal tambahkan saja ke dalam header http-nya. ![image](https://github.com/user-attachments/assets/2b1a4d99-40f4-4583-907f-101c7872b183)


Di dalam cookie terdapat `quantity` yang memiliki nilai `Limited`. Oke, karena sekarang kita tahu apa yang harus kita ubah, tinggal kita masukkan saja valuenya dalam request http-nya
![image](https://github.com/user-attachments/assets/6edb2ac7-df35-43da-a084-442071895998)


Oke, sekarang kita diminta untuk mengganti `user-agent` menjadi `AgentYessir`.
![image](https://github.com/user-attachments/assets/52fe94f8-1755-4f7f-b5ee-67035c4dc409)


Don ges, sekarang situs web mengatakan, `"Great! To make it obvious for John, lets say it's From pinkus@cellmate.com"`. Jadi di field request http ada yang disebut `From` yang bisa kita isi dengan email. Dengan pengetahuan itu, kita masukkan saja `From: pinkus@cellmate.com` dalam requestnya.

![image](https://github.com/user-attachments/assets/79202020-2161-4521-a9d9-92a5c54e385c)

Selesai deh...


## Flag
FLAG: `COMPFEST16{nOW_h3Lp_H1m_1n_john-O-jail-misc_8506972ce3}`
