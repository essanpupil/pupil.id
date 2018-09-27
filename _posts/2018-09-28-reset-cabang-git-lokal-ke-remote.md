---
layout: post
title: "Reset Cabang Git di Lokal ke Cabang Remote"
date: 2018-09-28 01:00:00
categories: git
comments: True
tags:
  - git
---
Saya baru saja mengubah file di cabang master di repo lokal. Setelah selesai, kemudian saya *commit* perubahan tersebut. Tapi, setelah saya pikir-pikir lagi, ternyata saya salah, dan tidak ingin menyimpan perubahan yang sudah terlanjur saya *commit*. Saya ingin cabang master di lokal sama dengan di *remote*. Berikut urutan perintah git yang saya pakai untuk me-*reset* cabang master git lokal agar sama dengan cabang remote:

1. `git fetch origin`
2. `git reset --hard origin/master`

PERHATIAN: Perintah `git reset --hard` akan menghapus semua perubahan yang sudah dilakukan, meskipun sudah *commit*. Cara ini saya temukan di [https://stackoverflow.com/a/1628334/1084903](https://stackoverflow.com/a/1628334/1084903)
