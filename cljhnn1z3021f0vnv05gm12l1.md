---
title: "23년 6월 후반기 뉴스레터"
datePublished: Thu Jun 29 2023 21:25:42 GMT+0000 (Coordinated Universal Time)
cuid: cljhnn1z3021f0vnv05gm12l1
slug: 23-6-1
tags: newsletter

---

## 새로운 빌트인 함수들

go 1.21 릴리즈 캔디데이트가 출시되었습니다.

그와 함께 새로운 릴리즈 노트가 공개되었고, 새로운 내장 함수들도 공개되었습니다!

[Built-in functions in Go 1.21 (](https://antonz.org/go-1-21-builtins/)[antonz.org](http://antonz.org)[)](https://antonz.org/go-1-21-builtins/)

---

## 카프카와 고로 1억 활성 유저 받기

저는 나름 업무로 고와 NATS로 매우 많은 유저를 받는 서버 군을 받아서 이어서 개발해본 경험이 있습니다.

하지만 결국 다른 곳에서 병목이 생겨서 실패했는데요. 그때도 서버나 메시지큐의 성능적인 문제는 아니었습니다.

그래서 비슷한 이야기를 담고 있는 이 토픽이 흥미롭게 느껴지네요.

[How We Scaled to 100 Million Active Users Using Kafka and Golang — Eventual Consistency | by Mohammad Hoseini Rad | Jun, 2023 | ITNEXT](https://itnext.io/how-we-scaled-to-100-million-active-users-using-kafka-and-golang-eventual-consistency-6241cfeba7e8)

---

## 고 언어를 IDL로 쓸 수 없을까?

고 언어의 구조체는 사실 단순하게 쓰라고만 하면 얼마든지 단순하게 쓸 수 있습니다.

동일한 스펙의 JSON을 공유하는 여러 방법은 있지만, 의외로 고를 끼고 있는 서버를 운영한다면 이런 시도가 좋은 방향으로 이어질 수 있을 거라고 생각합니다.

[wilhelmguo/typescriptify-golang-structs: Convert your Go structs to TypeScript (](https://github.com/wilhelmguo/typescriptify-golang-structs)[github.com](http://github.com)[)](https://github.com/wilhelmguo/typescriptify-golang-structs)

---

## WASI에서 소켓 통신하기

머지안아 지원은 해주겠지만, 지금 당장, 롸잇나우 WASI에서 소켓 통신을 할 수 있는 라이브러리가 나왔습니다.

[stealthrocket/net: Go package implementing WASI socket extensions (](https://github.com/stealthrocket/net)[github.com](http://github.com)[)](https://github.com/stealthrocket/net)

---

## 이제는 고 프로그램도 스토킹을 해야할 시기

여러분들은 자신들이 만든 프로그램이 의도대로 동작하지 않아 곤혹스러울 때가 있었을 겁니다.

이제 곧 저희는 우리가 만든 프로그램이 어떻게 돌아가는 지 파악할 수 있게 될 것입니다.

[Execution tracer overhaul (](https://go.googlesource.com/proposal/+/ac09a140c3d26f8bb62cbad8969c8b154f93ead6/design/60773-execution-tracer-overhaul.md)[googlesource.com](http://googlesource.com)[)](https://go.googlesource.com/proposal/+/ac09a140c3d26f8bb62cbad8969c8b154f93ead6/design/60773-execution-tracer-overhaul.md)

---

## 뮤텍스와 채널에 대한 이야기

여러분들은 뮤텍스를 자주 쓰나요?  
채널을 자주 쓰나요?

저는 양쪽 다 자주 쓰는 편입니다.  
채널을 꽤 유용하게 활용했던 기억이 있습니다.  
성능은 좀 포기하더라도 채널을 썼을 때 좀 더 스타베이션이 덜 생성된 경험이 있어요.

그 이야기와는 별개로 이번에 소개드릴 아티클은 단순히 채널의 단점에 관한 이야기입니다.

[Go channels are bad and you should feel bad |](https://www.jtolio.com/2016/03/go-channels-are-bad-and-you-should-feel-bad/) [jtolio.com](http://jtolio.com)

---

## 매우 거대한 맵

혹시 아주 큰 크기의 맵을 만들어야 할 상황이 생기지 않던가요?

물론 전 없었습니다.

이번 아티클은 아주 거대한 맵을 만드는 이야기입니다.  
굳이 만들 상황이 없더라도 할당과 관련된 이야기가 있으니 한번 재밌게 읽어 보세요!

[Initializing Large Static Maps in Go | DoltHub Blog](https://www.dolthub.com/blog/2023-06-16-static-map-initialization-in-go/)

---

## 구조화된 로깅

고 1.21에는 `slog`가 추가되었습니다.

이제 막 빌트인으로 합류했다보니 가이드가 필요한 시점입니다.

그런 시기의 깔끔한 가이드가 있어 공유합니다!

[About Structured Logging in Go 1.21 - lzap (](https://lukas.zapletalovi.com/posts/2023/about-structured-logging-in-go121/)[zapletalovi.com](http://zapletalovi.com)[)](https://lukas.zapletalovi.com/posts/2023/about-structured-logging-in-go121/)

---

## 제네릭, 제네릭, 제네릭, ...

고퍼 여러분들은 모종의 이유로 인해 사실 제네릭이 여전히 그렇게 익숙하지 않으리라 생각합니다.

저도 막 `Option`이나 `Result`를 제외하곤 딱히 써보진 않았습니다.

그런 우리들을 위한 제네릭 가이드, 따란!

[Golang Generics: The Future of Go (](https://hackthedeveloper.com/golang-generics/)[hackthedeveloper.com](http://hackthedeveloper.com)[)](https://hackthedeveloper.com/golang-generics/)

---

## 아니 뭐 이런걸 다...

THE SHOR's ALGORITHM: Factorize Number Fast

[gophre/shor: Shor's algorithm (](https://github.com/gophre/shor)[github.com](http://github.com)[)](https://github.com/gophre/shor)

---

## 파일 동기화 쉽게 하기

예전에 bittorrent silo라는 솔루션이 있었습니다.

토렌트 기술을 이용해 각 머신의 폴더를 동기화 하는 기능이었는데요.

아쉽게도 현재는 찾아보기 어렵습니다.

그래도 일단은 이 솔루션이 사일로만큼의 사용성은 모르겠지만, 어느정도 대안이 되어 주지 않을까요?

[no-src/gofs: A cross-platform real-time file synchronization tool out of the box based on Golang (](https://github.com/no-src/gofs)[github.com](http://github.com)[)](https://github.com/no-src/gofs)