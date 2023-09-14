---
title: "23년 9월 전반기 뉴스레터"
datePublished: Thu Sep 14 2023 21:25:09 GMT+0000 (Coordinated Universal Time)
cuid: clmjoixu3000709la9fv47n68
slug: 23-9
tags: newsletter

---

## wasi 저도 써보곤 싶은데요?

고 1.21 버전에 wasi가 공식적으로 들어 왔습니다.

공식 블로그에 wasi에 대한 설명도 어느정도 있으니, 한번 구경해 보세요!

[WASI support in Go - The Go Programming Language](https://go.dev/blog/wasi)

---

## 올바른 프로파일링 방법?

여러분들은 고로 구성된 프로그램의 프로파일링을 많이 하시는 편인가요?

저는 PGO를 위해서라도 남기 남기려고 고려 중입니다.

그래서 이렇게 짜잔, 프로파일링에 대해 설명하는 아티클을 가져왔습니다!

[Profiling Go Applications in the Right Way with Examples | by Abdulsamet İLERİ | Sep, 2023 | Stackademic](https://blog.stackademic.com/profiling-go-applications-in-the-right-way-with-examples-e784526e9481)

---

## 겁나게 빠른 FastAPI

FastAPI는 파이썬의 고성능 웹프레임워크죠.

쉽고 빠르게 라우팅을 추가할 수 있으며,  
스웨거 문서도 만들 수 있습니다.

이걸 고에서 하면 정말 빠르지 않을까요?

[hvuhsg/GoAPI: GoAPI - A Fast and Easy-to-use Web Framework for Building APIs in Go (](https://github.com/hvuhsg/GoAPI)[github.com](http://github.com)[)](https://github.com/hvuhsg/GoAPI)

---

## 빠르게 고 어플리케이션 배포하기

한번 쯤 굳이 환경 설정을 하지 않고, 여러 환경에 배포하고 싶지 않으신가요?

[goreleaser/goreleaser: Deliver Go binaries as fast and easily as possible (](https://github.com/goreleaser/goreleaser)[github.com](http://github.com)[)](https://github.com/goreleaser/goreleaser)

[GoReleaser - GoReleaser](https://goreleaser.com/)

---

## 혹시 아직도 go build . 만 하십니까?

저도 그렇습니다.

스트립조차 하지 않죠.

이번 기회에 한번 빌드 옵션에 대해 제대로 파악해보고 필요한 곳에 잘 써야겠어요.

[Advanced Go Build Techniques | Stackademic](https://blog.stackademic.com/advanced-go-build-techniques-d44cbc0cbeda)

---

## 자바.. 게러세터.. 롬복..

에 있는 고 버전 롬복입니다..

[yujiachen-y/goaccessor: `goaccessor` is a Go tool designed to automate the generation of `getter` and `setter` boilerplate code for your types and variables. (](https://github.com/yujiachen-y/goaccessor)[github.com](http://github.com)[)](https://github.com/yujiachen-y/goaccessor)

---

## GraphQL에 다들 관심 많으신가요?

저는 쓰고는 싶은데, 고에서는 상황이 마땅치 않더라구요.

그래도 이런 아티클을 보면 한번쯤 해보고 싶습니다.

Rest를 GraphQL로 바꾸는 예시!

[Convert Rest Endpoint To GraphQL in Go - Hasan Ocak Tech Blog (](https://ocakhasan.github.io/golang-convert-rest-to-graphql/)[ocakhasan.github.io](http://ocakhasan.github.io)[)](https://ocakhasan.github.io/golang-convert-rest-to-graphql/)

---

## 새로운 웹소켓 라이브러리

얼마전 새로운 웹소켓 라이브러리가 첫 선을 보였습니다.

제가 개인적으로 존경하는 분도 컨트리뷰터에 있는 걸 보아 성능적으로 부족함이 없을 것같은 알 수 없는 믿음이 생기네요.

[lxzan/gws: lightweight go websocket server & client, supports running over tcp/kcp/uds. keywords: ws, wss, proxy, chat, golang (](https://github.com/lxzan/gws)[github.com](http://github.com)[)](https://github.com/lxzan/gws)

---

## Yet another sql client

[Yazeed1s/sqlweb: Relational-database web client (](https://github.com/Yazeed1s/sqlweb)[github.com](http://github.com)[)](https://github.com/Yazeed1s/sqlweb)

---

## 고 동시성의 이해

다른 언어에서 오신 분들이 유독 어려워하는 게 동시성에 대한 이해인 것같습니다.

하지만 실제로는 어려운 문제는 아니죠.

채널에 대한 조금의 이해만 생기면 쉽게 파악할 수 있으실 겁니다.

[Go Concurrency Visually Explained – Select statement | by Brian NQC | Aug, 2023 | Stackademic](https://blog.stackademic.com/go-concurrency-visually-explained-select-statement-b546596c8e6b)

---

## 크로뮴에 추가된 wasm GC

드디어 크로뮴에 wasm gc가 추가되었습니다.

[Intent to Ship: WebAssembly Garbage Collection (WasmGC) (](https://groups.google.com/a/chromium.org/g/blink-dev/c/K_GpDF0y5Q8/m/XIJSfbTHBwAJ)[google.com](http://google.com)[)](https://groups.google.com/a/chromium.org/g/blink-dev/c/K_GpDF0y5Q8/m/XIJSfbTHBwAJ)

---

## 해시를 통한 데이터 분류

데이터를 분산시켜서 처리하는 데에 매우 좋은 수단은 해시입니다.

레디스 클러스터는 해시를 기반으로 저장할 곳을 선택하죠.

로드밸런서도 동일한 클라이언트의 요청을 같은 서버에 전달하기 위해 해시를 쓰기도 합니다.

잘만 쓰면 유용하게 쓸 수 있는 해시, 한번 알아볼까요?

[Demystifying Consistent Hashing: A Key to Scalable and Efficient Data Distribution – The Efficient Dev](https://theefficientdev.blog/2023/09/09/demystifying-consistent-hashing-a-key-to-scalable-and-efficient-data-distribution/)

---

## 내게 맞는 DB는 뭘까?

여러분들의 환경에서 가장 적합한 DB는 뭐라고 생각하시나요?

RDB? Redis? Scylla?

[Picking the Perfect Database for Your Microservices (](https://amplication.com/blog/picking-the-perfect-database-for-your-microservices)[amplication.com](http://amplication.com)[)](https://amplication.com/blog/picking-the-perfect-database-for-your-microservices)

---

## Go 코드 내에서 프로토버퍼 생성 처리하기

매번 고를 위한 프로토버퍼 파일을 생성하기 위해 protoc의 플러그인을 설치해야했습니다.

물론 buf를 쓰면 모든 게 잘 풀리긴 합니다만, 개인이 직접 만든 툴이 있다면 내장시켜서 쓴다면 훨씬 편하지 않을까요?

[Protoc Plugins with Go. In this article we take a look at… | by Homayoon Alimohammadi | ITNEXT](https://itnext.io/protoc-plugins-with-go-52a178dbc27a)

---

## 젯브레인의 러스트 IDE

젯브레인에서 러스트 목적 IDE를 출시했습니다.

RustRover라는 이름에서 벌써 남다른 언어 사랑을 보이는 러스타시안이 보이네요.

[Introducing RustRover – A Standalone Rust IDE by JetBrains | The IntelliJ Rust Blog](https://blog.jetbrains.com/rust/2023/09/13/introducing-rustrover-a-standalone-rust-ide-by-jetbrains/)

---

## GDC가 이름을 바꿀 예정입니다.

Go Developer Community가 이름을 바꿔서 뉴스레터에서 더 넓은 분야의 개발 지식과 소식을 담고 싶습니다.

그래서 새로운 이름을 구상 중이고, 괜찮은 아이디어가 있다면 제보해 주세요!