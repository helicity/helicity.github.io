---
title: "Visual Studio c++ 프로젝트, dll & pdb unmatch"
---

항상 그렇지만, 실수와 착각으로 인해 고생했던 것들은 뭔가 적어놓고 싶어진다.

크래시덤프 디버그를 위해서 BCGCBPRO 30.30 dll(release)을 다시 빌드하고 덤프파일 로드했는데
pdb로딩이 안되더라. windbg로도 해보고 별짓을 다해봐도 pdb 로딩이 안된다. 방금 빌드한 dll/pdb인데도!

결국 chkmatch.exe 로 두개를 비교해봤다.
그랬더니 나오는 메시지가..


D:\coding\OC_4-6\enscape_main_control_program\bin\x86Release>chkmatch -c BCGCBPRO3030120.dll BCGCBPRO3030120.pdb
ChkMatch - version 1.0
Copyright (C) 2004 Oleg Starodumov
http://www.debuginfo.com/


Executable: BCGCBPRO3030120.dll
Debug info file: BCGCBPRO3030120.pdb

Error: Debug information not found in the executable.



release로 빌드한 dll에 디버그 정보가 없다고 한다.

그러면 visual studio나 windbg는 디버그 정보 없다고 띄워야 할텐데,

"매칭되는 심볼을 찾을수 없다" 이딴 메시지가 뜨니까 낚인거었다.

욕하고 싶은 1박2일이었다.

참고로 chkmatch.exe에는 pdb와 dll의 시그니처를 강제로 맞추는 기능도 제공한다. (타임스탬프만 다르거나 할 때 등)
