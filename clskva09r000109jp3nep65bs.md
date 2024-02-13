---
title: "24년 2월 전반기 뉴스레터"
datePublished: Tue Feb 13 2024 21:20:09 GMT+0000 (Coordinated Universal Time)
cuid: clskva09r000109jp3nep65bs
slug: 24-2
tags: newsletter

---

1월 하반기 뉴스레터를 예고도 없이 쉬어 죄송합니다. &lt;(\_ \_)&gt;

---

## postgres에서 full text search engine를 추구하면 안 되는 걸까?

라고는 했지만 이미 GIN 인덱스를 이용해서 한국어 full text search도 가능하고, 그 성능도 꽤 좋은 것같습니다.

데이터 삽입 성능만 앞으로 어떻게 해결할 수 있다면 ES의 아성에 도전해볼 수 있을까요?

[PostgreSQL GIN 인덱스를 통한 LIKE 검색 성능 개선 | by 김병묵 | VUNO SW Dev | Medium](https://medium.com/vuno-sw-dev/postgresql-gin-%EC%9D%B8%EB%8D%B1%EC%8A%A4%EB%A5%BC-%ED%86%B5%ED%95%9C-like-%EA%B2%80%EC%83%89-%EC%84%B1%EB%8A%A5-%EA%B0%9C%EC%84%A0-3c6b05c7e75f)

[Postgres is Enough (github.com)](https://gist.github.com/cpursley/c8fb81fe8a7e5df038158bdfe0f06dbb)

[When does Postgres stop being good enough for full text search? (meilisearch.com)](https://blog.meilisearch.com/postgres-full-text-search-limitations/?ref=dailydev)

---

## 고 언어에서 인터페이스 모킹 어떻게 하시나요?

일일이 항상 `true`를 반환하는 거라도 만드시나요?

그런 단순한 반환값이라면 자동으로 만들어주면 좋을 텐데 말이죠?

[Meet Moq: Easily mock interfaces in Go | by Mat Ryer | Medium](https://medium.com/@matryer/meet-moq-easily-mock-interfaces-in-go-476444187d10#.uy9qkloty)

[matryer/moq: Interface mocking tool for go generate (github.com)](https://github.com/matryer/moq)

---

## 저도 풀 텍스트 서치 엔진에 대한 꿈이 있습니다.

선행되어야 하는 것 중 하나가 이 문장이 어떤 언어로 되어 있는가 판단하는 것이지요.

[pemistahl/lingua-go: The most accurate natural language detection library for Go, suitable for short text and mixed-language text (](https://github.com/pemistahl/lingua-go)[github.com](http://github.com)[)](https://github.com/pemistahl/lingua-go)

---

## [파이썬으로 만들어보는 검색 엔진](https://github.com/pemistahl/lingua-go)

[A search engine in 80 lines of Python (alexmolas.com)](https://github.com/pemistahl/lingua-go)

---

## [라인에서 고 자료구조 라이브러리를 낸 적 있는 거 아십니까?](https://github.com/pemistahl/lingua-go)

[High performance! Thread safe](https://github.com/pemistahl/lingua-go)! Lock free! 합니다만 자바 향이 좀 있네요.

하지만 내부 구현체들은 하나하나 좋은 것같습니다.

[line/garr: Collection of high performance, thread-safe, lock-free go data structures (github.com)](https://github.com/line/garr)

---

## Zanzibar라고 들어 보셨을 겁니다.

구글에서 발표했던 글로벌 권한 인증 시스템인데, `ory`에서 고 언어로된 구현체를 하나 내줬군요.

[ory/keto: Open Source (Go) implementation of "Zanzibar: Google's Consistent, Global Authorization System". Ships gRPC, REST APIs, newSQL, and an easy and granular permission language. Supports ACL, RBAC, and other access models. (github.com)](https://github.com/ory/keto)

---

## 이런 로드 밸런싱은 어때요?

외부 연결이 아니라 내부 서비스 간 로드 밸런싱에 유용해 보이는 도구입니다.

[https://github.com/YanKawaYu/go-socket](https://github.com/YanKawaYu/go-socket)

---

## Embedded Redis for go?

레디스가 진짜 고랭 앱에 임베딩된 건 아니지만 비슷한 느낌은 낼 수 있어 보입니다.

심지어 이 친구는 고랭 앱에 올라가면서 분산 저장소로도 활용할 수 있다구요?

[buraksezer/olric: Distributed in-memory object store. It can be used as an embedded Go library and a language-independent service. (github.com)](https://github.com/buraksezer/olric)

---

## API를 만드는 새로운 방법

마이크로소프트가 `typespec`이라는 물건을 새로 출시했습니다.

독자적인 IDL을 기반으로 openapi 문서나 protobuf 파일 등을 생성하는 문서로, 기존의 openapi 문서를 작성하는 것의 불편한 점을 잘 해소할 수 있지 않을까 생각합니다.

[TypeSpec](https://typespec.io/)

[deepmap/oapi-codegen: Generate Go client and server boilerplate from OpenAPI 3 specifications (github.com)](https://github.com/deepmap/oapi-codegen)

---

## 고 언어 객체에서 타입스크립트 객체로

하다 못해 고 언어로 된 구조체를 타입스크립트 클래스로 바꿔주기만 해도 전 매우 만족스러울 것같았습니다.

여태 만족스러운 물건을 찾진 못 했는데, 이 친구라면 제 꿈을 이뤄줄지도...?

[gzuidhof/tygo: Generate Typescript types from Golang source code (](https://github.com/gzuidhof/tygo)[github.com](http://github.com)[)](https://github.com/gzuidhof/tygo)

---

## 고 언어와 타입스크립트 사이의 브릿지

그래서 전 고 언어와 타입스크립트 서버 간 통신도 가능했으면 좋겠습니다.

[BlueRPC : End-to-End Go-Typescript Type Safety (](https://bluerpc-docs.onrender.com/)[bluerpc-docs.onrender.com](http://bluerpc-docs.onrender.com)[)](https://bluerpc-docs.onrender.com/)

---

## [Yet Another HTTP Server](https://bluerpc-docs.onrender.com/)

[hossein1376/grape: Modern, zero-dependency HTT](https://bluerpc-docs.onrender.com/)[P l](https://github.com/gzuidhof/tygo)[ibrary for Go (github.com)](https://github.com/hossein1376/grape)

---

## 리액트 어떻게 공부하시나요?

관리자 대시보드 한번 만들어 보시는 것도 좋지 않을까요?

[How to Build an Admin Dashboard with React (freecodecamp.org)](https://www.freecodecamp.org/news/build-admin-dashboard-react/)

---

## 20060102150405

[Golang - Advanced Date-Time Utility functions | by Dharti R | Jan, 2024 | Canopas](https://blog.canopas.com/golang-date-time-utilities-part-2-b1192eb04842)

[maniartech/gotime: The gotime is a Go library for simplified date and time proc](https://blog.canopas.com/golang-date-time-utilities-part-2-b1192eb04842)[essing, offering intuitive parsing, formatting, and relative time calculations. (github.com)](https://github.com/maniartech/gotime)

---

## 컨테이너의 네트워크가 어떻게 동작하는 지 알고 계신 가요?

전 대충만 아는데...

[How Container Networking Works: a Docker Bridge Network From Scratch (iximiuz.com)](https://labs.iximiuz.com/tutorials/container-networking-from-scratch)

---

## 자바...는 너무 어렵지만

postgres에 관련된 내용이니 읽어 봐야...

[@Transactional의 해로움 (channel.io)](https://channel.io/ko/blog/bad-transactional)

---

## 리액트 맛 고 언어 UI 라이브러리

햝짝

[goui-org/goui: An experimental web framework for creating user interfaces (github.com)](https://github.com/goui-org/goui)

---

## Very Fast Stream Multiplexer for Golang

[xtaci/smux: A Stream Multiplexing Library for golang with least memory usage(TDMA) (github.com)](https://github.com/xtaci/smux)

---

## 언제나 SIMD 최적화를 보면 신기해요.

하지만 제가 할 순 없죠.

[From slow to SIMD: A Go optimization story (sourcegraph.com)](https://sourcegraph.com/blog/slow-to-simd)