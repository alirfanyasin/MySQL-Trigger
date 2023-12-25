# MySQL Trigger


## Basic Trigger
```sql
CREATE TRIGGER trigger_name
  AFTER INSERT
  ON table_name
  FOR EACH ROW

BEGIN
    -- TODO: IMPLEMENT
END;
```

## Crete Trigger
Membuat trigger untuk melihat perubahan data <br>
Example:

Gunakan database `sekolah.sql`


Langkah pertama membuat table baru bernama `guru_log`
```sql
CREATE TABLE guru_log (
  id BIGINT PRIMARY KEY AUTO_INCREMENT,
  guru_id BIGINT,
  old_nama_guru VARCHAR(100),
  new_nama_guru VARCHAR(100),
  old_tanggal_lahir DATE,
  old_jenis_kelamin VARCHAR(50)
);
```

Membuat sebuah trigger untuk menyimpan perubahan ketika data dari table `guru` diupdate
```sql
CREATE TRIGGER guru_log
  BEFORE UPDATE
  ON guru
  FOR EACH ROW
BEGIN
  -- TODO: Implement
  INSERT INTO guru_log
  SET guru_id=OLD.guru_id,
  old_nama_guru=OLD.nama_guru,
  new_nama_guru=NEW.nama_guru,
  old_tanggal_lahir=OLD.tanggal_lahir,
  old_jenis_kelamin=OLD.jenis_kelamin;
END;
```


Jalankan perintah update untuk mengtrigger `guru_log` 
```sql
UPDATE guru SET nama_guru = 'Hendry' WHERE guru_id = 1;
```

Lihat di dalam tablenya sekarang ada data `nama_guru` yang lama dan data yang baru.
```sql
SELECT * FROM guru_log;
```


Data Awal di table `guru`
![image](https://github.com/alirfanyasin/MySQL-Trigger/assets/77270380/c236be19-9bc0-40fc-9f67-9213804a7311)

Data setelah di update di table `guru`
![image](https://github.com/alirfanyasin/MySQL-Trigger/assets/77270380/6d6dafa6-d62b-4013-8f82-cad3f542f249)

Data di table `guru_log`
![image](https://github.com/alirfanyasin/MySQL-Trigger/assets/77270380/0e02cd4b-2138-4b42-81c1-b43039b17368)





