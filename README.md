## Mata Kuliah

Sebagai tugas praktikum: [6 dan 7] Basis Data | Universitas Pelita Bangsa.

## Laporan Praktikum

- Bagian 1: Membuat Tabel untuk Praktikum 6 dan 7

  > silahkan restore ***[Praktikum 6] 10-06-2024.sql***.

  <p align="left">
    <img src="/ss/ERD.jpg" width="800">
  </p>

### Pertanyaan dari Praktikum 7

1. Data karyawan yang bekerja pada departemen yang sama dengan karyawan yang bernama Fii:
```sql
SELECT e.*
FROM employee e
JOIN department d ON e.id_department = d.id_department
WHERE d.id_department = (SELECT id_department FROM employee WHERE name = 'Fii');
```
  
2. Data karyawan yang gajinya lebih besar dari rata-rata gaji semua karyawan, urutkan menurun berdasarkan besaran gaji:
```sql
SELECT *
FROM employee
WHERE salary > (SELECT AVG(salary) FROM employee)
ORDER BY salary DESC;
```

3. NIK dan nama karyawan untuk semua karyawan yang bekerja di department yang sama dengan karyawan dengan nama yang mengandung huruf 'A':
```sql
SELECT e.nik, e.name, e.id_department
FROM employee e
JOIN department d ON e.id_department = d.id_department
WHERE d.id_department IN (SELECT id_department FROM employee WHERE name LIKE '%A%');
```

4. Data karyawan yang bekerja pada departemen yang ada di kantor pusat:
```sql
SELECT e.*, c.name AS company_name
FROM employee e
JOIN department d ON e.id_department = d.id_department
JOIN company c ON d.id_company = c.id_company
WHERE c.name = 'Isekai';
```

5. NIK dan nama karyawan untuk semua karyawan yang bekerja di department yang sama dengan karyawan dengan nama yang mengandung huruf 'A' dan yang gajinya lebih besar dari rata-rata gaji semua karyawan:
```sql
SELECT e.nik, e.name, e.salary
FROM employee e
JOIN department d ON e.id_department = d.id_department
WHERE d.id_department IN (SELECT id_department FROM employee WHERE name LIKE '%A%')
AND e.salary > (SELECT AVG(salary) FROM employee);
```

  <p align="left">
    <img src="/ss/Result.jpg" width="600">
  </p>

## Documentation

All associated resources. are licensed under the [MIT License](https://mit-license.org/).
