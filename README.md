# Anggota Kelompok

# Kelompok 13 (Ganjil) 

| NAMA  | NIM | 
| ------------- | ------------- | 
| Muhammad Dzaki Abbiyu | 312210381  |
| Mikael Rivaldo | 312210378 |

----
### Website ini menggunakan bahasa pemrograman PHP dan database MySQL. Website ini digunakan untuk pengelolaan iuran kas RT.

----

Databases Table

----

![image](https://github.com/MikaelRivaldo/Pengelolaan_Iuran_Kas_RT/assets/115770247/74d5e271-b02c-4553-941b-949af9f80114)

`Website diatas ini menggunakan 3 tabel database MYSQL untuk menyimpan data yaitu Tabel Users, Warga dan Iuran`

----

## Tabel Users

![user](https://github.com/MikaelRivaldo/Pengelolaan_Iuran_Kas_RT/assets/115770247/9a743b7c-1444-4861-a07c-60348255f8a3)

### Untuk Sourcodenya bisa menggunakan seperti dibawah ini :

```html
CREATE TABLE IF NOT EXISTS `db_kas_rt`.`users` (
`id` INT NOT NULL AUTO_INCREMENT,
`username` VARCHAR(100) NULL,
`password` VARCHAR(100) NULL,
`nama` VARCHAR(200) NULL,
`email` VARCHAR(200) NULL,
`status` TINYINT(1) NULL,
`role` TINYINT(1) NULL DEFAULT 2 COMMENT '1:Admin\n2:User',
PRIMARY KEY (`id`),
UNIQUE INDEX `username_UNIQUE` (`username` ASC),
UNIQUE INDEX `email_UNIQUE` (`email` ASC))
ENGINE = InnoDB
```
----

 ## Tabel Warga

![warga](https://github.com/MikaelRivaldo/Pengelolaan_Iuran_Kas_RT/assets/115770247/9b54b903-158f-404a-a598-1bbc3047441e)

### Untuk Sourcodenya bisa menggunakan seperti dibawah ini :

```html
CREATE TABLE IF NOT EXISTS `db_kas_rt`.`warga` (
`id` INT NOT NULL AUTO_INCREMENT,
`nik` VARCHAR(50) NULL,
`nama` VARCHAR(200) NULL,
`jenis_kelamin` ENUM('L', 'P') NULL,
`no_hp` VARCHAR(20) NULL,
`alamat` TINYTEXT NULL,
`no_rumah` VARCHAR(10) NULL,
`status` TINYINT(1) NULL,
`users_id` INT NOT NULL,
PRIMARY KEY (`id`),
UNIQUE INDEX `nik_UNIQUE` (`nik` ASC),
INDEX `fk_warga_users1_idx` (`users_id` ASC),
CONSTRAINT `fk_warga_users1`
FOREIGN KEY (`users_id`)
REFERENCES `mydb`.`users` (`id`)
ON DELETE NO ACTION
ON UPDATE NO ACTION)
ENGINE = InnoDB
```

---

## Tabel Iuran

![iuran](https://github.com/MikaelRivaldo/Pengelolaan_Iuran_Kas_RT/assets/115770247/7240f7d2-756b-46bc-ac69-0ed57c882a6e)

### Untuk Sourcodenya bisa menggunakan seperti dibawah ini :

```html
CREATE TABLE IF NOT EXISTS `db_kas_rt`.`iuran` (
`id` INT NOT NULL AUTO_INCREMENT,
`tanggal` DATE NULL,
`warga_id` INT NOT NULL,
`nominal` DECIMAL(10,2) NULL,
`keterangan` TINYTEXT NULL,
`jenis_iuran` TINYINT(1) NULL,
PRIMARY KEY (`id`),
INDEX `fk_iuran_warga1_idx` (`warga_id` ASC),
CONSTRAINT `fk_iuran_warga1`
FOREIGN KEY (`warga_id`)
REFERENCES `mydb`.`warga` (`id`)
ON DELETE NO ACTION
ON UPDATE NO ACTION)
ENGINE = InnoDB
```

---

## TOOLS YANG DIGUNAKAN

1. **XAMPP**

   Dalam pembuatan sistem iuran kas RT ini, kami menggunakan XAMPP sebagai lingkungan pengembangan lokal. XAMPP terdiri dari Apache, MySQL, dan PHP. Apache adalah web server yang digunakan untuk menampilkan halaman web. MySQL adalah database server yang digunakan untuk menyimpan data. PHP adalah bahasa pemrograman server-side yang digunakan untuk membuat halaman web interaktif.

2. **VSCode**

   Untuk editor kode, kami menggunakan Visual Studio Code (VSCode). VSCode adalah editor kode sumber yang populer yang dapat digunakan untuk berbagai bahasa pemrograman. VSCode memiliki fitur-fitur yang memudahkan pengembang untuk menulis, mengedit, dan menjalankan kode.

3. **Bootstrap**

   Untuk membuat tampilan halaman web, kami menggunakan Bootstrap. Bootstrap adalah framework CSS yang populer yang dapat digunakan untuk membuat tampilan halaman web yang responsif. Bootstrap memiliki fitur-fitur yang memudahkan pengembang untuk membuat tampilan halaman web yang menarik dan mudah digunakan.

### Database
----

![image](https://github.com/MikaelRivaldo/Pengelolaan_Iuran_Kas_RT/assets/115770247/d71ff985-5390-4b4c-88c9-e16328fb1ce2)


## **_Demo:_**

<img src=https://download.logo.wine/logo/YouTube/YouTube-Logo.wine.png width="130px">

- [Dokumentasi Youtube]()

<img src=https://res.cloudinary.com/practicaldev/image/fetch/s--ux15-5qy--/c_imagga_scale,f_auto,fl_progressive,h_1080,q_auto,w_1080/https://dev-to-uploads.s3.amazonaws.com/i/a12tj8n6facp0kt0xb0n.jpeg width="120px">

- [Laporan](https://drive.google.com/file/d/1YV1iuozh-MXM3i06TF9NUDLHI__pqfRH/view?usp=sharing)


- [Web Hosting]()
