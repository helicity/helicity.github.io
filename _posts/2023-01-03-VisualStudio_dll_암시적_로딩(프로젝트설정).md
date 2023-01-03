---
title: "Visual Studio c++ 프로젝트, dll 암시적 로딩, 프로젝트 설정"
---


자주 안쓰니까 자꾸 까먹어서 정리해 놓는다.

Visual Studio c++로 dll 프로젝트 만들고, exe 프로젝트에서 dll을 암시적으로 로딩하도록 하는 프로젝트 설정 방법.


dll 프로젝트만 빌드하면 dll만 나오고 export library는 생성되지 않는다.

exe 프로젝트에서 Project Property > Linker > Input > Additional Dependencies 에
dll이름과 동일한 lib 파일이름을 적어주면, exe 프로젝트를 빌드할 때 export library를 자동으로 생성한다.

이거 까먹어서 (어디 설명도 없고) dll 프로젝트 설정만 계속 건드려보는 삽질을 했다.

dll 프로젝트는 기본 설정으로 놔둘 것
https://learn.microsoft.com/ko-kr/cpp/build/reference/working-with-import-libraries-and-export-files?view=msvc-170
여기는 링커 옵션 설명 (/DEF, /EXPORT) 등이 있는데 이건 Visual Studio에서 자동으로 연결해주는 것은 고려하지 않는 것
