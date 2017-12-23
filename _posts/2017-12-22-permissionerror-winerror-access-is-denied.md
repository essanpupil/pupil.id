---
layout: post
title: PermissionError [WinError 5] Access is denied Ketika Menjalankan py.test di Windows
date: 2017-12-22 01:00:00
description: Memperbaiki error PermissionError [WinError 5] Access is denied ketika menjalankan pytest di Windows
share: true
comments: true
tags:
  - pytest
  - python
  - windows
---
Saya pernah mengalami error ketika menjalankan pytest di Windows 10. Keterangan lengkapnya adalah:
```
(dbfi) C:\Users\Jendela>pytest
============================= test session starts =============================
platform win32 -- Python 3.6.3, pytest-3.2.3, py-1.5.2, pluggy-0.4.0
rootdir: C:\Users\Jendela, inifile:
plugins: django-3.1.2, cov-2.5.1
collected 0 items / 1 errors

=================================== ERRORS ====================================
______________________________ ERROR collecting  ______________________________
envs\dbfi\lib\site-packages\py\_error.py:66: in checked_call
    return func(*args, **kwargs)
E   PermissionError: [WinError 5] Access is denied: 'C:\\Users\\Jendela\\AppData\\Local\\Application Data'

During handling of the above exception, another exception occurred:
envs\dbfi\lib\site-packages\py\_path\common.py:377: in visit
    for x in Visitor(fil, rec, ignore, bf, sort).gen(self):
envs\dbfi\lib\site-packages\py\_path\common.py:429: in gen
    for p in self.gen(subdir):
envs\dbfi\lib\site-packages\py\_path\common.py:429: in gen
    for p in self.gen(subdir):
envs\dbfi\lib\site-packages\py\_path\common.py:429: in gen
    for p in self.gen(subdir):
envs\dbfi\lib\site-packages\py\_path\common.py:414: in gen
    entries = path.listdir()
envs\dbfi\lib\site-packages\py\_path\local.py:387: in listdir
    names = py.error.checked_call(os.listdir, self.strpath)
envs\dbfi\lib\site-packages\py\_error.py:86: in checked_call
    raise cls("%s%r" % (func.__name__, args))
E   py.error.EBUSY: [Resource device]: listdir('C:\\Users\\Jendela\\AppData\\Local\\Application Data',)
!!!!!!!!!!!!!!!!!!! Interrupted: 1 errors during collection !!!!!!!!!!!!!!!!!!!
=========================== 1 error in 0.32 seconds ===========================
```
Error ini terjadi ketika `pytest` dijalankan bukan di dalam root directory project yang saya kerjakan. Saya menjalankan `pytest` ketika berada di folder `C:\User\Jendela`, sedangkan root directory project saya ada di `C:\User\Jendela\Projects\dbfi`. Solusi dari error ini adalah, pastikan anda berada di root directory project anda ketika menjalankan `pytest`.
