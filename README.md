
# MUHAMMAD RIZKY EFENDI
# 1. Menampilkan Nama Karyawan yang Berada di Departemen yang Dipimpin oleh Manajer dengan Nama 'Rika'
----

SELECT k.nama
FROM karyawan k
JOIN departemen d ON k.id_dept = d.id_dept
JOIN karyawan m ON d.manajer_nik = m.nik
WHERE m.nama = 'Rika';


---
![Screenshot (195)](https://github.com/MUHAMMADRIZKYEFENDI/muhammad-rizky-efendi-uas/assets/168548623/07cd95fc-2c55-47a1-834d-16e377a2f3a6)

# 2. Menampilkan Nama Proyek yang Dikerjakan oleh Karyawan dari Departemen 'RnD'

---
SELECT DISTINCT p.nama
FROM project p
JOIN project_detail pd ON p.id_proj = pd.id_proj
JOIN karyawan k ON pd.nik = k.nik
JOIN departemen d ON k.id_dept = d.id_dept
WHERE d.nama = 'RnD';

---
![Screenshot (196)](https://github.com/MUHAMMADRIZKYEFENDI/muhammad-rizky-efendi-uas/assets/168548623/8b17cd8f-ba3e-447d-b790-2600b339d251)

# 3. Menampilkan Nama Karyawan yang Terlibat dalam Lebih dari Satu Proyek
---
SELECT k.nama
FROM karyawan k
JOIN project_detail pd ON k.nik = pd.nik
GROUP BY k.nama
HAVING COUNT(pd.id_proj) > 1;

---
![Screenshot (197)](https://github.com/MUHAMMADRIZKYEFENDI/muhammad-rizky-efendi-uas/assets/168548623/35e23c5a-d8f7-48be-acff-7934034f539e)

# 4. Menampilkan Nama Proyek yang Melibatkan Karyawan Terbanyak
---
SELECT p.nama
FROM project p
JOIN project_detail pd ON p.id_proj = pd.id_proj
GROUP BY p.nama
ORDER BY COUNT(pd.nik) DESC
LIMIT 1;

---
![Screenshot (198)](https://github.com/MUHAMMADRIZKYEFENDI/muhammad-rizky-efendi-uas/assets/168548623/f213bd01-9de8-4889-9d75-13f720e55441)

# 5. Menampilkan Nama Proyek yang Diikuti oleh Karyawan dengan Gaji Pokok Kurang dari 3 Juta
---
SELECT DISTINCT p.nama
FROM project p
JOIN project_detail pd ON p.id_proj = pd.id_proj
JOIN karyawan k ON pd.nik = k.nik
WHERE k.gaji_pokok < 3000000;

---
![Screenshot (199)](https://github.com/MUHAMMADRIZKYEFENDI/muhammad-rizky-efendi-uas/assets/168548623/a49b61d7-b08d-4b20-81e5-ef99e0066489)

