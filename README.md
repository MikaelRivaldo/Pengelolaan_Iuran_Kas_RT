# Anggota Kelompok

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
