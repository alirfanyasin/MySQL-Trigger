# MySQL Trigger

## Pemahaman Dasar:
- Trigger adalah semacam "pemicu" yang aktif ketika suatu peristiwa tertentu terjadi di dalam tabel.
- Peristiwa tersebut bisa berupa operasi penyisipan (INSERT), pembaruan (UPDATE), atau penghapusan (DELETE).

## Eksekusi
- Trigger dieksekusi setelah peristiwa tertentu terjadi.
- Misalnya, jika Anda memiliki trigger setelah penyisipan (AFTER INSERT), itu berarti trigger akan dijalankan setelah data baru dimasukkan ke dalam tabel.

## Menyederhanakan Tugas Otomatis
- Trigger membantu menyederhanakan tugas otomatisasi di dalam database.
- Contoh: Anda bisa membuat trigger untuk memperbarui timestamp setiap kali ada pembaruan pada suatu baris.

## Peringatan
- Penggunaan trigger perlu diperhatikan agar tidak menyebabkan kompleksitas yang tidak diinginkan.
- Terlalu banyak trigger atau trigger yang kompleks dapat membuat sistem sulit dipahami.