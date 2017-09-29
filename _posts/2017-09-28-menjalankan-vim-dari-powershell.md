---
layout: post
title: Menjalankan Vim dari PowerShell
date: 2017-09-28 17:31:00
description: Membuka text editor Vim dari PowerShell di Windows 10
share: true
comments: true
tags:
  - windows 10
  - vim
  - powershell
---

Untuk dapat menggunakan vim di Windows 10, langkah-langkah yang harus dilakukan adalah:
1. Download vim untuk windows di [https://vim.sourceforge.io/download.php#pc](https://vim.sourceforge.io/download.php#pc).
2. Install vim dengan cara double click pada file yg sudah di download.
3. Buat alias untuk command line di PowerShell dengan cara mengetikkan baris perintah berikut ini di dalam PowerShell.
   `Set-Alias vim ' C:\Program Files (x86)\Vim\vim80\vim.exe'`
4. Anda bisa menjalankan vim dari PowerShell dengan menggunakan perintah `vim` dari dalam PowerShell.