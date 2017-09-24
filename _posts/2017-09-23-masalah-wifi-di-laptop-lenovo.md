---
layout: post
title: Masalah Wifi Laptop Lenovo di Linux
date: 2017-09-23 08:00:00
description: Masalah ketika menghidupkan wifi di linux khusus laptop lenovo
share: true
comments: true
tags:
  - linux
  - lenovo
---

Saya menginstall Fedora di laptop Lenovo V510. Ketika ingin terkoneksi ke jaringan wifi, saya mengalami masalah, yaitu wifi network selalu dalam keadaan `Turn Off`. Setiap kali saya coba ubah ke `Turn On`, selalu gagal tanpa keterangan apapun. Setelah googling, berikut ini solusi yang berhasil buat saya:
1. Buka file `/etc/modprobe.d/blacklist.conf` dengan text editor.
   `sudo vi /etc/modprobe.d/blacklist.conf`
2. Tambahkan text `blacklist ideapad-laptop` di bagian paling bawah.
3. Simpan dan tutup text editor.
4. Reboot.


Cara ini sudah berhasil saya coba di Ubuntu 16.04, Debian 9 dan Fedora 26. Meskipun model laptopnya bukan Ideapad, tapi tetap berhasil.
