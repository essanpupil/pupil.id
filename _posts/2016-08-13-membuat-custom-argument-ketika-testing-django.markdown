---
layout: post
title: "Membuat Custom Argument pada Django Testing"
date: 2016-08-13 22:45:41
categories: django
comments: True
---
Untuk menjalankan testing dj Django, cukup dengan perintah `./manage.py test`. Beberapa argument optional yang bisa dijalankan ketika testing anrtara lain:  

1. `--keep-db` untuk tidak menghapus database yang digunakan ketik testing.
2. `-v [2, 3]` untuk menampilkan detail informasi ketika menjalankan testing. Pilihan level detail adalah 2 & 3.
3. `--settings SETTINGS_MODULE` untuk menentukan module settings yang dipakai untuk menjalankan testing.
4. `--testrunner TEST_RUNNER_CLASS` untuk menentukan test runner yang dipakai dalam menjalankan testing.  

Argument testing django selengkapnya bisa dilihat dengan menjalankan `./manage.py test -h`.  

Mulai versi 1.8, Django memiliki fitur untuk menambahkan argument ketika melakukan testing, yaitu dengan meng-override classmethode `add_arguments` dari class `django.test.runner.DiscoverRunner` di dalam sebuah custom test runner. Berikut ini contoh langkah-langkah untuk membuat custom test runner yang memiliki tambahan argument `--headless`.

## Buat module custom_test_runner.py
Untuk menampung class test runner, buatlah sebuah module dengan nama `custom_test_runner.py` kemudian simpan module tersebut di direktori yang sama dengan module settings.py

## Buat test runner class
Tulislah class di bawah ini pada module yang di buat sebelumnya.  

```python
from django.test.runner import DiscoverRunner


class CustomTestRunner(DiscoverRunner):

    @classmethod
    def add_arguments(cls, parser):
        parser.add_argument('--headless',
            action='store_true', default=False, dest='headless',
            help='Add this options to do headless browser testing')
```

## Edit module settings.py
Tambahkan keterangan di module settings.py untuk menggunakan test runner buatan kita, dengan cara menambahkan bari berikut:  

`TEST_RUNNER = 'myproject.custom_test_runner.CustomTestRunner'`  

Ubahlah *path* di atas sesuai dengan konfigurasi project anda. Biasanya, `myproject` adalah direktori tempat module settings.py tersimpan.

## Konfirmasi argument tambahan
Untuk mengetahui apakah penambahan custom argument berhasil, anda bisa menggunakan command  `python manage.py test -h`, apabila berhasil, maka custom argument yang anda buat akan ditampilkan.
