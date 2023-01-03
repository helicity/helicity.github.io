---
title: "python 최소 실행버전 만들기 (python 무설치 스크립트용)"
---


python을 설치하지 않고 python 스크립트를 실행하기 위한 최소버전 패키지를 만드는 방법을 정리한다.


파이썬 공식 설치본이든, portable 버전이든, python.exe 파일이 있는 폴더 안에 필요한 모든것들이 기본적으로 있다.

아무것도 import 하지 않더라도 python실행파일은 기본적으로 site 모듈을 필요로 하게되는데,
이 site 모듈이 내부적으로 import os를 하기 때문에, os 모듈에서 import하는 모듈들은 모두 기본적으로 포함되어야 한다.

일단 2.7.6버전 기준으로 다음 파일들이 필요하다.

 python.exe
 python27.dll
 msvcr90.dll
 [Lib]
    _abcoll
    _weakrefset
    abc
    codecs
    copy_reg
    functools
    genericpath
    linecache
    locale
    ntpath
    os
    re
    site
    sre_compile
    sre_constants
    sre_parse
    stat
    sysconfig
    traceback
    types
    UserDict
    warnings
    [encodings]
        모든 파일들... (120개)

