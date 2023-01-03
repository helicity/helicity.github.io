---
title: "c++ std::atomic_bool vs std::atomic<bool>"
---



atomic<bool>은 operator=(bool)를 지원해서 대입초기화가 가능하다.
반면에 atomic_bool은 store, load 멤버를 이용해야만 한다.

c++에 atomic<bool>보다 사용성이 떨어지는 atomic_bool이 존재하는 이유는 ?

그건 바로..

c++ committee 애들이 c랑 호환되는 기능 같이 추가하자고 제안했다가
뺀찌먹었던거란다.
(이 오지랖 넓고 오만한 xx 들..)

아래는 스캇메이어(무려!)가 이 내용을 질문하고 c++ 커미티 애(Bo Persson)가 대답했던 글

https://comp.std.cpp.narkive.com/nwMakWji/std-atomic-bool-vs-std-atomic-bool


[Count the number of commits on a Git branch]: https://stackoverflow.com/questions/11657295/count-the-number-of-commits-on-a-git-branch
