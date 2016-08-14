---
layout: post
title: "Membuat Custom Argument pada Django Testing"
date: 2016-08-13 22:45:41
categories: django
comment: True
---
Mulai versi 1.8, Django memiliki fitur untuk menambahkan argument ketika melakukan testing, yaitu dengan meng-override methode `add_arguments` dari class DiscoverRunner.  

Berikut ini adalah contoh custom test runner yang memiliki tambahan argument `--headless`.  

{% gist 6ae01e8dff5a1454880b3349116c6c65 %}
