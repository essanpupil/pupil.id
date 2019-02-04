---
layout: post
title: "Fungsi Python time.tzset() Tidak Dapat Digunakan di Windows"
date: 2018-09-24 23:55:00
comments: True
tags:
  - python
  - windows
---
Hari ini saya menemukan satu hal menarik, ternyata fungsi `time.tzset()` tidak dapat di gunakan di sistem operasi Windows. Beginilah yang terjadi ketika saya mencobanya.

```python
>>> import time
>>> time.tzset()
Traceback (most recent call last):
  File "<stdin>", line 1, in <module>
AttributeError: module 'time' has no attribute 'tzset'
```

Sedangkan ketika saya mencoba di Ubuntu (WSL) tidak ada masalah, beginilah hasilnya:

```python
>>> import time
>>> time.tzset()
>>>
```

Setelah saya cek [dokumentasinya](https://docs.python.org/3/library/time.html#time.tzset), ternyata memang fungsi ini hanya tersedia di sistem operasi berbasis unix.
