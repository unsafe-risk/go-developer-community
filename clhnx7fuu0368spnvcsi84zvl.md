---
title: "23년 5월 전반기 뉴스레터"
datePublished: Sun May 14 2023 21:20:42 GMT+0000 (Coordinated Universal Time)
cuid: clhnx7fuu0368spnvcsi84zvl
slug: 32-5-1
tags: newsletter

---

## 모듈과 의존성 관리에 대한 가이드

고 언어에서 사용하는 의존성 관리 단위는 모듈입니다.  
그리고 여러 모듈들에서 의존하고 있는 외부 모듈들은 GOPATH 안에 기록되죠.  
여전히 고 모듈을 쓰지 않는 분들에 대한 좋은 가이드가 있습니다.  
이미 쓰고 있다면 내부 동작을 대략적으로 알 수 있는 기회가 될 수 있으니 한번 읽어 보세요!

[Dependency Management in Go (](https://blog.manel.in/posts/go-deps)[manel.in](http://manel.in)[)](https://blog.manel.in/posts/go-deps)

---

## 웹을 데스크탑 UI 환경으로 써보기

고 언어에는 여러 GUI 환경이 있습니다.

그 중에서 네이티브 환경을 제공하는 GUI 들도 물론 있습니다만,  
대체로는 많은 사람들이 만족하며 쓰고 있진 못 한 걸로 알고 있습니다.

그래서 이번에 원래 C/C++로 작성된 웹뷰를 cgo로 붙인 webui의 고 언어 바인딩을 소개해 드리려고 합니다.  
여러 OS에서 웹뷰를 자연스럽게 쓸 수 있다는 점이 매력적이고, 자바스크립트 이벤트를 고에서 처리할 수 있게 해주는 것이 특이 사항입니다.

[webui-dev/go-webui: Use any web browser as GUI, with Go in the backend and HTML5 in the frontend. (](https://github.com/webui-dev/go-webui)[github.com](http://github.com)[)](https://github.com/webui-dev/go-webui)

---

## 또 다른 사용하기 쉽고 편리한 캐시 라이브러

imcache가 얼마 전에 1.0을 릴리즈 했습니다.

imcache는 일반적인 sync.Map을 쓰는 것같은 편리한 인터페이스를 제공합니다.  
그러면서 TTL과 최대 한도 지정, 샤딩 등을 추가로 지원하고 있습니다.

[erni27/imcache: A zero-dependency generic in-memory cache Go library (](https://github.com/erni27/imcache)[github.com](http://github.com)[)](https://github.com/erni27/imcache)

---

## 함수의 옵셔널 패러미터

고 언어에서 옵셔널 패러미터를 어떻게 구현하는 지 알고 계신가요 ?ㅅ?

일단은 제가 알기로는 디폴트 옵션을 수정하는 1급 함수들을 사용하는 것으로 알고 있습니다.

간단하게 말씀드리면, `type Input { Name string; Age int16; Address string; }` 항목이 있다면, 이 타입을 옵셔널로 받는 함수는 `func Event(opt ...func(Input) Input) error` 같은 시그니처를 사용하게 되죠.

여기까지는 그냥 작성만 해주면 되니 불편한건 없습니다.  
조금 귀찮은 게 있다면, 함수가 실행될 때 `opt`로 들어온 함수들을 실행해 줘야하죠.  
`for`로 반복해서 처리해주면 되지만 그것도 귀찮은 여러분들을 위한 라이브러리를 소개해 드리겠습니다!

[RussellLuo/gopt: Generic Functional Options for Go. (](https://github.com/RussellLuo/gopt)[github.com](http://github.com)[)](https://github.com/RussellLuo/gopt)

---

## 편리한 비밀번호 생성기

한번씩 여러분들은 비밀번호를 생성하고 관리하는 게 귀찮지 않으신가요?

저는 좀 귀찮습니다. 하지만 이 중 생성하는 것까지는 적은 노력으로 해줄 수 있는 라이브러리가 있습니다!  
acopw-go는 쉬운 사용성을 제공하며 여러분들이 원하는 여러 포맷의 비밀번호를 만들어줍니다.  
이제 한번 비밀번호 매니저를 만들어 볼까요?

[acopw-go: Small cryptographically secure password generator package for Go. (](https://sr.ht/~jamesponddotco/acopw-go/)[sr.ht](http://sr.ht)[)](https://sr.ht/~jamesponddotco/acopw-go/)

---

## SQL 관계 다이어그램

RadhiFadlillah의 sqldiagram은 아직 MySQL만 지원하지만 SQL 파일(혹은 코드)를 입력하면,  
그에 상응하는 테이블들의 관계를 다이어그램으로 나타내줍니다.

다이어그램을 그리는 데에는 D2가 사용되었으니, 데이터베이스 관리나 학습 용도 뿐만 아니라 D2 라이브러리를 학습하기 위한 목적으로도 충분히 재밌을 것같습니다!

[RadhiFadlillah/sqldiagram: CLI to generate Entity Relationship Diagram from SQL file (](https://github.com/RadhiFadlillah/sqldiagram)[github.com](http://github.com)[)](https://github.com/RadhiFadlillah/sqldiagram)

---

## C/C++이랑도 사이좋게 지내야죠.. 암요..

C/C++에서는 구조체를 바이너리로 만들어 보내는 경우가 종종 있더라구요.

그래서인지 고에서도 한번씩 구조체를 깡으로 binary 라이브러리를 통해 해버리는 걸 본적이 있는데,  
이게 그다지 직관적이거나 명시적인 것과 거리가 멀다고 생각해서 그렇게 좋게 보지 못하고 있습니다.

그러던 중 struc이란 라이브러리를 찾았습니다.  
이 라이브러리는 binary 라이브러리가 하는 그것과 비슷하지만 구조체 태그를 통해 더욱 명확하게 어떻게 해달라는 걸 조정할 수 있습니다.

빅/리틀은 물론 여러 타입과 패딩도 설정할 수 있으니 한번 C/C++의 pack, unpack을 감당해야 하신다면 시도해 보는 것도 좋다고 봅니다.

[lunixbochs/struc: Better binary packing for Go (](https://github.com/lunixbochs/struc)[github.com](http://github.com)[)](https://github.com/lunixbochs/struc)

---

## 바퀴를 왜이리 좋아하는 건데..

고퍼들은 뭔가 바퀴를 좋아하는 것같습니다.  
분산 데이터베이스인 코크로치 데이터베이스도 그렇고, 이번에 소개시켜드릴 고키부리라는 테스트 툴도 그렇습니다.

고키부리는 프로젝트의 루트 폴더에서 실행하면, 해당 프로젝트의 테스트를 불러오고 실행하고 결과를 관리하는 웹 UI를 제공합니다.

[michenriksen/gokiburi: Automatic test runs for Go projects (](https://github.com/michenriksen/gokiburi)[github.com](http://github.com)[)](https://github.com/michenriksen/gokiburi)

---

## 여러분들이 atomic 래퍼 타입을 사용해야 하는 이유

고 언어 1.19 버전 이후로는 atomic 패키지에 `atomic.Int64`같은 래퍼 타입이 생겼습니다.

많은 분들이 그냥 `atomic.LoadInt64`, `atomic.StorInt64`같은 `int64` 포인터를 접근하는 래퍼를 쓰는 것과 무엇이 다른지 신경을 안 쓰실 것같습니다.

하지만 이 변화는 개발자들로 하여금 발생할 수 있는 실수를 줄여줍니다!  
관련 아티클은 다음과 같습니다.

[The Go 1.19 Atomic Wrappers and why to use them | by Ralph Caraveo | May, 2023 | Medium](https://medium.com/@deckarep/the-go-1-19-atomic-wrappers-and-why-to-use-them-ae14c1177ad8)

---

## BFF 인증 패턴에 대해서

저는 아직까지 BFF를 적극적으로 활용해본 적이 없습니다.

하지만 언젠가는 BFF를 해야하고, 인증에 대해서는 언젠가 해야하는 부분인 만큼 이 아티클이 비기너에게 적지 않은 도움이 될 수 있을 거라 생각합니다.

[Backend For Frontend Authentication Pattern in Go | by Mehul Gohil | May, 2023 | Medium](https://medium.com/@mehulgohil75/backend-for-frontend-auth-pattern-in-go-bcf5a1d16aa)

---

## 에러 핸들링 좀 어떻게 해줘

고 언어 개발자들 대상으로 한 23년 1분기 설문조사 결과가 발표되었습니다.

여전히 에러 핸들링에 대한 어려움이 상위권에 랭크되어 있고,  
cgo의 크로스플랫폼 빌드는 어려운 이야기로 보입니다.

이외에 여러 긍정적인 조사 결과와 개선해야할 포인트들이 있으니 한번 확인해 보세요!

[Go Developer Survey 2023 Q1 Results - The Go Programming Language](https://go.dev/blog/survey2023-q1-results)

---

## 커맨드 라인에서 AI를 활용하는 방법

mods는 CLI에서 표준 입력을 통해 값을 주고 응답을 받을 수 있는 AI 툴입니다.

표준 입력과 표준 출력을 통해서 값을 처리하기 때문에, 쉘의 파이프라인(`|`), 입력 처리(`<`), 출력 처리(`>`, `>>`)를 그대로 활용할 수 있습니다.

[charmbracelet/mods: AI on the command line (](https://github.com/charmbracelet/mods)[github.com](http://github.com)[)](https://github.com/charmbracelet/mods)

---

## 여러분들 HTTP 응답을 어떻게 처리하고 계시나요?

Manish R Jane은 자신의 고루틴 누수 사례를 들어, "HTTP 응답을 꼭 닫을 것"을 강조하고 있습니다.

왜 HTTP 응답을 닫아야 하는지, 그 결말에 다다른 이유와 방지법에 대해 다음 아티클에서 확인해 보세요!

[TIL: Go Response Body MUST be closed, even if you don’t read it - Manish R Jain](https://manishrjain.com/must-close-golang-http-response)

---

## 고에서 압축 쉽게 하기

klauspost의 compress라는 패키지는 다양한 압축 알고리즘을 제공하는 압축 라이브러리입니다.

단순 나열만 해도, `zstandard`, `S2`, `deflate`, `gzip`, `zip`, `snappy`, `huff0`, `FSE`, `pgzip` 등이 있습니다.

[klauspost/compress: Optimized Go Compression Packages (](https://github.com/klauspost/compress)[github.com](http://github.com)[)](https://github.com/klauspost/compress)