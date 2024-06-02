## Profil
| Variable | Isi |
| -------- | --- |
| **Nama** | ALVIN ALFANDY |
| **NIM** | 312310473 |
| **Kelas** | TI.23.A5 |
| **Mata Kuliah** | Basis data |

# Soal Latihan Praktikum 

![gambar_ss1](screenshot/ss1.png)

![gambar_ss2](screenshot/ss2.png)

![gambar_ss3](screenshot/ss3.png)

![gambar_ss4](screenshot/ss4.png)

# Tabel mahasiswa
![alt text](screenshot/image.png)

# Tabel dosen
![alt text](screenshot/image-1.png)

# Tabel matakuliah
![alt text](screenshot/image-4.png)

# Tabel jadwal mengajar
![alt text](screenshot/image-2.png)

# Tabel Krsmahasiwa
![alt text](screenshot/image-3.png)

## Latihan

- Lakukan join table Mahasiswa dan Dosen.
- Lakukan join tabel Matakuliah dan Dosen.
- Lakukan join table JadwalMengajar, Dosen, dan Matakuliah.
- Lakukan join tabel KrsMahasiswa, Mahasiswa, Matakuliah, dan Dosen.

## Buat Script SQL JOIN Table berdasarkan skema data diatas.

- Lakukan join table Mahasiswa dan Dosen.
![alt text](screenshot/image-5.png)
```
SELECT m.nim, m.nama, m.jk, d.nama AS 'Dosen PA'
FROM mahasiswa m
JOIN dosen d ON m.kd_ds = d.kd_ds;
```
- LEFT JOIN table Mahasiswa dan Dosen
![image](https://github.com/alvinalfandy/Mysql5/assets/64345368/b4d1430b-6275-44b8-b889-3c7e8a636ab1)
```
SELECT Mahasiswa.nim, Mahasiswa.nama, Mahasiswa.jk, Dosen.nama AS "Dosen PA"
FROM Mahasiswa LEFT JOIN Dosen ON Dosen.kd_ds = Mahasiswa.kd_ds;
```

- Lakukan join tabel Matakuliah dan Dosen
![alt text](screenshot/image-6.png)
```
SELECT Matakuliah.kd_mk, Matakuliah.nama AS "Nama Matakuliah", Matakuliah.sks, Dosen.nama AS "Nama Dosen Pengampu"
FROM JadwalMengajar
LEFT JOIN Matakuliah ON JadwalMengajar.kd_mk = Matakuliah.kd_mk
LEFT JOIN Dosen ON JadwalMengajar.kd_ds = Dosen.kd_ds;

```
- Lakukan join table JadwalMengajar, Dosen, dan Matakuliah
![alt text](screenshot/image-7.png)
```
SELECT jm.kd_mk, mk.nama, mk.sks, d.nama AS 'Dosen Pengampu'
FROM jadwalmengajar jm
JOIN dosen d ON jm.kd_ds = d.kd_ds
JOIN matakuliah mk ON jm.kd_mk = mk.kd_mk;
```
-  join tabel KrsMahasiswa, Mahasiswa, Matakuliah, dan Dosen
![alt text](screenshot/image-8.png)
```
SELECT km.kd_mk, mk.nama, mk.sks, d.nama AS 'Dosen Pengampu', jm.hari, jm.jam, jm.ruang
FROM krsmahasiswa km
JOIN mahasiswa m ON km.nim = m.nim
JOIN matakuliah mk ON km.kd_mk = mk.kd_mk
JOIN jadwalmengajar jm ON km.kd_mk = jm.kd_mk AND km.kd_ds = jm.kd_ds
JOIN dosen d ON jm.kd_ds = d.kd_ds;
```

### Buat laporan praktikum yang berisi, langkah-langkah praktikum beserta screenshot yang sudah dilakukan dalam bentuk dokumen.

## SELESAI <img align="center" alt="Ikhsan-Python" height="40" width="45" src="https://em-content.zobj.net/source/microsoft-teams/337/student_1f9d1-200d-1f393.png"> <img align="center" alt="Ikhsan-Python" height="40" width="45" src="https://em-content.zobj.net/thumbs/160/twitter/348/flag-indonesia_1f1ee-1f1e9.png">


